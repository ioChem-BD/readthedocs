Installation procedure
======================

The system administrator must perform following actions prior deploying the ioChem-BD platform.

Create iochembd system user
---------------------------

First we will create a user account called *iochembd*, it will hold ioChem-BD files and will be responsible for running the web service that provides access to the software.

.. code:: bash

     root# useradd -m iochembd

We can use any other non privileged system user or username to install or run this software, we called it *iochembd* as an example. 

.. attention:: The following commands will be run as the *iochembd* user, unless otherwise mentioned.

Unzip application package
-------------------------

To start ioChem-BD installation, we will first `download`_ and extract the software package in the *iochembd* user home.

.. code:: bash

      iochembd$ cd ~
      iochembd$ tar -xvf iochembd-binary-X.X.X.tar.gz

All the software is contained inside the single folder you just decompressed, with the following structure:

.. code:: bash

       iochembd
       ├── apache-tomcat
       ├── browse
       ├── cas
       ├── COPYING
       ├── create
       ├── init-script
       ├── init.sh
       ├── installer.jar
       ├── postinstall.sh
       ├── README.md
       ├── ssl
       ├── third-party
       ├── THIRD-PARTY.txt
       ├── updates
       ├── webapps
       └── webapps2

We can place it anywhere in our filesystem: one good candidates is *iochembd* user home, another one is inside */opt* folder. 

From now on we will talk about *BASE_PATH* when we refer to the path of this folder. 
All extracted folders and its inner files must belong to the same user and group than the one that will start the web-server service (in this case *iochembd*), 
so it will be able to read and write inside it without problem.

Init database
-------------

PostgreSQL configuration
~~~~~~~~~~~~~~~~~~~~~~~~

If you have just installed the PostgreSQL server package you need to initialise its databases and start the database server, as *root* user you must run:

.. code:: bash

   root# /sbin/service postgresql initdb

You must set also PostgreSQL to start every time you restart your server.

.. code:: bash

   root# chkconfig --level 345 postgresql on

Now we will configure PostgreSQL authentication file to allow login with password, we will edit */var/lib/pgsql/data/pg_hba.conf* and add these two lines:

.. code:: bash

       # TYPE DATABASE USER ADDRESS METHOD
       # IPv4 local connections:
       host iochemCreate iochembd 127.0.0.1/32 md5
       host iochemBrowse iochembd 127.0.0.1/32 md5

We can now start the PostgreSQL database service:

.. code:: bash

   root# /sbin/service postgresql restart

We will now create a new PostgreSQL database user and set the account password. 

From the command line we will change to "root" or "postgres" user account (one with enough rights to execute the *createuser* command) and type the following:

.. code:: bash

   postgres$ createuser -s -d -l -P iochembd

      Enter password for new role: XXXXXXX
      Enter it again:  XXXXXXX

After we create the account, please keep this password safe and consider it the **database.password** parameter. We will now create the two databases that will store ioChem-BD data:

.. code:: bash

   postgres$ createdb -E UTF8 --locale='en_US.utf8' -T template0 -O iochembd "iochemCreate"
   postgres$ createdb -E UTF8 --locale='en_US.utf8' -T template0 -O iochembd "iochemBrowse"

Run the installation script
---------------------------

We must now change back to *iochembd* user. 

Now we can execute the visual installer by moving inside *BASE_PATH* and executing the *init.sh* script.

.. code:: bash

   iochembd$ cd *BASEPATH*
   iochembd$ ./init.sh

A form will appear showing that the installer has started. 


.. figure:: /imgs/Install_step_1.png
   :alt: Welcome form
   
   Welcome form

The next one will display the e-mail parameters configuration, more info at `mail fields`_. There are two checkboxes that configure email to use encryption.

-  with no encrypted email services (default port 25) we will set both options unchecked
-  with SSL encryption (default port 465) we will check first option
-  with STARTTLS (default port 587) we will check both options

.. figure:: /imgs/Install_step_200.png
   :alt: E-mail parameters

   E-mail parameters 

