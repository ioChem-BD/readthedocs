Set upload limits
=================

The administrator can set limits to the size of the uploaded files via the web interface to improve service performance.

.. important:: 
   Uploading content to Create module using its web interface instead of its `shell client`_ requires the ioChem-BD web server to perform the file conversion using web server CPUs.
   
   This action can become a bottleneck if multiple large output files are uploaded using the web interface.   
   
To limit the size of the files uploaded via web, there are two parameters that can be set on *BASE_PATH/create/resource.properties* file:
    
.. code:: bash

   upload.max.file.size = -1
   upload.output.max.file.size = -1


Properties: 
  * upload.max.file.size: Define the max file size uploaded via web, in bytes.
  * upload.output.max.file.size: Define the max file size of the output files, the file type that consumes more CPU during file conversion, in bytes.
  
Unsetting the parameter or setting its value to -1 will remove that specific upload restriction.

.. warning::
   Every modification of these parameters will require restarting the ioChem-BD service to load the new configuration.


.. _shell client: ../../guides/usage/uploading-content-to-create/using-shell-client.html