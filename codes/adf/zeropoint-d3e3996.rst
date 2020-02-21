.. _zeropoint-d3e3996:

zeropoint
=========

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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | zeropoint                         |
   +-----------------------------------+-----------------------------------+
   | name                              | Zero-point energy                 |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Zero-Point\sEnergy.\*         |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | frequencyanalysis/zeropoint.xml   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Zero-Point Energy :      0.500175 a.u.
    ===================     13.610451 eV
    (imaginary frequencies were excluded from the summation) 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="zeropoint"> 
           <module cmlx:lineCount="3" cmlx:templateRef="zeropoint">
               <scalar dataType="xsd:double" dictRef="cc:zeropoint" units="nonsi:electronvolt">13.610451</scalar> 
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="1" />
   <record id="zeropoint">\s*={10,}+\s*{F,cc:zeropoint}eV.*</record>
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:zeropoint']" value="nonsi:electronvolt" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
