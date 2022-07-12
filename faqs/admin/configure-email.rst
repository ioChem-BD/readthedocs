Configure email service
=======================

ioChem-BD can be configured to send *reset password* emails when the *Forgot your password?* option is used on the login page. The service also sends notifications to new users with a welcome message and a link to set their password.

To perform these operations, the email service must be properly configured inside ioChem-BD. 

Initial checks
--------------

Before configuring our service, will check that we can communicate with the mail server on its port. To do so we need the IP or DNS entry where the mail server resides, then the port number where it runs. The most common ones are:

  * 25: plain communication, no encoding
  * 465: using SSL protocol
  * 587: using STARTTLS protocol
 
The port numbers can change or have different types of protocols running on them, take this only as a guide and always talk with your IT team before configuring the service.

Having the IP or DNS entry, the port and protocol will now check that we have communication through this port. On the server where ioChem-BD resides will run the following *telnet* command (change the server name and the port to match your server configuration):

.. code:: bash

       $ telnet smtp.gmail.com 465
       

If the telnet command connects the server, we can assess the connection is enabled and no firewall is blocking our communication, otherwise, the port must be opened on the network side.

.. code:: bash
       
       Trying XXX.XXX.XXX.XXX...
       Connected to smtp.gmail.com.
       Escape character is '^]'.
       
       telnet> quit 
       Connection closed
 

Now using the *nmap* command will determine the protocol used in the mail server to communicate:

.. code:: bash

       $  nmap -Pn --script ssl-enum-ciphers -p 465 smtp.gmail.com
        
        map scan report for smtp.google.com (XXX.XXX.XXX.XXX)
        Host is up (0.000083s latency).
        
        PORT    STATE SERVICE
        465/tcp open  smtps
        | ssl-enum-ciphers:  
        |   TLSv1.0:
        |     ciphers:
        |       TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA (ecdh_x25519) - A
        |       TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA (ecdh_x25519) - A
        |       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (ecdh_x25519) - A
        |       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (ecdh_x25519) - A
        |       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 2048) - A
        |       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 2048) - A
        |       TLS_RSA_WITH_3DES_EDE_CBC_SHA (rsa 2048) - C
        |     compressors:
        |       NULL
        |     cipher preference: server
        |     warnings:
        |       64-bit block cipher 3DES vulnerable to SWEET32 attack
        |   TLSv1.1:
        |     ciphers:
        |       TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA (ecdh_x25519) - A
        |       TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA (ecdh_x25519) - A
        |       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (ecdh_x25519) - A
        |       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (ecdh_x25519) - A
        |       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 2048) - A
        |       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 2048) - A
        |       TLS_RSA_WITH_3DES_EDE_CBC_SHA (rsa 2048) - C
        |     compressors:
        |       NULL
        |     cipher preference: server
        |     warnings:
        |       64-bit block cipher 3DES vulnerable to SWEET32 attack
        |   TLSv1.2:  
        |     ciphers:  
        |       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA (secp256r1) - A
        |       TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 (secp256r1) - A
        |       TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 (secp256r1) - A
        |       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA (secp256r1) - A
        |       TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 (secp256r1) - A
        |       TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (secp256r1) - A
        |       TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256 (secp256r1) - A
        |       TLS_RSA_WITH_AES_128_CBC_SHA (rsa 2048) - A
        |       TLS_RSA_WITH_AES_128_CBC_SHA256 (rsa 2048) - A
        |       TLS_RSA_WITH_AES_128_GCM_SHA256 (rsa 2048) - A
        |       TLS_RSA_WITH_AES_256_CBC_SHA (rsa 2048) - A
        |       TLS_RSA_WITH_AES_256_CBC_SHA256 (rsa 2048) - A
        |       TLS_RSA_WITH_AES_256_GCM_SHA384 (rsa 2048) - A
        |     compressors:  
        |       NULL
        |     cipher preference: client
        |_  least strength: A
 
         
The command outputs that it is offering the service in different protocols such as TLSv1.0, TLSv1.1, TLSv1.2. Always choose the highest protocol version, in this case, TLSv1.2, the lowest ones are no longer secure.  

A different output can indicate that the service is closed/network communication blocked:

