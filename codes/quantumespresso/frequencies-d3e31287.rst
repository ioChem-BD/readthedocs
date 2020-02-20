.. _frequencies-d3e31287:

frequencies
===========

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
   | *source*                          | QuantumEspresso log               |
   +-----------------------------------+-----------------------------------+
   | id                                | frequencies                       |
   +-----------------------------------+-----------------------------------+
   | name                              | Frequencies                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\*{10,}\s*$\s*freq\s\(.\*     |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\*{10,}                       |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | ./postprocessings/phonom.xml      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    **************************************************************************
        freq (    1) =      -3.022679 [THz] =    -100.825730 [cm-1]
        freq (    2) =      -1.252407 [THz] =     -41.775805 [cm-1]
        freq (    3) =       0.801352 [THz] =      26.730212 [cm-1]
        freq (    4) =       2.015948 [THz] =      67.244786 [cm-1]
        freq (    5) =       3.401824 [THz] =     113.472642 [cm-1]
        freq (    6) =     129.087361 [THz] =    4305.890869 [cm-1]
    ************************************************************************** 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="frequencies">
         <module cmlx:templateRef="frequencies">
            <array dataType="xsd:string" dictRef="cc:serial" size="6">1 2 3 4 5 6</array>
            <array dataType="xsd:double" dictRef="cc:frequency" size="6" units="nonsi:cm-1">-100.825730 -41.775805 26.730212 67.244786 113.472642 4305.890869</array>
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="1" />
   <record repeat="*" makeArray="true">\s*freq\s*\({X,cc:serial}\).*=\s*{F,cc:frequency}\[cm-1\]\s*</record>
   <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:frequency']" value="nonsi:cm-1" />
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
