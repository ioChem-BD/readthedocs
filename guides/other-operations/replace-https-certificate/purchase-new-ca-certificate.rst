Purchase a new certificate form a Certification Authority (CA)
==============================================================

In this section we will show the steps necessary to request a certificate to a Certification Authority. In this specific case we will use `ssls.com`_ CA to request the certificate, but you can choose any other CA of your choice, the steps will be similar, if not equal.

To buy a certificate we first need to generate a *Certificate Request* file (CSR). Inside it there will be defined the most relevant data of our certificate (domain to register, institution, city, country, etc).

Then we will submit such CSR file to the CA and after it checks that we own the server of that domain, it will generate and send us the public certificate file(s) to install in our server.

Certificate Request (CSR) generation
------------------------------------

You need to run the following commands from the same user account that runs the ioChem-BD software to avoid file permission errors.

First we will move to the *ssl/new* folder and execute the following commands:

.. code:: console

      iochembd$  cd BASE_PATH/ssl/new
      iochembd$  openssl genrsa -out pkcs1.key 2048   
      iochembd$  openssl pkcs8 -topk8 -inform PEM -outform PEM -nocrypt -in pkcs1.key -out certificate.key
      iochembd$  rm pkcs1.key
      

Created private key, now go for the certificate request

.. code:: console

      iochembd$  openssl req -new -key certificate.key -out request.csr

      You are about to be asked to enter information that will be incorporated into your certificate request.
      What you are about to enter is what is called a Distinguished Name or a DN. There are quite a few fields but you can leave some blank 

      For some fields there will be a default value, If you hit enter the field will be left blank.
      -----
     
      Country Name (2 letter code) [XX]:     ES 
      State or Province Name (full name) []:     Tarragona
      Locality Name (eg, city) [Default City]:    Tarragona
      Organization Name (eg, company) [Default Company Ltd]:     Institution of Chemical Research of Catalonia   #Fill with your institution information, 
      Organizational Unit Name (eg, section) []:     Theoretical Group
      Common Name (eg, your name or your servers hostname) []:    iochem-bd.iciq.es                               # Set on Common Name the Domain URL for the certificate
      Email Address []:    contact@example.com
     
      Please enter the following extra attributes to be sent with your certificate request
     
      # Leave following fields empty
     
      A challenge password []:    
      An optional company name []:
   

Purchasing the certificate
--------------------------


| At this point, on *BASE_PATH/create/ssl* folder there will be:
|  - a file called *request.csr* , that is the certificate request file that we will send to the CA and 
|  - a file called *certificate.key* with the private key of the custom generated certificate.

| We must now contact the CA to request the public certificate.
| In the page of the CA we will pick a single domain certificate and then add it the basket.
| Other type of domain certificate can be select if it better suits your needs, but the single domain one is a cheap solution.

|image0|

Once selected, customer can select the number of years that the certificate will last until it expires. The longer expiration date, the less certificate updates have to be performed during time.

|image1|

In the next step, the payment method must be filled in

|image2|

After the payment has been done, the CA page will display a new certificate in the list, ready to be requested.

|image3|

The following page will request to paste the content of the CSR file we have generated, so we will copy paste it including the *BEGIN NEW CERTIFICATE REQUEST* and the *END NEW CERTIFICATE REQUEST* lines. Paste CSR file content there.

|image4|

On the next page we will choose the "Java Tomcat" option.

|image5|

The next page will display the supported domains for this new certificate, please double check this fields are valid.

|image6|


Validating domain ownership
~~~~~~~~~~~~~~~~~~~~~~~~~~~

| The next step is crucial in the certificate generation process. The CA must check that your are the real owner of that domain. 
| To check it you can choose two validation methods:

  - To store an specific file inside your web server, so the CA will later retrieve it, verifying you are the domain owner, `instructions here`_. 
  - To send you a verification mail to an specific domain email address , `further instructions here`_.

|image7|

After deciding the validation method (via file or email), we must finally fill the contact form.

|image8|

If you followed the previous steps for validating your certificate, the line of your certificate will now display a green *Active* button on your account.

|image9|

| If you click the certificate link, you will be presented a page with the option to download the certificate public keys. We will use this files soon for installing the certificate. 
| Click on *Download* option to get public certificate zip file.

|image10|

Installing the certificate
--------------------------

Once we have the certificate .zip file we will extract its contents into the BASE_PATH/create/ssl folder

.. code:: console

      iochembd$  cp iochem-bd.iciq.es.zip BASE_PATH/create/ssl    
      iochembd$  cd BASE_PATH/create/ssl
      iochembd$  unzip iochem-bd.iciq.es.zip

After the extraction you must have on *BASE_PATH/create/ssl* folder at least the following files:

-  A *certificate.key* file with your private key
-  A *\*.crt* file with your public key certificate in X509 PEM format
-  An optional *\*.bundle* with the intermediate CA certificates in X509 PEM format

With the following command you can extract.

Now you can follow the instructions from `Associate an existing certificate`_ page.

.. _ssls.com: http://ssls.com
.. _instructions here: validate-domain-owner.html#validate-domain-owner-using-CA-provided-file
.. _further instructions here: validate-domain-owner.html#validate-domain-owner-using-email-address
.. _Associate an existing certificate: with-existing-certificate.html

.. |image0| image:: /imgs/Acert1.png
.. |image1| image:: /imgs/Acert2.png
.. |image2| image:: /imgs/Acert3.png
.. |image3| image:: /imgs/Cert2.png
.. |image4| image:: /imgs/Cert3.png
.. |image5| image:: /imgs/Cert4.png
.. |image6| image:: /imgs/Cert5.png
.. |image7| image:: /imgs/Cert6.png
.. |image8| image:: /imgs/Cert8.png
.. |image9| image:: /imgs/Cert12.png
.. |image10| image:: /imgs/Cert13.png
