.. _energy2-d3e36417:

energy2
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
   | id                                | energy2                           |
   +-----------------------------------+-----------------------------------+
   | name                              | Energy section 2                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*d\sForce\s=.\*                |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*d\sForce.*d\sEwald.\*         |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | energy2.xml                       |
   +-----------------------------------+-----------------------------------+

**Input.**

::

       d Force = 0.6233654E-03[ 0.149E-02,-0.247E-03]  d Energy = 0.6368289E-03-0.135E-04
       d Force = 0.2547416E-01[ 0.255E-01, 0.255E-01]  d Ewald  = 0.2547237E-01 0.178E-05  
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="energy2">
           <module cmlx:lineCount="3" cmlx:templateRef="energy2">
               <scalar dataType="xsd:double" dictRef="cc:deltaEnergy" units="nonsi:electronvolt">0.0006368289</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record id="energy">\s*d\sForce\s=.*d\sEnergy\s=\s*{E,cc:deltaEnergy}(\s|-).*</record>
   <record repeat="1" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:deltaEnergy']" value="nonsi:electronvolt" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
