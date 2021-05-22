.. _lattice-d3e37232:

lattice
=======

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
   | id                                | lattice                           |
   +-----------------------------------+-----------------------------------+
   | name                              | Lattice vectors                   |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*direct\slattice\svectors\     |
   |                                   | s*reciprocal\slattice\svectors.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\w+.*$\s\*                    |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | position/lattice.xml              |
   +-----------------------------------+-----------------------------------+

**Input.**

::

         direct lattice vectors                 reciprocal lattice vectors
       13.011000000  0.000000000  0.000000000     0.076858043  0.000000000  0.000000000
        0.000000000 13.011000000  0.000000000     0.000000000  0.076858043  0.000000000
        0.000000000  0.000000000 19.337000000     0.000000000  0.000000000  0.051714330
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="lattice">
           <module cmlx:templateRef="lattice">
               <array dataType="xsd:double" dictRef="cc:lattice" size="3">13.011000000 0.000000000 0.000000000</array>
               <array dataType="xsd:double" dictRef="cc:lattice" size="3">0.000000000 13.011000000 0.000000000</array>
               <array dataType="xsd:double" dictRef="cc:lattice" size="3">0.000000000 0.000000000 19.337000000</array>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*direct\slattice\svectors\s*reciprocal\slattice\svectors.*" endPattern="~">    <record repeat="1" />    <record>{3F,cc:lattice}.*</record>    <record>{3F,cc:lattice}.*</record>    <record>{3F,cc:lattice}.*</record>    <transform process="pullup" xpath=".//cml:array" repeat="2" />                               
           </template>   
       </templateList>
   <transform process="delete" xpath="./cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
