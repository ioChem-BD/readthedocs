.. _dipole-d3e36908:

dipole
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
   | *source*                          | VASP outcar                       |
   +-----------------------------------+-----------------------------------+
   | id                                | dipole                            |
   +-----------------------------------+-----------------------------------+
   | name                              | Dipole corrections                |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Dipole\scorrections.\*        |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | incar/dipole.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Dipole corrections
      LMONO  =      F    monopole corrections only (constant potential shift)
      LDIPOL =      T    correct potential (dipole corrections)
      IDIPOL =      3    1-x, 2-y, 3-z, 4-all directions 
      EPSILON=  1.0000000 bulk dielectric constant
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="dipole">
           <module cmlx:templateRef="dipole">
               <module>
                   <list cmlx:templateRef="missingID">
                       <scalar dataType="xsd:string" dictRef="v:ldipol">T</scalar>
                   </list>
               </module>
               <module>
                   <list cmlx:templateRef="missingID">
                       <scalar dataType="xsd:integer" dictRef="v:idipol">3</scalar>
                   </list>
               </module>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*LDIPOL.*" endPattern=".*" endPattern2="~">    <record>\s*LDIPOL\s*={A,v:ldipol}.*</record> 
           </template>  <template pattern="\s*IDIPOL.*" endPattern=".*" endPattern2="~">    <record>\s*IDIPOL\s*={I,v:idipol}.*</record> 
           </template>
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
