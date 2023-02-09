.. _bonding.energy-d3e3763:

bonding.energy
==============

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
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | bonding.energy                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Bonding energy section                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*B&#92;sO&#92;sN&#92;sD&#92;sI&#92;sN&#92;sG&#92;s+E&#92;sN&#92;sE&#92;sR&#92;sG&#92;sY.\*                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*$&#92;s*&#92;={5,}+.\*                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | results/bonding.energy.xml                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    ===========================
    B O N D I N G   E N E R G Y  ***  (decomposition)  ***
    ===========================

   *** WARNING ***

   The bond energy is computed as an energy difference between molecule and
   fragments. In particular when the fragments are single atoms, they are usually
   computed as SPHERICALLY SYMMETRIC and SPIN-RESTRICTED. Obviously, this usually
   does NOT represent the true atomic groundstate.
   ...

   Summary of Bonding Energy (energy terms are taken from the energy decomposition above)
   ======================================================================================

     Electrostatic Energy:            -33.475567726025723       -910.9165        -21006.24        -87890.09
     Kinetic Energy:                   24.937087958477719        678.5727         15648.26         65472.32
     Coulomb (Steric+OrbInt) Energy:    8.680505521299182        236.2086          5447.10         22790.66
     XC Energy:                       -27.291167088981922       -742.6304        -17125.47        -71652.95
     Solvation:                        -0.008061655700173         -0.2194            -5.06           -21.17
     Dispersion Energy:                -0.128691164634089         -3.5019           -80.75          -337.88
     Spin-Orbit:                       -0.149130118381270         -4.0580           -93.58          -391.54
                                     --------------------     -----------       ----------      -----------
     Total Bonding Energy:            -27.149141335230745       -738.7657        -17036.35        -71280.06

    ...

       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="bonding.energy">
        <module cmlx:templateRef="bonding.energy">
         <scalar dataType="xsd:double" dictRef="cc:eener" units="nonsi:electronvolt">-910.9165</scalar>
         <scalar dataType="xsd:double" dictRef="cc:kinener" units="nonsi:electronvolt">678.5727</scalar>
         <scalar dataType="xsd:double" dictRef="cc:coulombener" units="nonsi:electronvolt">236.2086</scalar>
         <scalar dataType="xsd:double" dictRef="cc:xcener" units="nonsi:electronvolt">-742.6304</scalar>
         <scalar dataType="xsd:double" dictRef="cc:solvener" units="nonsi:electronvolt">-0.2194</scalar>
         <scalar dataType="xsd:double" dictRef="cc:dispener" units="nonsi:electronvolt">-3.5019</scalar>
         <scalar dataType="xsd:double" dictRef="cc:spinener" units="nonsi:electronvolt">-4.058</scalar>
         <scalar dataType="xsd:double" dictRef="cc:total" units="nonsi:electronvolt">-738.7657</scalar>
        </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="summary" pattern="\s*Summary\sof\sBonding\sEnergy.*" endPattern="\s*Total\sBonding\sEnergy.*" endOffset="1">    <templateList>      <template pattern="\s*Electrostatic\sEnergy.*" endPattern=".*" endOffset="0">        <record id="electrostatic">.*:\s+\S+\s*{F,cc:eener}.*</record>                   
                   </template>      <template pattern="\s*Kinetic\sEnergy.*" endPattern=".*" endOffset="0">        <record id="kinener">.*:\s+\S+\s*{F,cc:kinener}.*</record>                  
                   </template>      <template pattern="\s*Coulomb.*" endPattern=".*" endOffset="0">        <record id="coulomb">.*:\s+\S+\s*{F,cc:coulombener}.*</record>                                  
                   </template>      <template pattern="\s*XC\sEnergy.*" endPattern=".*" endOffset="0">        <record id="xc">.*:\s+\S+\s*{F,cc:xcener}.*</record>                                 
                   </template>      <template pattern="\s*Solvation.*" endPattern=".*" endOffset="0">        <record id="solvation">.*:\s+\S+\s*{F,cc:solvener}.*</record>                                 
                   </template>      <template pattern="\s*Dispersion\sEnergy.*" endPattern=".*" endOffset="0">        <record id="dispersion">.*:\s+\S+\s*{F,cc:dispener}.*</record>                                   
                   </template>      <template pattern="\s*Spin\-Orbit.*" endPattern=".*" endOffset="0">        <record id="spin">.*:\s+\S+\s*{F,cc:spinener}.*</record>                                    
                   </template>      <template pattern="\s*Total\s*Bonding\s*Energy.*" endPattern=".*" endPattern2="~" endOffset="0">        <record id="total">.*:\s+\S+\s*{F,cc:total}.*</record>
                   </template>               
               </templateList>    <transform process="pullup" repeat="2" xpath=".//cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:module[count(*)=0]" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:electronvolt" />         
           </template>
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
