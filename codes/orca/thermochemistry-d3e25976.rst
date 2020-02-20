.. _thermochemistry-d3e25976:

thermochemistry
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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | thermochemistry                   |
   +-----------------------------------+-----------------------------------+
   | name                              | Thermochemistry section           |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\-+\s                         |
   |                                   | *$\s*THERMOCHEMISTRY.*$\s*\-+\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s\*                         |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*freq.*$\s\*                   |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | thermochemistry.xml               |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   --------------------------
   THERMOCHEMISTRY AT 298.15K
   --------------------------

   Temperature         ... 298.15 K
   Pressure            ... 1.00 atm
   Total Mass          ... 248.32 AMU

   Throughout the following assumptions are being made:
     (1) The electronic state is orbitally nondegenerate
     (2) There are no thermally accessible electronically excited states
     (3) Hindered rotations indicated by low frequency modes) are not
         treated as such but are treated as vibrations and this may
         case some error
     (4) All equations used are the standard statistical mechanics
         equations for an ideal gas
     (5) All vibrations are strinctly harmonic


       

**Output text.**

.. code:: xml

   <comment class="example.output" id="thermochemistry">
         <module cmlx:templateRef="thermochemistry">
            <scalar dataType="xsd:double" dictRef="cc:temp" units="si:k">298.15</scalar>
            <scalar dataType="xsd:double" dictRef="cc:press" units="nonsi:atm">1.00</scalar>
            <scalar dataType="xsd:double" dictRef="cc:totalmass">248.32</scalar>
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="4" />
   <record>\s*Temperature\s*\.\.\.{F,cc:temp}.*</record>
   <record>\s*Pressure\s*\.\.\.{F,cc:press}.*</record>
   <record>\s*Total\sMass\s*\.\.\.{F,cc:totalmass}.*</record>
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:temp']" value="si:k" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:press']" value="nonsi:atm" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:mass']" value="nonsi:dalton" />
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
