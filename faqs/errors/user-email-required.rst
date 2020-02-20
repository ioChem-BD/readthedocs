A 'User Email is required' error page appears after login 
=========================================================

This error appears normally during the first login just after installing the ioChem-BD software. 

Symptoms
---------

In this case, the user gets the following error message:

::

   User Email is required
   Your SSO system is not configured properly to release user email info

Cause
-------

The error is due to a misconfiguration in the machine that runs ioChem-BD software. In this case, the Central Authentication Service (CAS) can’t find its own domain because it’s not defined in */etc/hosts* file. This results in missing user profile information right after authentication.

Steps to fix it
----------------

The sysadmin of the server running ioChem-BD software must append a line inside */etc/hosts* file.

This line must set loopback IP of the machine (127.0.0.1) to the **host.hostname** parameter `defined during installation`_.   

As an example, if ioChem-BD is running on *test.iochem-bd.org*, the line to add inside */etc/hosts* should be the following

::

   127.0.0.1 test.iochem-bd.org

After editing this file, the error will disappear just by reloading the login page or log in again.


.. _defined during installation: ../../guides/installation/required-steps.html#certificate-fields