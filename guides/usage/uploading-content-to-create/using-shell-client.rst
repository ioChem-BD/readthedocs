Shell client
------------

The ioChem-BD shell client is intented to be deployed into a Linux box, where your calculations are generated and reside, or on any \*nix machine where calculations are visible.

First we need to download the shell client into that box. To do so, you will first login in your Create Module. Then you click on *Options* in upper right menu bar. You need to selecy *Download shell client* so that it displays a form that will request your ioChem-BD password, the same that you used to login.

.. figure:: /imgs/WebUploadForm5.png
   :alt: Options menu bar

   Options menu bar

The Create module will generate a .zip bundle with all files. Decompress it using a command like:

.. code:: console

       $ unzip shell.zip

After deflating this file you have to add executing rights to the *start-rep-shell* command and secure the properties file.

.. code:: console

       $ cd shell
       $ chmod +x start-rep-shell
       $ chmod 700 ./resources/resources.properties

The next step is to connect to the Create module via our Linux shell client. Call the *start-rep-shell* script. 

.. important:: The call has to be made using the *source* command so to affect the current shell and to add our set of specific shell commands.

.. code:: console

       $ source start-rep-shell                                


Or its abreviatted form:

.. code:: console
                 
       $ . start-rep-shell
       
                     

More infornation: `Shell commands`_

.. _Shell commands: shell-commands.html


.. toctree::
   :maxdepth: 2
   :hidden:
   
   /guides/usage/uploading-content-to-create/shell-commands
   /guides/usage/uploading-content-to-create/using-shell-client/shell-automated-scripts.rst