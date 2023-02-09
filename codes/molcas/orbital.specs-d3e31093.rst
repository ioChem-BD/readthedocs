.. _orbital.specs-d3e31093:

orbital.specs
=============

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
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | orbital.specs                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Orbital specifications                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | .*Orbital&#92;sspecifications&#92;s*:&#92;s\*                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;-&#92;-&#92;s\*                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | .*[0-9]+$&#92;s\*                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/orbital.specs.xml                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   ++    Orbital specifications:
         -----------------------
    
         Symmetry species               1
                                        a
         Frozen orbitals                0
         Occupied orbitals             16
         Secondary orbitals            28
         Deleted orbitals               0
         Total number of orbitals      44
         Number of basis functions     44
   --
       
       

.. container:: formalpara-title

   **Input**

::

        Orbital specifications :
         Symmetry species               1   2
                                        a   b
         Frozen orbitals                0   0
         Aufbau                        52
         Start temperature = 0.500
         End temperature   = 0.010
         Temperature Factor= 0.460
         Deleted orbitals               0   0
         Total number of orbitals      72  70
         Number of basis functions     72  70
         
       

.. container:: formalpara-title

   **Input**

::

   ++       Orbital specifications:
         -----------------------

         Symmetry species                           1   2
                                                    a   b
         Frozen orbitals                            0   0
         Inactive orbitals                         27  24
         Active orbitals                            2   0
         RAS1 orbitals                              0   0
         RAS2 orbitals                              2   0
         RAS3 orbitals                              0   0
         Secondary orbitals                        91  92
         Deleted orbitals                           0   0
         Number of basis functions                120 116

   --
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="orbital.specs">
            <module cmlx:templateRef="orbital.specs">
               <array dataType="xsd:integer" dictRef="m:symserial" size="1">1</array>
               <array dataType="xsd:string" dictRef="m:symlabel" size="1">a</array>
               <array dataType="xsd:integer" dictRef="m:frozenorb" size="1">0</array>
               <array dataType="xsd:integer" dictRef="m:occuporb" size="1">16</array>
               <array dataType="xsd:integer" dictRef="m:secondaryorb" size="1">28</array>
               <array dataType="xsd:integer" dictRef="m:deletedorb" size="1">0</array>
               <array dataType="xsd:integer" dictRef="m:orbno" size="1">44</array>
               <array dataType="xsd:integer" dictRef="m:basisno" size="1">44</array>
            </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="orbital.specs2">
           <module cmlx:templateRef="orbital.specs">
               <array dataType="xsd:integer" dictRef="m:symserial" size="2">1 2</array>
               <array dataType="xsd:string" dictRef="m:symlabel" size="2">a b</array>
               <array dataType="xsd:integer" dictRef="m:frozenorb" size="2">0 0</array>
               <module cmlx:templateRef="aufbau">
                  <scalar dataType="xsd:double" dictRef="m:tempstart">0.500</scalar>
                  <scalar dataType="xsd:double" dictRef="m:tempend">0.010</scalar>
                  <scalar dataType="xsd:double" dictRef="m:tempfactor">0.460</scalar>
               </module>
               <array dataType="xsd:integer" dictRef="m:deletedorb" size="2">0 0</array>
               <array dataType="xsd:integer" dictRef="m:orbno" size="2">120 116</array>
               <array dataType="xsd:integer" dictRef="m:basisno" size="2">120 116</array>
            </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="orbital.specs3">
            <module cmlx:templateRef="orbital.specs">
               <array dataType="xsd:integer" dictRef="m:symserial" size="2">1 2</array>
               <array dataType="xsd:string" dictRef="m:symlabel" size="2">a b</array>
               <array dataType="xsd:integer" dictRef="m:frozenorb" size="2">0 0</array>
               <array dataType="xsd:integer" dictRef="m:inactiveorb" size="2">27 24</array>
               <array dataType="xsd:integer" dictRef="m:activeorb" size="2">2 0</array>
               <array dataType="xsd:integer" dictRef="m:ras1orb" size="2">0 0</array>
               <array dataType="xsd:integer" dictRef="m:ras2orb" size="2">2 0</array>
               <array dataType="xsd:integer" dictRef="m:ras3orv" size="2">0 0</array>
               <array dataType="xsd:integer" dictRef="m:secondaryorb" size="2">91 92</array>
               <array dataType="xsd:integer" dictRef="m:deletedorb" size="2">0 0</array>
               <array dataType="xsd:integer" dictRef="m:basisno" size="2">120 116</array>
            </module>    
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern="\s*Symmetry\sspecies.*" endPattern="\s*Frozen.*" endPattern2="~">    <record>\s*Symmetry\sspecies{1_20I,m:symserial}</record>    <record>{1_20A,m:symlabel}</record>
           </template>  <template pattern="\s*Frozen\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Frozen\sorbitals{1_20I,m:frozenorb}</record>
           </template>  <template pattern="\s*Occupied\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Occupied\sorbitals{1_20I,m:occuporb}</record>
           </template>  <template pattern="\s*Inactive\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Inactive\sorbitals{1_20I,m:inactiveorb}</record>
           </template>  <template pattern="\s*Active\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Active\sorbitals{1_20I,m:activeorb}</record>
           </template>  <template pattern="\s*RAS1\sorbitals.*" endPattern="\s*Secondary.*">    <record>\s*RAS1\sorbitals{1_20I,m:ras1orb}</record>    <record>\s*RAS2\sorbitals{1_20I,m:ras2orb}</record>    <record>\s*RAS3\sorbitals{1_20I,m:ras3orv}</record>
           </template>  <template pattern="\s*Secondary\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Secondary\sorbitals{1_20I,m:secondaryorb}</record>
           </template>  <template pattern="\s*Deleted\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Deleted\sorbitals{1_20I,m:deletedorb}</record>
           </template>  <template pattern="\s*Number\sof\sbasis\sfunctions.*" endPattern=".*" endPattern2="~">    <record>\s*Number\sof\sbasis\sfunctions{1_20I,m:basisno}</record>    
           </template>  <template pattern="\s*Total\snumber\sof\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Total\snumber\sof\sorbitals{1_20I,m:orbno}</record>
           </template>  <template id="aufbau" pattern="\s*Aufbau.*" endPattern="\s*Temperature.*" endPattern2="~" endOffset="1">    <record>\s*Aufbau{1_20I,m:aufbau}</record>    <record>\s*Start\stemperature\s*={F,m:tempstart}</record>    <record>\s*End\stemperature\s*={F,m:tempend}</record>    <record>\s*Temperature\sFactor\s*={F,m:tempfactor}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list" />
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:array" repeat="2" />
   <transform process="delete" xpath=".//cml:module[not(@cmlx:templateRef='aufbau')]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
