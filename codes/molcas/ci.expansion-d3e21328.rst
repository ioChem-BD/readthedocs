.. _ci.expansion-d3e21328:

ci.expansion
============

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
   | id                                | ci.expansion                      |
   +-----------------------------------+-----------------------------------+
   | name                              | CI expansion specifications       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | .                                 |
   |                                   | *CI\sexpansion\sspecifications.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .*[0-9]$\s*(\-\-)?\s\*            |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/ci/ci.expansion.xml       |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        CI expansion specifications:
         ----------------------------
    
         Number of configuration state fnc.        10
         Number of determinants                    10
         Number of root(s) required                 7
         Root chosen for geometry opt.              7
         CI roots used                              1     2     3     4     5     6     7
         weights                                0.143 0.143 0.143 0.143 0.143 0.143 0.143
         highest root included in the CI            7
         max. size of the explicit Hamiltonian     10
    

**Input.**

::

         CI expansion specifications:
         ----------------------------

         Number of configuration state fnc.      1764
         Number of determinants                  2485
         Number of root(s) required                 1
         CI root used                               1
         highest root included in the CI            1
         Root passed to geometry opt.               1

**Output text.**

.. code:: xml

   <comment class="example.output" id="ci.expansion">
       <module cmlx:templateRef="ci.expansion">
           <scalar dataType="xsd:integer" dictRef="m:conffnc">10</scalar>
           <scalar dataType="xsd:integer" dictRef="m:determinants">10</scalar>
           <scalar dataType="xsd:integer" dictRef="m:requiredroot">7</scalar>
           <scalar dataType="xsd:integer" dictRef="m:chosenroot">7</scalar>
           <array dataType="xsd:integer" dictRef="m:ciroots" size="7">1 2 3 4 5 6 7</array>
           <array dataType="xsd:double" dictRef="m:rootweight" size="7">0.143 0.143 0.143 0.143 0.143 0.143 0.143</array>
           <scalar dataType="xsd:integer" dictRef="m:highestroot">7</scalar>
           <scalar dataType="xsd:integer" dictRef="m:maxsizehamilt">10</scalar>
        </module>
     </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="ci.expansion2">     
         <module cmlx:templateRef="ci.expansion">
            <scalar dataType="xsd:integer" dictRef="m:conffnc">1764</scalar>
            <scalar dataType="xsd:integer" dictRef="m:determinants">2485</scalar>
            <scalar dataType="xsd:integer" dictRef="m:requiredroot">1</scalar>
            <array dataType="xsd:integer" dictRef="m:ciroots" size="1">1</array>
            <scalar dataType="xsd:integer" dictRef="m:highestroot">1</scalar>
            <scalar dataType="xsd:integer" dictRef="m:passedroot">1</scalar>
         </module>
     </comment>

**Template definition.**

.. code:: xml

   <template pattern="\s*Number\sof\sconfiguration\sstate\sfnc..*" endPattern=".*" endPattern2="~">  <record>\s*Number\sof\sconfiguration\sstate\sfnc.{I,m:conffnc}</record> 
       </template>
   <template pattern="\s*Number\sof\sdeterminants.*" endPattern=".*" endPattern2="~">  <record>\s*Number\sof\sdeterminants{I,m:determinants}</record>    
       </template>
   <template pattern="\s*Number\sof\sroot\(s\)\srequired.*" endPattern=".*" endPattern2="~">  <record>\s*Number\sof\sroot\(s\)\srequired{I,m:requiredroot}</record>  
       </template>
   <template pattern="\s*Root\schosen\sfor\sgeometry\sopt..*" endPattern=".*" endPattern2="~">  <record>\s*Root\schosen\sfor\sgeometry\sopt.{I,m:chosenroot}</record>    
       </template>
   <template pattern="\s*CI\sroots?\sused.*" endPattern=".*" endPattern2="~">  <record>\s*CI\sroots?\sused{1_30I,m:ciroots}</record>             
       </template>
   <template pattern="\s*weights.*" endPattern=".*" endPattern2="~">  <record>\s*weights{1_30F,m:rootweight}</record>
       </template>
   <template pattern="\s*highest\sroot\sincluded\sin\sthe\sCI.*" endPattern=".*" endPattern2="~">  <record>\s*highest\sroot\sincluded\sin\sthe\sCI{I,m:highestroot}</record>
       </template>
   <template pattern="\s*max.\ssize\sof\sthe\sexplicit\sHamiltonian.*" endPattern=".*" endPattern2="~">  <record>\s*max.\ssize\sof\sthe\sexplicit\sHamiltonian{I,m:maxsizehamilt}</record>
       </template>
   <template pattern="\s*Root\spassed\sto\sgeometry\sopt.*" endPattern=".*" endPattern2="~">  <record>\s*Root\spassed\sto\sgeometry\sopt\.{I,m:passedroot}</record>  
       </template>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="pullup" xpath=".//cml:array" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
