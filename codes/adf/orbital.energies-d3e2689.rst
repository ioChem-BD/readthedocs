.. _orbital.energies-d3e2689:

orbital.energies
================

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
   | id                                | orbital.energies                  |
   +-----------------------------------+-----------------------------------+
   | name                              | Orbital Energies, all Irreps      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s+Or                            |
   |                                   | bital\sEnergies,\sall\sIrreps\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | (\s*\S+\s*){5}+\s*$\s\*           |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | results/orbital.energies.xml      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Orbital Energies, all Irreps
    ========================================

    Irrep        no.  (spin)   Occup              E (au)                E (eV)
    ---------------------------------------------------------------------------
    F             1            14.00       -0.36757674632897E+00       -10.0023
    S             1             2.00       -0.17807967614530E+00        -4.8458
    D             1             1.00       -0.65673904079374E-01        -1.7871
    P             1             0.00       -0.21381529425854E-01        -0.5818
    S             2             0.00        0.26879232235995E-01         0.7314
    D             2             0.00        0.59810837659445E-01         1.6275
    S             3             0.00        0.41593031488421E+00        11.3180
    D             3             0.00        0.55856291553914E+00        15.1993
    F             2             0.00        0.12445144510448E+01        33.8650
    F             3             0.00        0.10105604536582E+02       274.9875
    S             4             0.00        0.28122880530536E+04     76526.2516
    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="orbital.energies">
           <module cmlx:lineCount="16" cmlx:templateRef="orbital.energies">
             <list cmlx:lineCount="11" cmlx:templateRef="energies">
               <array dataType="xsd:string" dictRef="cc:irrep" size="11">F S D P S D S D F F S</array>
               <array dataType="xsd:integer" dictRef="cc:serial" size="11">1 1 1 1 2 2 3 3 2 3 4</array>
               <array dataType="xsd:double" dictRef="cc:occup" size="11">14.0 2.0 1.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0</array>
               <array dataType="xsd:double" dictRef="cc:energy" units="nonsi:electronvolt" size="11">-10.0023 -4.8458 -1.7871 -0.5818 0.7314 1.6275 11.318 15.1993 33.865 274.9875 76526.2516</array>
             </list>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="5" />
   <record id="energies" repeat="*" makeArray="true">{A,cc:irrep}{I,cc:serial}{F,cc:occup}\s+\S+\s+{F,cc:energy}</record>
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:energy']" value="nonsi:electronvolt" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
