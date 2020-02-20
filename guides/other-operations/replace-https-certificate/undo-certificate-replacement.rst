Undo certificate replacement process
====================================

If an exception raises during the certification replacement process, you can undo the entire process by replacing current certificate files for its backup copies.

The process affects the following files:

+---------------------------------------------------------+---------------------------------------------------------------------+
|  File                                                   | Usage                                                               |
+=========================================================+=====================================================================+
| *BASE_PATH*/ssl/**keystore**                            | Java keystore used by Apache Tomcat to serve HTTPS encoded content  |
+---------------------------------------------------------+---------------------------------------------------------------------+
| *BASE_PATH*/ssl/**truststore**                          | Java Runtime trusted public certificates keystore                   |
+---------------------------------------------------------+---------------------------------------------------------------------+

This files are backup before starting the process by appending a timestamp to its name.

To restore them, we will stop the web service and replace the generated files with the latest backup files.

.. code:: bash

      iochembd$  BASE_PATH/apache-tomcat/bin/shutdown.sh
      
      iochembd$  cp BASE_PATH/ssl/keystore_161019191826 BASE_PATH/ssl/keystore   
      iochembd$  cp BASE_PATH/ssl/truststore_161019191826  BASE_PATH/ssl/truststore
      
      iochembd$  BASE_PATH/apache-tomcat/bin/startup.sh

With these steps, our original certificates will be restored and the faulty update process fixed.


.. _revert certificate changes: #undo-certificate-generation-process
