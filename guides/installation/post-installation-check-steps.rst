Final checks
============

| Finally, system administrator must check the following communication channels in order for 
| ioChem-BD platform to properly operate:
|  -  When using the shell client, check that `the defined port`_ where the ioChem-BD runs is accesible from that machine.
|  -  Check `calculation publication workflow`_ works from Create to Browse.
|  -  Check Browse email `notification parameters`_ are valid by sending test emails from *Edit eperson* page.

It is up to the sysadmin to configure the network interfaces, firewall services, proxies and other routing mechanisms to allow proper communications.

Optional tasks
++++++++++++++

In order to improve site content indexing by web robots and search engines, you can crontab the generation of the Browse module sitemap with the following command.

.. code:: bash

    iochembd$ crontab -e
    #Append the following line being *BASEPATH* the platform installation folder
            
    00 00 * * *  BASEPATH/browse/bin/dspace generate-sitemaps 
   


This last step conclude the ioChem-BD system installation and configuration.

Summary
-------

Let us recap all steps taken to arrive to this point:
 
  1. Gather important system configuration parameters. 
  2. Create database and start software installation. 
  3. Start webserver and login as administrator. 
  4. Generate users and groups from *Browse* module. 
  5. Create communities and subcommunities where users will be able to publish their digital assets. 
  6. Setup backup script and test platform network connectivity.
 

.. _the defined port: ./required-steps.html#certificate-fields
.. _calculation publication workflow: ../usage/publishing-calculations/publish-process.html
.. _notification parameters: ./required-steps.html#mail-settings
