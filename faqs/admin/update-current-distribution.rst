Update platform
===============

The update process of ioChem-BD is quite straightforward by using an update script bundled with the platform.

Please update as soon as you get the `notification`_ of new releases to fix bugs and get the latest functionalities.

Steps to do: 
  1. Shutdown the service
  2. Backup application files and data (run the `backup script`_ if you already have it defined) 
  3. Run update script and check process logs 
  4. Start the service


Previous considerations prior updating: 

  - In the code examples, BASE_PATH is considered the base path where the software is installed 
  - All operations should be executed by the same linux user that installed and runs the software, unless otherwise advised


1. Shutdown the server
~~~~~~~~~~~~~~~~~~~~~~

Update process must be performed with the service stopped.

.. code:: bash

   iochembd$  cd BASE_PATH/apache-tomcat/bin
   iochembd$  ./shutdown.sh
   ... wait one minute
   iochembd$  ps -eaf | grep tomcat
   ... if there is no running process it has stopped properly otherwise kill the process

2. Perform a backup of the application files and data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Please review `backup script`_ page on the documentation for more information about the backup process automation.

3. Run update script
~~~~~~~~~~~~~~~~~~~~

.. important:: On versions prior v2.0.0, **the update script has been updated**, please download the new one `here`_ and replace the one inside *BASE_PATH/updates* folder

Now run the utility:

.. code:: bash

   iochembd$   cd BASE_PATH/updates
   iochembd$   ./updater.sh

The update process will start downloading pending patches and applying them one after the other until it reaches latest.

In case you get an error updating the platform, please copy the output text from the update tool and send it to contact@iochem-bd.org, we will contact you as soon as possible to aid you in solving the possible errors in this process. Meanwhile, you can recover the software from the backup copy described in point 2.

4. Start the server
~~~~~~~~~~~~~~~~~~~

If the update process ended successfully, the patch program will start the server automatically to apply latest updates.

.. code:: bash

   17:01:09.543 [main] INFO  update.UpdatePatch -  Task: Running Ant target : update
   17:03:42.600 [main] INFO  utils.SqlRunner -     Running update vxxx.SetCalculationOrdering
   17:03:43.073 [main] INFO  update.UpdatePatch -  Task: Updating Browse dspace.cfg file
   17:03:43.120 [main] INFO  update.TomcatManager - Starting Apache Tomcat...  <== Server started
   17:03:43.128 [main] INFO  utils.Utils - Running command:[/home/iochembd/iochem-bd/apache-tomcat/bin/startup.sh]
   17:03:43.128 [main] INFO  update.UpdateProcess - ioChem-BD updated to latest version.
   Update process finished.

Otherwise, start it manually with the following commands:

.. code:: bash

   iochembd$   cd *BASE_PATH*/apache-tomcat/bin
   iochembd$   ./startup.sh

This will finish the update process of the ioChem-BD platform.

.. _notification: http://eepurl.com/dJDgWI
.. _backup script: ../../guides/installation/backup-policy.html
.. _here: https://www.iochem-bd.org/update/updater.sh
