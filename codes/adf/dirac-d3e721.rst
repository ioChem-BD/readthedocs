dirac
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/adf/program.header-d3e728

=====

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
   | id                                | dirac                             |
   +-----------------------------------+-----------------------------------+
   | name                              | Dirac module                      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s+\*\                           |
   |                                   | s+\|\s+D\sI\sR\sA\sC\s+\|\s+\*.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*D\s+                          |
   |                                   | I\s+R\s+A\s+C\s+E\s+X\s+I\s+T\s\* |
   +-----------------------------------+-----------------------------------+
   | offset                            | -10                               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | dirac/dirac.xml                   |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

                
    *******************************************************************************
    *                                                                             *
    *  -------------------------------------                                      *
    *   Amsterdam Density Functional  (ADF)         2007.01   August 20, 2007     *
    *  -------------------------------------                                      *
    *                                               Build 200708201257            *
    *                                                                             *
    *                                                                             *
    *                            =====================                            *
    *                            |                   |                            *
    *                            |     D I R A C     |                            *
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
    ****************************  pentium_linux_ifc  ******************************

    DIRAC 2007.01  RunTime: Oct17-2008 16:16:47

   ...

    *******************************************************************************

                                D I R A C   E X I T             
       

**Template definition.**

.. code:: xml

   <templateList>  <xi:include href="../program.header.xml" />
           </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
