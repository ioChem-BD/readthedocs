.. _lattice-d3e50189:

lattice
=======

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image2|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | VASP outcar                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | lattice                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Lattice vectors                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*direct&#92;slattice&#92;svectors&#92;s*reciprocal&#92;slattice&#92;svectors.\*                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | position/lattice.xml                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         direct lattice vectors                 reciprocal lattice vectors
       13.011000000  0.000000000  0.000000000     0.076858043  0.000000000  0.000000000
        0.000000000 13.011000000  0.000000000     0.000000000  0.076858043  0.000000000
        0.000000000  0.000000000 19.337000000     0.000000000  0.000000000  0.051714330
       
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="lattice">
           <module cmlx:templateRef="lattice">
               <array dataType="xsd:double" dictRef="cc:lattice" size="3">13.011000000 0.000000000 0.000000000</array>
               <array dataType="xsd:double" dictRef="cc:lattice" size="3">0.000000000 13.011000000 0.000000000</array>
               <array dataType="xsd:double" dictRef="cc:lattice" size="3">0.000000000 0.000000000 19.337000000</array>
           </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*direct\slattice\svectors\s*reciprocal\slattice\svectors.*" endPattern="~">    <record repeat="1" />    <record>{3F,cc:lattice}.*</record>    <record>{3F,cc:lattice}.*</record>    <record>{3F,cc:lattice}.*</record>    <transform process="pullup" xpath=".//cml:array" repeat="2" />                               
           </template>   
       </templateList>
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
