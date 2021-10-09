.. _mulliken.header-d3e22361:

mulliken.header
===============

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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | mulliken.header                   |
   +-----------------------------------+-----------------------------------+
   | name                              | Mulliken (spin) population        |
   |                                   | Analysis header                   |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Mulliken\                     |
   |                                   | s(spin\s)?population\sAnalysis.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | mod                               |
   |                                   | ules/mulliken/mulliken.header.xml |
   +-----------------------------------+-----------------------------------+

**Input.**

::

         Mulliken spin population Analysis for root number: 1
       

**Input.**

::

         Mulliken population Analysis for root number: 1
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="mulliken.header">
           <module cmlx:templateRef="mulliken.header">
               <scalar dataType="xsd:integer" dictRef="m:rootnumber">1</scalar>
           </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="mulliken.header2">
           <module cmlx:templateRef="mulliken.header">
               <scalar dataType="xsd:integer" dictRef="m:rootnumber">1</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="mullikenroot" pattern="\s*Mulliken\spopulation\sAnalysis\sfor\sroot\snumber.*" endPattern="~">    <record>\s*Mulliken\spopulation\sAnalysis\sfor\sroot\snumber:{I,m:rootnumber}</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="2" />                             
           </template>  <template id="mullikenroot" pattern="\s*Mulliken\sspin\spopulation\sAnalysis\sfor\sroot\snumber.*" endPattern="~">    <record>\s*Mulliken\s{A,m:mullikentype}\spopulation\sAnalysis\sfor\sroot\snumber:{I,m:rootnumber}</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="2" />                  
           </template>
       </templateList>
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
