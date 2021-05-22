.. _zero.point.energy-d3e36257:

zero.point.energy
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
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | zero.point.energy                 |
   +-----------------------------------+-----------------------------------+
   | name                              | Zero point vibration energy       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\*{20,}\s*$\s*\*.*$\s*\*\s+ze |
   |                                   | ro\spoint\sVIBRATIONAL\senergy.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\*{20,}\s\*                   |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | zero.point.energy.xml             |
   +-----------------------------------+-----------------------------------+

**Input.**

::

         **************************************************************
         *                                                            *
         *  zero point VIBRATIONAL energy  :      0.0598644  Hartree  *
         *    SCF-energy                   :   -228.9336374           *
         *    SCF + E(vib0)                :   -228.8737730           *
         *                                                            *
         **************************************************************
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="zero.point.energy">
           <module cmlx:templateRef="zero.point.energy">
               <scalar dataType="xsd:double" dictRef="t:zeropoint" units="nonsi:hartree">0.0598644</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="2" />
   <record>\s*\*\s*zero\spoint\sVIBRATIONAL\senergy\s+:{F,t:zeropoint}Hartree.*</record>
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath="./cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
