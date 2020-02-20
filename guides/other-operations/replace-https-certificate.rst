Replace HTTPS certificate 
=========================

ioChem-BD generates a self-signed certificate during its installation to enable secure HTTPS communications.

The downside of self-signed certificates is that they are not recognized by web browsers, so users will receive a warning message every time they access your ioChem-BD instance.

In order to use a valid HTTPS certificate and avoid such access warnings we encourage to replace that certificate for one expedited by a Certification Authority (CA), or any other valid certificate you already posses.

Two scenarios have been setup for ioChem-BD administrators in order to help in replacing HTTPS certificates, please choose the one that better fits your needs.


.. toctree::

   Associate an existing certificate you already own <./replace-https-certificate/with-existing-certificate>
   Purchase a new certificate on a Certification Authority (CA)  <./replace-https-certificate/purchase-new-ca-certificate>
   Undo certificate replacement process <./replace-https-certificate/undo-certificate-replacement>
