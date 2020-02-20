Associate an existing certificate
=================================

Requirements
------------

The *openssl* software package needs to be installed in your system and inside the *$PATH* variable (login with the same user account that runs the ioChem-BD software and try to execute *openssl version* command to check its properly installed).

.. code:: console

   iochembd$  openssl version
   OpenSSL 1.0.2h  3 May 2016  (or another version)


| The update process also needs these certificate files
|   -  A file with the public certificate
|   -  A file with the certificate private key
|   -  A file with the intermediate certificates (optional)      

| Now we will detail the file names and the format of every file enumerated previously. 
| The file with the public certificate must be encoded on **X.509 PEM** format and with extension **.crt**. Example:

.. code:: console

      -----BEGIN CERTIFICATE-----
      MIIE/zCCBGgCAg4CMA0GCSqGSIb3DQEBBQUAMIGbMQswCQYDVQQGEwJKUDEOMAwG
      A1UECBMFVG9reW8xEDAOBgNVBAcTB0NodW8ta3UxETAPBgNVBAoTCEZyYW5rNERE    
      ...
      3V1dbLU5id63lVD8sUEULyfWFGk3L+Uka5oiSsxwZhdIb/Q=
      -----END CERTIFICATE----

The file with the private certificate must be encoded on **unencrypted PKCS#8 PEM** format and with extension **.key**. Example:

.. code:: console

      -----BEGIN PRIVATE KEY-----
      MHcCAQEEIBdVHnnzZmJm+Z1HAYYOZlvnB8Dj8kVx9XBH+6UCWlGUoAoGCCqGSM49
      AwEHoUQDQgAEThPp/xgEov0mKg2s0GII76VkZAcCc//3quAqzg+PuFKXgruaF7K
      ...
      -----END PRIVATE KEY-----

Under some circumstances the certificate also has some intermediate certificates that contain its upper level certificates (the ones that the certificate trusts). In this special case you must concatenate all that certificates into a single file on **X509 PEM** format , ordered from them most local to most global and must have **.bundle** extension. Example file content with three intermediate
certificates:

.. code:: console

      -----BEGIN CERTIFICATE-----
      ....
      -----END CERTIFICATE-----
      -----BEGIN CERTIFICATE-----
      ....
      -----END CERTIFICATE-----
      -----BEGIN CERTIFICATE-----
      ....
      -----END CERTIFICATE-----

--------------

Final checks: To ensure our certification chain is valid before we update ioChem-BD certificates, we will run the following command:

.. code:: bash

      iochembd$   openssl verify -CAfile additional.bundle  certificate.crt 
      certificate.crt : OK

Any different response from previous command except OK should be analyzed and it’s not advised to continue this certificate update procedure until the certification chain is totally valid.

Update process
--------------

From now on we will talk about *BASE_PATH* when we refer to the path where the software has been installed, please replace it for the real full path

We will run the update process with the same user account that runs the software (in this case *iochembd*), all previous certificate files must also be owned by this user.

We will initially stop the web service:

.. code:: bash

      iochembd$  BASE_PATH/apache-tomcat/bin/shutdown.sh

Once the service has stopped, we will copy copy all certificate files inside *BASE_PATH/ssl/new* folder:

.. code:: bash

      iochembd$  cp certificate.crt    BASE_PATH/ssl/new    #Only file extensions are fixed, filenames can be arbitrary 
      iochembd$  cp certificate.key    BASE_PATH/ssl/new     
      iochembd$  cp additional.bundle  BASE_PATH/ssl/new    #Optional file

With the requested files inside the ssl folder, we will launch the tool that replaces self-signed certificates for the new ones.

.. code:: bash

      iochembd$  cd BASE_PATH/updates
      iochembd$  ./updater.sh -p ReplaceDomainCertificate

.. error:: If you get an error retrieving the patch files similar to this one:

.. code:: console

      Error retrieving patch files on http://www.iochem-bd.org/conversion/updates/ReplaceDomainCertificate/update.tar.gz!
      Please contact ioChem-BD development team at: contact@iochem-bd.org

| Please replace the update script *updater.sh* with the latest version from: 
| https://www.iochem-bd.org/update/updater.sh.

The output of this patch will enumerate all steps performed and which files are backed up and replaced:

.. code:: console

   16:13:40 [main] INFO  utils.Utils - Running command:[/bin/pgrep, -a, -f, tomcat]
   16:13:40 [main] INFO  update.UpdatePatch -      Running update vxxx.ReplaceDomainCertificate
   16:13:40 [main] INFO  update.UpdatePatch - Generating pkcs12 certificate file from certs + key
   16:13:40 [main] INFO  utils.Utils - Running command:[openssl, pkcs12, -export, -in, /home/user/iochem-bd/ssl/new/cert.crt, -inkey, /home/user/iochem-bd/ssl/new/cert.key, -out, /home/user/iochem-bd/ssl/new/certificate.p12, -name, iochem-bd, -chain, -CAfile, /home/user/iochem-bd/ssl/new/cert.bundle, -caname, root, -passin, pass:changeit, -passout, pass:changeit]
   16:13:40 [main] INFO  update.UpdatePatch - Generating keystore from pkcs12 certificate
   16:13:40 [main] INFO  utils.Utils - Running command:[keytool, -importkeystore, -deststorepass, changeit, -destkeypass, changeit, -destkeystore, /home/user/iochem-bd/ssl/new/keystore.jks, -srckeystore, /home/user/iochem-bd/ssl/new/certificate.p12, -srcstoretype, PKCS12, -srcstorepass, changeit, -alias, iochem-bd]
   16:13:40 [main] INFO  update.UpdatePatch - Replacing keystore with the newly generated one.
   16:13:40 [main] INFO  update.UpdatePatch - 

   End update successfully
   16:13:40 [main] INFO  update.UpdateProcess - ioChem-BD updated with patch ReplaceDomainCertificate. 


If the result of the update process is successful, we can start the service. 

.. code:: bash

      iochembd$    BASE_PATH/apache-tomcat-7.0.37/bin/startup.sh

Once started, we can check that the ioChem-BD service is running with a valid HTTPS certificate, green lock indicates a valid certificate.

.. figure:: /imgs/Correct_https_certificate.png
   :alt: Green lock on navigation bar
   
   Green lock on navigation bar



.. important:: If an exception raises during the certification replacement process, you can undo the entire process by `restoring previous certificates`_ and contact contact@iochem-bd.org reporting your errors


.. _restoring previous certificates: ./undo-certificate-replacement.html