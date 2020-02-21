quild.module
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/adf/program.header-d3e4278
   /codes/adf/quild.coord-d3e4398

============

.. table:: Implementation level

   +-----------------------------------+-----------------------------------+
   | Type                              | Status                            |
   +===================================+===================================+
   | CML extraction template           | |image0|                          |
   +-----------------------------------+-----------------------------------+
   | HTML5 representation              | |image1|                          |
   +-----------------------------------+-----------------------------------+

.. table:: Template attributes

   +-----------------------------------+-----------------------------------+
   | Attribute                         | Value                             |
   +===================================+===================================+
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | quild.module                      |
   +-----------------------------------+-----------------------------------+
   | name                              | QUILD Module                      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s+\*\                           |
   |                                   | s+\|\s+Q\sU\sI\sL\sD\s+\|\s+\*.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Leaving\sQUILD.\*             |
   +-----------------------------------+-----------------------------------+
   | offset                            | -10                               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | quild/quild.xml                   |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

    *******************************************************************************
    *                                                                             *
    *  -------------------------------------                                      *
    *   Amsterdam Density Functional  (ADF)         2009.01   September 29th, 2009*
    *  -------------------------------------                                      *
    *                                               Build 200912192106            *
    *                                                                             *
    *                                                                             *
    *                            =====================                            *
    *                            |                   |                            *
    *                            |     Q U I L D     |                            *
    *                            |                   |                            *
    *                            =====================                            *
    *                                                                             *
    *                                                                             *
    *   Online information and documentation:  http://www.scm.com                 *
    *   E-mail:  support@scm.com   info@scm.com                                   *
    *                                                                             *
    *   Scientific publications using ADF results must be properly referenced     *
    *   See the User Manuals (or the web site) for recommended citations          *
    *   The terms and conditions of the End User License Agreement apply to       *
    *   the use of ADF, http://www.scm.com/Sales/LicAgreement.html                *
    *                                                                             *
    *****************************  pentium64_linux  *******************************
    
    QUILD 2009.01  RunTime: May03-2010 13:06:38
    
   ...
   =============
   Leaving QUILD
   =============
    
       

**Template definition.**

.. code:: xml

   <templateList>  <xi:include href="quild/../program.header.xml" />  <xi:include href="quild/quild.coord.xml" />        
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
