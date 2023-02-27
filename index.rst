.. ioChem-BD documentation master file, created by
   sphinx-quickstart on Wed Feb 12 21:10:49 2020.


ioChem-BD documentation
===========================================


.. raw:: html

   <a href='https://gitlab.com/ioChem-BD/iochem-bd/-/blob/master/COPYING'>
    <img src='https://img.shields.io/badge/license-AGPL-green' alt='License type' />
   </a>
   <a href='https://docs.iochem-bd.org/en/latest/?badge=latest'>
    <img src='https://readthedocs.org/projects/iochem-bd-documentation/badge/?version=latest' alt='Documentation Status' />
   </a>

Welcome
------------

| Find here notes and guides about ioChem-BD platform, how to use it and eventually, how to install it. 
| Don’t hesitate contacting us at contact@iochem-bd.org if you need further information.

.. topic:: Please consider reading some papers regarding this platform and other related topics:

   | Álvarez-Moreno, M., de Graaf, C., López, N., Maseras, F., Poblet, J. M., Bo, C.  
   | *Managing the Computational Chemistry Big Data Problem: The ioChem-BD Platform.* 
   | J. Chem. Inf. Model, 55, 1, 95-103 (2015). https://doi.org/10.1021/ci500593j

   | Bo, C., Maseras, F. & López, N. 
   | *The role of computational results databases in accelerating the discovery of catalysts.* 
   | Nat Catal 1, 809–810 (2018). https://doi.org/10.1038/s41929-018-0176-4


About
-----------

ioChem-BD relies in an unique software platform which is builded in a modular way to satisfy all the needs: data creation and curation, publishing, storage, indexing data and search engine services.


| The main node of the network runs the `Find module`_, which acts as central server and is feed by any new data published in the repositories. 
| The *Find* module provides a fast chemical-aware search engine open public service and is hosted at the Barcelona Supercomputer Center (BSC). Also, the `first public-access node`_ is provided by BSC.

Other ioChem-BD modules automatize relevant data-extracting processes and transforms raw numerical data into labeled data in a database. It provides the researcher with tools for validating, enriching, publishing and sharing information, as well as tools to access, post-process and visualize data.

Users include computational chemistry research groups worldwide, university libraries and related services, and high performance supercomputer centers. 

.. figure:: /imgs/IoChem-BD_diagram.png 
   :alt: ioChem-BD function overview diagram
   
   ioChem-BD function overview diagram
   

Modular architecture
~~~~~~~~~~~~~~~~~~~~~~~~~

The services available in the repository are actually provided by different modules: *Create*, *Browse* and *Find*. Each one has different objectives in managing chemistry digital assets, and they both complement each other. While there exists one only *Find*, there are as many *Create*/*Browse* modules as nodes in the network.

Create module
+++++++++++++++++

This web service is intended for use in private manner. It is fed with user files uploaded via a web browser or from any box running a Linux shell client, see `Uploading Content into Create`_ page.

Features:
 
  - Private interface, content accessed by user permission only 
  - Productivity-oriented GUI designed using the zKoss framework
  - Automated document, data graph/chart generation: PDF files of supporting information reports, reaction energy profiles, etc...
  - Search by keywords and administrative metadata 
  - Compact and intuitive design 
  - Publish user selected data to the companion *Browse* module


| The data is structured inside this module using **projects** and **calculations**, like folders and files inside a file system. 
| Each calculation has to be enclosed inside a project, and a project can be on the root or enclosed inside another project as a subproject. 
| Data organization is totally left to the user’s own criteria.


Browse module
++++++++++++++++++

| This web service is intended for public access. It is fed with projects and calculations published from the *Create* module. 
| The *Browse* module uses entities such are **Community**, **Collection** and **Item** to organize the information:

  - Communities are the basis of hierarchy organization
  - Collections are the end point where to publish elements 
  - Items are viewable digital assets. An item can be made of a single or a group of files, all of them related to the same calculation: 
   
     - input and output files, 
     - graphics, 
     - associated documents, 
     - and more...


We can make a direct correspondence of elements between *Create* and *Browse* organizational elements:

=============== ================
*Create* entity *Browse* entity
=============== ================
\-              Community
Project         Collection
Calculation     Item
=============== ================

It is up to ioChem-BD’s system administrator to `generate users, groups`_ and `communities`_ where to publish content. Collections and items are automatically generated during the process of publication from the Create module.


Topics inside this documentation
================================

.. toctree::
   :maxdepth: 1
   :caption: Links
   :includehidden:

   Go back to ioChem-BD central <https://www.iochem-bd.org>


.. toctree::
   :maxdepth: 1
   :caption: User guide
   
   Create module walktrough </guides/usage/create-module-walktrough>
   Uploading content into Create </guides/usage/uploading-content-to-create>   
   Publish a dataset into Browse </guides/usage/publishing-calculations/publish-process>
   Generating reports </guides/usage/generating-reports>
   Video tutorials </guides/usage/video-tutorials>

.. toctree::
   :maxdepth: 1
   :caption: Installation guide

   System requirements </guides/installation/system-requirements>
   Steps prior installation </guides/installation/required-steps>
   Installation procedure </guides/installation/installation>
   Creating users and groups </guides/installation/user-and-group-generation>
   Publishing endpoints definition </guides/installation/publishing-endpoints-definition>
   Post-installation steps</guides/installation/post-installation-steps>           
   Advanced system configuration </guides/advanced-system-configuration>


.. toctree::
   :maxdepth: 2
   :caption: FAQ
   
   General usage </faqs/general>
   Administration </faqs/administration>
   Errors   </faqs/error> 
   
   

.. toctree::
   :maxdepth: 1
   :caption: Data conversion
   
   How to use this help? <conversion-howto>
   Feature matrix <feature-matrix>
   From chemical codes to CML<conversion-cml>
   From CML to HTML5 report <conversion-html>
   Conversion test dataset <conversion-test-dataset>


.. _Uploading Content page: ./usage/uploading-content-to-create.html
.. _`Find module`: https://www.iochem-bd.org
.. _`first public-access node`: https://iochem-bd.bsc.es
.. _`Uploading Content into Create`: guides/usage/uploading-content-to-create.html
.. _`generate users, groups`: guides/installation/user-and-group-generation.html
.. _`communities`:  guides/installation/publishing-endpoints-definition.html


