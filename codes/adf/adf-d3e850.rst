adf
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/adf/program.header-d3e857
   /codes/adf/model.parameters-d3e977
   /codes/adf/adf.runtype-d3e1534
   /codes/adf/adf.build-d3e1991
   /codes/adf/adf.technical-d3e1997
   /codes/adf/adf.computation-d3e2003
   /codes/adf/adf.results-d3e2480
   /codes/adf/adf.frequencyanalysis-d3e3989

===

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
   | id                                | adf                               |
   +-----------------------------------+-----------------------------------+
   | name                              | ADF module                        |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \                                 |
   |                                   | \s+\*\s+\|\s+A\sD\sF\s+\|\s+\*.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*A\s+D\s+F\s+E\s+X\s+I\s+T\s\* |
   +-----------------------------------+-----------------------------------+
   | offset                            | -10                               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | adf/adf.xml                       |
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
    *                              =================                              *
    *                              |               |                              *
    *                              |     A D F     |                              *
    *                              |               |                              *
    *                              =================                              *
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
    
    ADF 2007.01  RunTime: Oct17-2008 16:16:48
    Oxygen (TZP, 1s frozen)
   ...

   (INIT)
   ...
    
                                         ************************************
                                         *  R U N   T Y P E : SINGLE POINT  *
                                         ************************************
   ...
                                         *********************************************
                                         *  R U N   T Y P E : GEOMETRY OPTIMIZATION  *
                                         *********************************************
   ...
                                         ****************************************
                                         *  B U I L D : (Fragments, Functions)  *
                                         ****************************************
   ...
                                         ***********************
                                         *  T E C H N I C A L  *
                                         ***********************
   ...
                                         ***************************
                                         *  C O M P U T A T I O N  *
                                         ***************************
   ...
                                         *******************
                                         *  R E S U L T S  *
                                         *******************
   ...                                      
                                         ******************************************
                                         *  F R E Q U E N C Y    A N A L Y S I S  *
                                         ******************************************

    *******************************************************************************

                                A D F   E X I T        
       

**Template definition.**

.. code:: xml

   <templateList>  <xi:include href="../program.header.xml" />  <xi:include href="init/modelparameters/model.parameters.xml" />  <xi:include href="runtype/runtype.xml" />  <xi:include href="build/build_fragments.xml" />  <xi:include href="technical/technical.xml" />  <xi:include href="computation/computation.xml" />  <xi:include href="results/results.xml" />  <xi:include href="frequencyanalysis/frequencyanalysis.xml" />       
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