.. code:: bash

       $ nmap -Pn --script ssl-enum-ciphers -p 465 smtp.gmail.com
       
        Starting Nmap 7.80 ( https://nmap.org ) at 2022-01-21 13:54 CET
        Nmap scan report for smtp.gmail.com (XXX.XXX.XXX.XXX)
        Host is up.
        Other addresses for smtp.gmail.com (not scanned): XXXX:XXXXX:XXXX:c07::6c
        rDNS record for XXX.XXX.XXX.XXX: aa-aa-aaaa.aaaaa.aaa
        
        PORT    STATE    SERVICE
        465/tcp filtered smtps
        
        Nmap done: 1 IP address (1 host up) scanned in 2.23 seconds


Now, we will apply this information to the configuration files of ioChem-BD. 
Edit *BASE_PATH/browse/config/dspace.cfg* to configure the email service, being *BASE_PATH* the base folder where ioChem-BD software is installed.

The properties starting with *mail.* are the ones devoted to this service.

.. code:: bash

    # SMTP mail server
    mail.server = 
    
    # SMTP mail server authentication username and password (if required)
    mail.server.username = 
    mail.server.password =
    
    # SMTP mail server alternate port (defaults to 25)
    mail.server.port = 
    
    # From address for mail
    mail.from.address = 
    
    # Currently limited to one recipient!
    feedback.recipient = 
    
    # General site administration (Webmaster) e-mail
    mail.admin = 
    
    # Recipient for server errors and alerts
    alert.recipient = 
    
    # Recipient for new user registration emails
    registration.notify = 
    
    # Set the default mail character set. This may be overridden by providing a line
    # inside the email template "charset: <encoding>", otherwise this default is used.
    mail.charset = UTF-8
    
    # A comma-separated list of hostnames that are allowed to refer browsers to email forms.
    # Default behaviour is to accept referrals only from dspace.hostname
    mail.allowed.referrers = 
    
    mail.extraproperties = 
   

The following configurations are basic guidelines of the configuration, please refer to this `javax.mail`_ reference page to explore further configurations, 
most of them will be added to *mail.extraproperties* property.  

.. warning::
   Every modification of the email parameters will require restarting the ioChem-BD service to load the new configuration.
  

STMP configuration per protocol
-------------------------------

- `Plain text`_ / no encoding
- `SSL`_
- `STARTTLS`_


Plain text
~~~~~~~~~~

Edit *BASE_PATH/browse/config/dspace.cfg* with the following properties:

.. code:: bash
    
    mail.server.port = 25 
    #mail.extraproperties = 
   

Comment *mail.extraproperties* property and set port equals 25. This option is not recommended because all information will travel plain, without encryption. 


SSL
~~~

Edit *BASE_PATH/browse/config/dspace.cfg* with the following properties:

.. code:: bash

    mail.server.port = 465    
    mail.extraproperties = mail.smtp.ssl.protocols=TLSv1.2, \
                       mail.smtp.socketFactory.port=465, \
                       mail.smtp.socketFactory.class=javax.net.ssl.SSLSocketFactory, \
                       mail.smtp.socketFactory.fallback=false

Specify the encryption protocol in the *mail.extraproperties* appending the  *mail.smtp.ssl.protocols* with one that the mail server is using.

STARTTLS
~~~~~~~~

Edit *BASE_PATH/browse/config/dspace.cfg* with the following properties:

.. code:: bash

    mail.server.port = 587
    mail.extraproperties = mail.smtp.starttls.enable=true, \
                       mail.smtp.socketFactory.port=587, \
                       mail.smtp.starttls.required=true    


If this setup doesn't work, try to set also the ssl protocol used:

.. code:: bash

    mail.server.port = 587
    mail.extraproperties = mail.smtp.starttls.enable=true, \
                       mail.smtp.socketFactory.port=587, \
                       mail.smtp.ssl.protocols=TLSv1.2, \
                       mail.smtp.starttls.required=true



Please contact us at contact@iochem-bd.org for further assistance if you have problems configuring the mail service. 
   
.. _Plain text: #plaintext
.. _SSL: #ssl
.. _STARTTLS: #starttls   
.. _javax.mail: https://www.tutorialspoint.com/javamail_api/javamail_api_smtp_servers.htm
