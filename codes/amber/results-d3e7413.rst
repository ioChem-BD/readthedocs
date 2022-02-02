.. _results-d3e7413:

results
=======

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
   | *source*                                                                                                                   | Amber log                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | results                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Final results                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*FINAL&#92;s*RESULTS&#92;s\*                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*-{20,}.\*                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/results.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

           FINAL RESULTS



      NSTEP       ENERGY          RMS            GMAX         NAME    NUMBER
      1000      -2.9777E+04     4.2354E-01     1.1992E+01     C20        32

    BOND    =     2111.5836  ANGLE   =       69.3578  DIHED      =       14.1882
    VDWAALS =     4939.8971  EEL     =   -36866.1371  HBOND      =        0.0000
    1-4 VDW =        7.6342  1-4 EEL =      -53.5173  RESTRAINT  =        0.0000
   --------------------------------------------------------------------------------
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="results">
           <module cmlx:templateRef="results">
               <scalar dataType="xsd:double" dictRef="am:step">1000</scalar>
               <scalar dataType="xsd:double" dictRef="am:etot" units="nonsi2:kcal.mol-1">-2.9777E+04</scalar>
               <scalar dataType="xsd:double" dictRef="am:rms">4.2354E-01</scalar>
               <scalar dataType="xsd:double" dictRef="am:gmax">1.1992E+01</scalar>
               <scalar dataType="xsd:double" dictRef="am:bond" units="nonsi2:kcal.mol-1">2111.5836</scalar>
               <scalar dataType="xsd:double" dictRef="am:angle" units="nonsi2:kcal.mol-1">69.3578</scalar>
               <scalar dataType="xsd:double" dictRef="am:dihed" units="nonsi2:kcal.mol-1">14.1882</scalar>
               <scalar dataType="xsd:double" dictRef="am:vdwaals" units="nonsi2:kcal.mol-1">4939.8971</scalar>
               <scalar dataType="xsd:double" dictRef="am:eel" units="nonsi2:kcal.mol-1">-36866.1371</scalar>
               <scalar dataType="xsd:double" dictRef="am:hbond">0.0000</scalar>
               <scalar dataType="xsd:double" dictRef="am:vdw14" units="nonsi2:kcal.mol-1">7.6342</scalar>
               <scalar dataType="xsd:double" dictRef="am:eel14" units="nonsi2:kcal.mol-1">-53.5173</scalar>
               <scalar dataType="xsd:double" dictRef="am:restraint" units="nonsi2:kcal.mol-1">0.0000</scalar>      
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="section" pattern="\s*NSTEP.*" endPattern="\s*">    <record />    <record>{I,am:step}{E,am:etot}{E,am:rms}{E,am:gmax}.*</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
           </template>  <template id="section" pattern="(.+=){4}.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record>{X,am:name}={F,am:value}{X,am:name}={F,am:value}{X,am:name}={F,am:value}{X,am:name}={F,am:value}</record>    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="pullup" xpath=".//cml:scalar" repeat="3" />                 
           </template>  <template id="section" pattern="(.+=){3}.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record>{X,am:name}={F,am:value}{X,am:name}={F,am:value}{X,am:name}={F,am:value}</record>    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="pullup" xpath=".//cml:scalar" repeat="3" />                   
           </template>
               
       </templateList>
   <transform process="delete" xpath=".//cml:module" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addAttribute" xpath="./cml:scalar[@dictRef='am:time(ps)']" name="dictRef" value="am:time" />
   <transform process="addAttribute" xpath="./cml:scalar[@dictRef='am:temp(k)']" name="dictRef" value="am:temp" />
   <transform process="addAttribute" xpath="./cml:scalar[@dictRef='am:1.4.nb']" name="dictRef" value="am:nb14" />
   <transform process="addAttribute" xpath="./cml:scalar[@dictRef='am:1.4.eel']" name="dictRef" value="am:eel14" />
   <transform process="addAttribute" xpath="./cml:scalar[@dictRef='am:1.4.vdw']" name="dictRef" value="am:vdw14" />
   <transform process="addUnits" xpath="./cml:scalar[@dictRef='am:time']" value="nonsi:picoseconds" />
   <transform process="addUnits" xpath="./cml:scalar[@dictRef='am:temp']" value="si:k" />
   <transform process="addUnits" xpath="./cml:scalar[@dictRef='am:temp']" value="nonsi:k" />
   <transform process="addUnits" xpath="./cml:scalar[matches(@dictRef, 'am:e.*') ]" value="nonsi2:kcal.mol-1" />
   <transform process="addUnits" xpath="./cml:scalar[matches(@dictRef, 'am:(bond|angle|dihed|nb14|eel14|vdwaals|vdw14|restraint|virial)') ]" value="nonsi2:kcal.mol-1" />
   <transform process="addUnits" xpath="./cml:scalar[matches(@dictRef, 'am:press') ]" value="nonsi2:bar" />
   <transform process="addAttribute" xpath="./cml:scalar" name="dataType" value="xsd:double" />
   <transform process="addAttribute" xpath="./cml:scalar[@dictRef='am:nstep']" name="dataType" value="xsd:integer" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
