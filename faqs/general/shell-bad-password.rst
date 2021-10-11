Can’t log in with the shell client
==================================

Under certain circumstances, you can have trouble connecting to the Create module with the shell client.  

Check connectivity
~~~~~~~~~~~~~~~~~~

Please first verify you can reach the Create web server from the host where you run the shell client by using a tool like *wget* and pointing your ioChem-BD homepage:

.. code:: bash

   user$   wget https://iochem-bd.bsc.es                             # Replace the hostname for your specific ioChem-BD URL
           wget: unable to resolve host address 'iochem-bd.bsc.es'   # This message will indicate you can't reach the server


Change your credentials
~~~~~~~~~~~~~~~~~~~~~~~

If you try to connect multiple times and receive the following messages:

.. code:: bash

   user$   . ./start-rep-shell 
           Could not retrieve latest session cookie, please login again.
           Username: user54958@iochem-bd.org
           Password (empty to quit): 
           
           Could not retrieve latest session cookie, please login again.
           Username: user54958@iochem-bd.org
           Password (empty to quit): 
 
It could be due to an incorrect/forgotten password, please change it using the `reset password`_ link.


Check your system date
~~~~~~~~~~~~~~~~~~~~~~

The ioChem-BD login mechanism checks your current system date against the server's date to avoid login reply attacks. 

If your system has an invalid date (future or outdated) the shell client will be unable to validate displaying the following error:
  

.. code:: bash

   user$   . ./start-rep-shell 
   user$   Could not retrieve latest session cookie, please login again.
           Username: user54958@iochem-bd.org
           Password (empty to quit): 
           Credentials are valid.
           Starting client...
           Client started.

   12:00:10.953 [main] ERROR cat.iciq.tcg.labbook.shell.main.ShellClient - Unable to validate ticket [ST-2xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxiochem-bd-bsc]
   12:00:10.954 [main] ERROR cat.iciq.tcg.labbook.shell.main.ShellClient - Error login on CREATE web system. Check credentials
   12:00:10.954 [main] ERROR cat.iciq.tcg.labbook.shell.Main - Error login on CREATE web system. Check credentials


To fix it, please set your system date (and timezone) to the current, valid value. 



.. _Reset password: reset-password.html

  