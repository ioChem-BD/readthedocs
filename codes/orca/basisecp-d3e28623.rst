.. _basisecp-d3e28623:

basisecp
========

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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | basisecp                          |
   +-----------------------------------+-----------------------------------+
   | name                              | ECP Parameter Information         |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{20}.*$                      |
   |                                   | \s*ECP\sPARAMETER\sINFORMATION.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Atom.*$\s\*                   |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*$\s*-{20}.\*                  |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | \\s*$\s\*                         |
   +-----------------------------------+-----------------------------------+
   | endPattern4                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/basisecp.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   -------------------------
   ECP PARAMETER INFORMATION
   -------------------------

    Group 1, Type Ru ECP SD(28,MWB) (replacing 28 core electrons, lmax=4)

   Atom   0Ru   ECP group =>   1
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="basisecp">
           <module cmlx:templateRef="basisecp">
               <module cmlx:templateRef="basisgroups">
                  <list cmlx:templateRef="group">
                     <list>
                        <scalar dataType="xsd:integer" dictRef="o:group">1</scalar>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Ru</scalar>
                        <scalar dataType="xsd:string" dictRef="o:ecptype">ECP SD(28,MWB)</scalar>
                     </list>
                  </list>
               </module>
               <module cmlx:templateRef="atombasis">
                  <list cmlx:templateRef="missingID">
                     <list>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">0</scalar>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Ru</scalar>
                        <scalar dataType="xsd:integer" dictRef="o:group">1</scalar>
                     </list>
                  </list>
               </module>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="basisgroups" pattern="\s*Group.*" endPattern="\s*" endPattern2="~">    <record id="group" repeat="*">\s*Group{I,o:group},\s*Type{A,cc:elementType}{X,o:ecptype}\(replacing.*</record>
           </template>  <template id="atombasis" pattern="\s*Atom.*" endPattern=".*" endPattern2="~" repeat="*">    <record repeat="*">\s*Atom{I,cc:serial}{A,cc:elementType}ECP\sgroup\s=>{I,o:group}</record>
           </template>
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
