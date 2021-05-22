.. _enthalpy-d3e27736:

enthalpy
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
   | id                                | enthalpy                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Enthalpy section                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{5,}\s*$\s*ENTHALPY\s\*      |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Total\sEnthalpy.\*            |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/enthalpy.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   --------
   ENTHALPY
   --------

   The enthalpy is H = U + kB*T
                   kB is Boltzmann's constant
   Total free energy                 ...   -228.86048127 Eh
   Thermal Enthalpy correction       ...      0.00094421 Eh       0.59 kcal/mol
   -----------------------------------------------------------------------
   Total Enthalpy                    ...   -228.85953707 Eh    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="enthalpy">
           <module cmlx:templateRef="enthalpy">
               <scalar dataType="xsd:double" dictRef="o:totalfree" units="nonsi:hartree">-228.86048127</scalar>
               <scalar dataType="xsd:double" dictRef="o:thermalcorrenthalpy" units="nonsi:hartree">0.00094421</scalar>
               <scalar dataType="xsd:double" dictRef="o:totalenthalpy" units="nonsi:hartree">-228.85953707</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="6" />
   <record>\s*Total\sfree\senergy\s*\.\.\.{F,o:totalfree}.*</record>
   <record>\s*Thermal\sEnthalpy\scorrection\s*\.\.\.{F,o:thermalcorrenthalpy}.*</record>
   <record />
   <record>\s*Total\sEnthalpy\s*\.\.\.{F,o:totalenthalpy}.*</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
