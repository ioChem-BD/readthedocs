Set upload limits
=================

The administrator can set size limits to the uploaded files to improve software performance and control disk usage. 

Uploading content using the web interface requires the ioChem-BD web server to perform the chemical files format conversion using web server CPUs. This action can become a bottleneck if multiple large output files are uploaded using this method.

The use of the `shell client`_ is the recommended method to favour system performance, setting upload limits can favour this choice.
    
.. important::

    The ioChem-BD platform has a default maximum file size upload limit set to **1GB** but output files greater than **100MB** should not be uploaded via web interface.


Uploading a file that exceeds the defined size when limitations are set will prompt the following error on the shell client:   

.. code:: bash

   $  loadadf -i input.com -o mo3w3o19.fac.opt.res -a large_8gb_file.xtc -n mo3w3o19.fac.opt -d mo3w3o19.fac.opt
       Processing calculation, please wait. 
       Problems ocurred during the execution of the command: 
       The request was rejected because its size (8192 MB) exceeds the configured maximum (500 MB).

And also to web users:

.. figure:: /imgs/Faqs_upload_size_error.png
   :alt: File size exceeded error form
   
  
The following parameters must be configured on *BASE_PATH/create/resource.properties* file to enable upload limits, where *BASE_PATH* is the software installation folder: 
    
.. code:: bash

   upload.max.file.size.soft = -1
   upload.max.output.file.size.soft = -1
   
   upload.max.file.size.hard = -1    
   upload.max.output.file.size.hard = -1
   
   upload.restriction.users.hard =   
   upload.max.file.size.message = 


Upload limit types
~~~~~~~~~~~~~~~~~~

There are two types of upload limits: *soft* and *hard*. The first is more restrictive than the latest.

By default, all users fall under the *soft* limitation type. The platform administrator defines the users allowed to use the *hard* quota. 

Soft limit
##########

Related parameters: 

.. code:: bash
 
   upload.max.file.size.soft = -1
   upload.max.output.file.size.soft = -1
 

The first parameter will define the maximum size for any uploaded file in bytes. The second one will define the maximum size for the output files, the one that consumes the server CPU if uploaded via web. 
Setting any value to -1 will set it to unlimited.

The following is an example defining a soft limit on all uploaded files greater than 500MB and output files greater than 25 MB.

.. code:: bash
 
   upload.max.file.size.soft = 524288000               # 500*1024*1024 in bytes 
   upload.max.output.file.size.soft = 26214400         #  25*1024*1024 in bytes


Hard limit
##########

Under some circumstances, the *soft* limit can not be enough for some users, so the hard limit is the option to configure:  

Related parameters:

.. code:: bash
 
   upload.max.file.size.hard = -1    
   upload.max.output.file.size.hard = -1
   upload.restriction.users.hard =


The first parameter will define the maximum size for any uploaded file in bytes. The second one will define the maximum size for the output files.
The last parameter is a list of the usernames that have the *hard* limit enabled, separated by colons (:). 

The following is an example defining a *hard* limit on all uploaded files greater than 2GB, output files greater than 100 MB and assigning these quota limits to users *jdoe* and *dzavala*:  

.. code:: bash
 
   upload.max.file.size.hard =  2147483648
   upload.max.output.file.size.hard = 104857600
   upload.restriction.users.hard = jdoe:dzavala

Setting any limit value to -1 will set it to unlimited.

Notifying users
###############

The last configuration parameter allows customizing the upload error message by appending additional steps, such as informing users on how to request the hard limit.:

.. code:: bash

   upload.max.file.size.message = 


An example of the indications message:

.. code:: bash

   upload.max.file.size.message = Please contact with admin1@iochem-bd.org to request an extended upload limit.


The provided message will appear in the warning notifications:

.. code:: bash

   $  loadadf -i input.com -o mo3w3o19.fac.opt.res -a large_8gb_file.xtc -n mo3w3o19.fac.opt -d mo3w3o19.fac.opt
       Processing calculation, please wait. 
       Problems ocurred during the execution of the command: 
       The request was rejected because its size (8192 MB) exceeds the configured maximum (500 MB). 
       Please contact with admin1@iochem-bd.org to request an extended upload limit.


.. figure:: /imgs/Faqs_upload_size_error_with_message.png
   :alt: File size exceeded error form


.. warning::

   Any modification of these parameters will require to reload its values, it can be done in two ways:
      - Restarting the ioChem-BD service or
      - accessing the refresh global variables url on the Create module: *https://BASE_URL/create/admintools/uploadlimits*, being *BASE_URL* the url where ioChem-BD is served.

.. _shell client: ../../guides/usage/uploading-content-to-create/using-shell-client.html
