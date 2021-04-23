.. _mixed.ci.coeffs-d3e21447:

mixed.ci.coeffs
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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | mixed.ci.coeffs                   |
   +-----------------------------------+-----------------------------------+
   | name                              | The CI coefficients for the MIXED |
   |                                   | states                            |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*The\sCI\scoeffi               |
   |                                   | cients\sfor\sthe\sMIXED\sstate.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .*[0-9]{4,}\s*$\s\*               |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 2                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/ci/mixed.ci.coeffs.xml    |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

     The CI coefficients for the MIXED state nr.   1
   --------------------------------------------------------------------------------
    CI COEFFICIENTS LARGER THAN  0.50D-01
     Occupation of active orbitals, and spin coupling
     of open shells. (u,d: Spin up or down).
     SGUGA info is (Midvert:IsyUp:UpperWalk/LowerWalk)
      Conf   SGUGA info Occupation       Coef       Weight
         8 ( 2:1:  1/  2)   u20uu          -0.771390         0.595043
        10 ( 2:1:  1/  4)   uduuu           0.306685         0.094056
        12 ( 2:1:  1/  6)   uuduu          -0.177065         0.031352
        13 ( 2:1:  1/  7)   u02uu           0.434433         0.188732
        16 ( 3:1:  2/  1)   uuudu          -0.237319         0.056320
        17 ( 3:1:  3/  1)   uuuud           0.185033         0.034237
    
       

**Input.**

::

     The CI coefficients for the MIXED state nr.   1
   --------------------------------------------------------------------------------
    CI COEFFICIENTS LARGER THAN 0.50D-01
     Occupation of active orbitals, and spin coupling
     of open shells. (u,d: Spin up or down).
      ConfOccupation       Coef       Weight                                       
     
         2    uuu0u           0.184637         0.034091
         3    uu0uu           0.369859         0.136796
         4    u0uuu          -0.716900         0.513946
         5    0uuuu          -0.561385         0.315153

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="ci.coeffs">
            <module cmlx:templateRef="ci.coeffs">
               <scalar dataType="xsd:integer" dictRef="m:mixedstate">1</scalar>
               <array dataType="xsd:integer" dictRef="m:configuration" size="3">2 3 4</array>
               <array dataType="xsd:string" delimiter="|" dictRef="x:value" size="3">uuu0u|uu0uu|u0uuu</array>
               <array dataType="xsd:double" dictRef="m:coeff" size="3">0.184637 0.369859 -0.716900</array>
               <array dataType="xsd:double" dictRef="m:weight" size="3">0.034091 0.136796 0.513946</array>
            </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="ci.coeffs2">
           <module cmlx:templateRef="mixed.ci.coeffs">                
               <scalar dataType="xsd:integer" dictRef="m:mixedstate">1</scalar>
               <array dataType="xsd:integer" dictRef="m:configuration" size="6">8 10 12 13 16 17</array>
               <array dataType="xsd:string" delimiter="|" dictRef="m:sguga" size="6">2:1:  1/  2|2:1:  1/  4|2:1:  1/  6|2:1:  1/  7|3:1:  2/  1|3:1:  3/  1</array>
               <array dataType="xsd:string" delimiter="|" dictRef="x:value" size="6">u20uu|uduuu|uuduu|u02uu|uuudu|uuuud</array>
               <array dataType="xsd:double" dictRef="m:coeff" size="6">-0.771390 0.306685 -0.177065 0.434433 -0.237319 0.185033</array>
               <array dataType="xsd:double" dictRef="m:weight" size="6">0.595043 0.094056 0.031352 0.188732 0.056320 0.034237</array>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*The\sCI\scoefficients\sfor\sthe\sMIXED\sstate\s*nr\.{I,m:mixedstate}</record>
   <template pattern="\s*ConfOccupation\s*Coef\s*Weight.*" endPattern="~">  <record repeat="2" />  <record repeat="*">{I,m:configuration}\s+{X,x:value}\s+{F,m:coeff}\s+{F,m:weight}</record>  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:configuration']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:value']" delimiter="|" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:coeff']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:weight']" />
       </template>
   <template pattern="\s*Conf\s*SGUGA\sinfo\sOccupation\s*Coef\s*Weight.*" endPattern="~" endOffset="1">  <record />  <record repeat="*">{I,m:configuration}\s+\({X,m:sguga}\)\s+{X,x:value}\s+{F,m:coeff}\s+{F,m:weight}</record>  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:sguga']" delimiter="|" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:configuration']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:value']" delimiter="|" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:coeff']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:weight']" />
       </template>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
