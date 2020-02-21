.. _atomicchargesspin-d3e26920:

atomicchargesspin
=================

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
   | id                                | atomicchargesspin                 |
   +-----------------------------------+-----------------------------------+
   | name                              | Atomic charges and spin           |
   |                                   | populations                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{10,}\s*$\s                  |
   |                                   | *MULLIKEN\sATOMIC\sCHARGES\sAND\s |
   |                                   | SPIN\s(POPULATIONS|DENSITIES)\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | ((?!-{10,}).)*$\s\*               |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | mulliken/atomicchargesspin.xml    |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   --------------------------------------------
   MULLIKEN ATOMIC CHARGES AND SPIN POPULATIONS
   --------------------------------------------
      0 Cu:    0.478119    0.653774
      1 Cu:    0.478120    0.653775
      2 N :   -0.302401    0.087069
      3 N :   -0.302401    0.087069
      4 N :   -0.302401    0.087069
      5 N :   -0.302400    0.087068
      6 N :    0.315931   -0.004557
      7 N :    0.315930   -0.004556
      8 N :   -0.477804    0.093879
      9 N :   -0.477804    0.093879
     10 N :   -0.477804    0.093879
     11 N :   -0.477804    0.093879
     12 N :   -0.596140    0.000645
     13 N :   -0.596140    0.000645
     14 H :    0.268504   -0.001631
     15 H :    0.268504   -0.001631
     16 H :    0.268504   -0.001631
     17 H :    0.268504   -0.001631
     18 H :    0.244541   -0.001710
     19 H :    0.244541   -0.001710
     20 H :    0.244541   -0.001710
     21 H :    0.244541   -0.001710
     22 H :    0.283635   -0.002300
     23 H :    0.283635   -0.002300
     24 H :    0.283635   -0.002300
     25 H :    0.283635   -0.002300
     26 H :    0.243730   -0.000125
     27 H :    0.243730   -0.000125
     28 H :    0.262705   -0.000176
     29 H :    0.262705   -0.000176
     30 H :    0.262704   -0.000176
     31 H :    0.262704   -0.000176
   Sum of atomic charges         :    2.0000000
   Sum of atomic spin populations:    2.0000000

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="atomicchargesspin">
            <module cmlx:templateRef="atomicchargesspin">
               <scalar dataType="xsd:double" dictRef="x:chargesum">2.0000000</scalar>
               <scalar dataType="xsd:double" dictRef="x:spinsum">-0.0000000</scalar>
               <array dataType="xsd:integer" dictRef="cc:serial" size="32">0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31</array>
               <array dataType="xsd:string" dictRef="cc:elementType" size="32">Cu Cu N N N N N N N N N N N N H H H H H H H H H H H H H H H H H H</array>
               <array dataType="xsd:double" dictRef="x:charge" size="32">0.469289 0.469287 -0.292692 -0.292691 -0.292694 -0.292694 0.318542 0.318540 -0.481730 -0.481730 -0.481730 -0.481730 -0.597426 -0.597426 0.267790 0.267790 0.267790 0.267790 0.244233 0.244233 0.244233 0.244233 0.282636 0.282636 0.282636 0.282636 0.244402 0.244402 0.262360 0.262360 0.262360 0.262360</array>
               <array dataType="xsd:double" dictRef="x:spin" size="32">0.618178 -0.618177 -0.023799 -0.023800 0.023799 0.023798 -0.000000 0.000002 0.087450 0.087450 -0.087450 -0.087450 0.000640 -0.000640 -0.001574 -0.001574 0.001574 0.001574 -0.001593 -0.001593 0.001593 0.001593 -0.002201 -0.002201 0.002201 0.002201 -0.000074 0.000074 -0.000080 -0.000080 0.000080 0.000080</array>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="3" />
   <record repeat="*" makeArray="true">{I,cc:serial}{A,cc:elementType}:{F,x:charge}{F,x:spin}</record>
   <record>\s*Sum\sof\satomic\scharges\s*:{F,x:chargesum}</record>
   <record>\s*Sum\sof\satomic\sspin\spopulations\s*:{F,x:spinsum}</record>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
