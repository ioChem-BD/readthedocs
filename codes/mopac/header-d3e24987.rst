.. _header-d3e24987:

header
======

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
   | *source*                          | MOPAC log                         |
   +-----------------------------------+-----------------------------------+
   | id                                | header                            |
   +-----------------------------------+-----------------------------------+
   | name                              | MOPAC header                      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s?\*+\s?$\s?\*+\s?Site#.\*      |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | header.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    *******************************************************************************
    ** Site#: 24836        For non-commercial use only     Version 16.093L 64BITS**
    *******************************************************************************
    ** Cite this program as: MOPAC2016, Version: 16.093L, James J. P. Stewart,   **
    ** Stewart Computational Chemistry, web: HTTP://OpenMOPAC.net. Days left:  87**
    *******************************************************************************
    **                                                                           **
    **                                MOPAC2016                                  **
    **                                                                           **
    *******************************************************************************

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="header">
           <module cmlx:templateRef="header">
             <scalar dataType="xsd:string" dictRef="cc:programSubversion">16.093L 64BITS</scalar>
             <scalar dataType="xsd:string" dictRef="cc:programVersion">2016</scalar>
          </module>     
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="programLine1" pattern=".*Version.*" endPattern=".*">    <record>.*Version\s+{X,cc:programSubversion}\*\*</record>         
           </template>  <template id="programLine2" pattern="\s?\*\*\s+MOPAC.*" endPattern=".*">    <record>\s?\*\*\s+MOPAC{X,cc:programVersion}\s*\*\*</record>           
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
