Steps prior installation
========================


The ioChem-BD installation procedure will ask for some configuration information that the sysadmin must provide in order to enable all the functionalities of the software. 

Please write down all these fields and keep them at hand during the installation process 

Required information 
--------------------

In this section we will list all fields that will be prompted for the user to fulfill, all accompanied by a little description of its usage in the system and some possible values. 

We define *Field name* column in the tables as an easy way to refer later to these parameters during installation process. 


Mail settings
~~~~~~~~~~~~~

It is advised to create an email account at your institution for ioChem-BD software, otherwise you can use a personal email address as sender of all notifications.

+--------------------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------+
| Field name               | Description                                                                                     | Sample values                                                    |
+==========================+=================================================================================================+==================================================================+
| **smtp.server.hostname** | SMTP server hostname                                                                            | smtp.urv.cat                                                     |
+--------------------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------+
| **smtp.server.port**     | Port number used by the mail server                                                             | 25  /                                                            |
|                          |                                                                                                 | 587                                                              |
+--------------------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------+
| **smtp.mail.from**       | Sender e-mail address, all notifications from ioChem-BD will be sent using this e-mail address  | iochem-bd@urv.cat     /                                          |
|                          |                                                                                                 | iochem-bd@iciq.es     /                                          |
|                          |                                                                                                 | username@institution.com                                         |
+--------------------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------+
| **smtp.mail.username**   | (Optional) If mail server requires authentication, set email account username                   |                                                                  |
+--------------------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------+
| **smtp.mail.password**   | (Optional) If mail server requires authentication, set email account password                   |                                                                  |
+--------------------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------+


Certificate fields
~~~~~~~~~~~~~~~~~~

The ioChem-BD software should to be run on a machine that can be publicly accessible, these are the benefits:

   - Users can access to it from any point of the world.
   - Your published datasets become Open Data and Open Science.
   - Your instance can synchronize its public data into a `bigger data repository`_ of theoretical chemistry results. 

.. tip:: You can request the synchronization of your ioChem-BD instance to the central service by `filling this form`_.  

================= ============================================================================================================================= ==========================================
Field name        Description                                                                                                                   Sample values
================= ============================================================================================================================= ==========================================
**host.hostname** Public qualified host name of the web server, if run locally remember to set the entry on your /etc/hosts file                iochem-bd.iciq.es /
                                                                                                                                                rodi.urv.es / 
                                                                                                                                                test.iochem-bd.org 
**host.ip**       Public ip of the web server                                                                                                   130.206.36.13 / 127.0.0.1
**host.port**     Port where the software will run and will be browsed (default: 443) Never use 80 because ioChem-BD uses HTTPS instead of HTTP 443 (default)
================= ============================================================================================================================= ==========================================

All communications inside this software:

  - shell client <-> modules, 
  - module <-> module,
  - and user browser <-> module 
  
are safety encrypted using SSL certificates; right now it uses self-signed certificates but in future revisions we will add support for self-registering Certification Authority (CA) certificates like the ones from Lets Encrypt. 

Please keep in mind that the field defined in **${cert.organization}** will be the organization name, which will be appended to all generated content and displayed in ioChem-BD web pages.

============================ ====================================================================== ===========================================================================
Field name                   Description                                                            Sample values
============================ ====================================================================== ===========================================================================
**cert.organizational.unit** Organizational unit defined inside SSL certificate                     Dept.Computational Chemistry / Quantum Chemistry Group
**cert.organization**        Name of your organization (avoid acronyms/abbreviations when possible) Universitat Rovira i Virgili / Institute of Chemical Research of Catalonia
**cert.city**                City/location of your organization                                     Tarragona / Barcelona / Paris
**cert.state**               State/Province or your organization                                    Catalonia - Spain / France
**cert.country.code**        Country code (two characters, `check it here`_)                        ES / FR
============================ ====================================================================== ===========================================================================

Database settings
~~~~~~~~~~~~~~~~~

These fields will be used by ioChem-BD to define its database connection parameters.

===================== ============================================================ =============
Field name            Description                                                  Sample values
===================== ============================================================ =============
**database.host**     Hostname of postgresql server                                localhost
**database.port**     Postgresql port number                                       5432
**database.username** Postgresql username (`defined during installation process`_) iochembd
**database.password** Postgresql password (`defined during installation process`_) 
===================== ============================================================ =============

Administrator account settings
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

During the last steps of installation you will be prompted to generate an ioChem-BD administrator account, such account will be the one in charge of managing and configuring all the software package. 

.. important:: For the sake of ioChem-BD’s security, it is advised that the administrator creates a **non-admin** user account if he/she wants to work with the *Create module* as a normal user.

=================== ================================================================== ================================================================
Field name          Description                                                        Sample values
=================== ================================================================== ================================================================
**admin.email**     Administrator email and also the admin username inside the system  iochem-bd@urv.cat / iochem-bd@iciq.es / username@institution.com
**admin.password**  Administration account password                                   
**admin.telephone** Contact phone that will appear on system errors and notifications  +34 977-XXX-XXX
=================== ================================================================== ================================================================


.. _filling this form: https://www.iochem-bd.org/home.jsp?action=requestAccount
.. _bigger data repository: https://www.iochem-bd.org
.. _check it here: http://www.nationsonline.org/oneworld/country_code_list.htm
.. _defined during installation process: ./installation.html#init-database