After filling in all fields, we can test the email parameters by sending a test message. We can click on the *Send test* button to check this configuration. 

.. figure:: /imgs/Install_step_2a.png
   :alt: wikilink

   Send test dialog
   
In the new form we can set the destination email and in a few seconds we must receive a test message from the installation program in our mailbox.
 
.. important:: Please check you received the test email because this is a very important step in ioChem-BD configuration, otherwise it will not be able to send notification to users.
   
   
The next form will ask for all the details related to SSL certificate generation, more info at `certificate fields`_:

.. figure:: /imgs/Install_step_3.png
   :alt: wikilink

   Certificate generation

Once our certificate has been generated and associated, a new form will pop up. In this one we must define the database connection parameters. Once all of them have been filled, we need to click on the *Test connection* button to check whether the database connection is successful.

.. figure:: /imgs/Install_step_4.png
   :alt: Database connection form

   Database connection form

The next form will ask for basic login information for ioChem-BD administrator account generation, more info at `administrator account fields`_:

.. figure:: /imgs/Install_step_5.png
   :alt: Admin account setup

   Admin account setup

Last form will ask for installing ioChem-BD, clicking on *Back* button will start the process all over again.

.. figure:: /imgs/Install_step_6_a.png
   :alt: Installation confirmation form

   Installation confirmation form

After clicking on *Install*, a series of messages will inform us of the different install stages, the process can take a few minutes to finish all steps.

.. figure:: /imgs/Install_step_7a.png
   :alt: Processing steps

   Processing steps

Once installation has finished, if you used default port (443) or one under 1024 to run ioChem-BD you must run **as root** the script file indicated by installer: *postinstall.sh*. It will open such privileged port to ioChem-BD services. 


If you get a message like this:

.. code:: bash

   root#  BASEPATH/postinstall.sh: line 6: setcap: command not found

This is because your system doesn’t have the *setcap* package installed, run this command in order to install the package and then run the post install script again.

.. code:: bash

   root# zypper install libcap-progs
   root# BASEPATH/postinstall.sh


Edit /etc/hosts
---------------

You must add an entry on */etc/hosts* to avoid ioChem-BD web services to go outside your network to find your domain, so you must enter the following line on /etc/hosts,

.. code:: bash

      127.0.0.1     iochem-bd.urv.es            #Please replace iochem-bd.urv.es for your server domain name

Start the web service
---------------------

The files responsible for managing our web service are:

.. code:: console

   iochembd$  BASE_PATH/apache-tomcat/bin/startup.sh    # to start service
   iochembd$  BASE_PATH/apache-tomcat/bin/shutdown.sh   # to stop service
  

After starting the web server you can track *BASE_PATH*/apache-tomcat/logs/catalina.out file to look for start-up errors. If they appear, please `contact us`_ in order to assist you as soon as possible.

Access ioChem-BD main page
--------------------------

Once installation has ended and web service has started, you should be able to access the main page of the ioChem-BD software, from now on *BASE_URL*. 

.. figure:: /imgs/Homepage2.png
   :alt: ioChem-BD Homepage
   
   ioChem-BD Homepage
 
To access both modules you can click on homepage top links or append module name to base URL:

-  *BASE_URL*/create
-  *BASE_URL*/browse

The web browser will “complain” about the self-signed certificate of the HTTPS pages, we just need to add an exception to avoid future questions or install a `valid HTTPS certificate`_. 

Now that the ioChem-BD software is successfully deployed, we have to create user accounts and define user groups. Please refer to the `Post installation steps`_ page.

.. _download: https://gitlab.com/ioChem-BD/iochem-bd/-/releases
.. _mail fields: ./required-steps.html#mail-settings
.. _certificate fields: ./required-steps.html#certificate-fields
.. _administrator account fields: ./required-steps.html#administrator-account-settings
.. _contact us: mailto:contact@iochem-bd.org
.. _Post installation steps: ./post-installation-steps.html
.. _valid HTTPS certificate: ../other-operations/replace-https-certificate.html