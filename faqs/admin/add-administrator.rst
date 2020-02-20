Add a new administrator user
============================ 

To create a new administrator account, you must have shell access to the ioChem-BD installation folder. 
Then move to the *BASE_PATH/browse/bin* subfolder. On this path, type the following command and follow the instructions.

.. code:: bash

     $ cd browse/bin
     $ ./dspace create-administrator

     Creating an initial administrator account
     E-mail address: user@institution.org
     First name: Michael
     Last name: Knight
     Password will not display on screen.
     Password: *****
     Again to confirm: *****
     Is the above data correct? (y or n): y
     Administrator account created

Your admin user will then be generated and you will be able to login.
