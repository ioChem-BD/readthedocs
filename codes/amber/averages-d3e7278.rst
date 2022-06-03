.. _averages-d3e7278:

averages
========

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
   | id                                                                                                                         | averages                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Averages                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#                                                                                                                         |
   |                                                                                                                            | 92;s*A&#92;sV&#92;sE&#92;sR&#92;sA&#92;sG&#92;sE&#92;sS&#92;s*O&#92;sV&#92;sE&#92;sR&#92;s*.*S&#92;sT&#92;sE&#92;sP&#92;sS |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*-{20,}.\*                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/averages.xml                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         A V E R A G E S   O V E R     500 S T E P S


    NSTEP = 50000000   TIME(PS) =  101030.000  TEMP(K) =   300.00  PRESS =     0.0
    Etot   =    -19416.4470  EKtot   =      4561.4534  EPtot      =    -23977.9004
    BOND   =        19.5282  ANGLE   =        98.7153  DIHED      =        27.7291
    1-4 NB =         9.2337  1-4 EEL =       -54.1394  VDWAALS    =      3532.6281
    EELEC  =    -27611.5955  EHBOND  =         0.0000  RESTRAINT  =         0.0000
    EKCMT  =         0.0000  VIRIAL  =         0.0000  VOLUME     =     77394.8592
                                                       Density    =         0.9869
    ------------------------------------------------------------------------------
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="averages">
           <module cmlx:templateRef="averages">
               <scalar dataType="xsd:integer" dictRef="am:nstep">50000000</scalar>
               <scalar dataType="xsd:double" dictRef="am:time" units="nonsi:picoseconds">101030.000</scalar>
               <scalar dataType="xsd:double" dictRef="am:temp" units="nonsi:k">300.00</scalar>
               <scalar dataType="xsd:double" dictRef="am:press" units="nonsi2:bar">0.0</scalar>
               <scalar dataType="xsd:double" dictRef="am:etot" units="nonsi2:kcal.mol-1">-19416.4470</scalar>
               <scalar dataType="xsd:double" dictRef="am:ektot" units="nonsi2:kcal.mol-1">4561.4534</scalar>
               <scalar dataType="xsd:double" dictRef="am:eptot" units="nonsi2:kcal.mol-1">-23977.9004</scalar>
               <scalar dataType="xsd:double" dictRef="am:bond" units="nonsi2:kcal.mol-1">19.5282</scalar>
               <scalar dataType="xsd:double" dictRef="am:angle" units="nonsi2:kcal.mol-1">98.7153</scalar>
               <scalar dataType="xsd:double" dictRef="am:dihed" units="nonsi2:kcal.mol-1">27.7291</scalar>
               <scalar dataType="xsd:double" dictRef="am:nb14" units="nonsi2:kcal.mol-1">9.2337</scalar>
               <scalar dataType="xsd:double" dictRef="am:eel14" units="nonsi2:kcal.mol-1">-54.1394</scalar>
               <scalar dataType="xsd:double" dictRef="am:vdwaals" units="nonsi2:kcal.mol-1">3532.6281</scalar>
               <scalar dataType="xsd:double" dictRef="am:eelec" units="nonsi2:kcal.mol-1">-27611.5955</scalar>
               <scalar dataType="xsd:double" dictRef="am:ehbond" units="nonsi2:kcal.mol-1">0.0000</scalar>
               <scalar dataType="xsd:double" dictRef="am:restraint" units="nonsi2:kcal.mol-1">0.0000</scalar>
               <scalar dataType="xsd:double" dictRef="am:ekcmt" units="nonsi2:kcal.mol-1">0.0000</scalar>
               <scalar dataType="xsd:double" dictRef="am:virial" units="nonsi2:kcal.mol-1">0.0000</scalar>
               <scalar dataType="xsd:double" dictRef="am:volume">77394.8592</scalar>
               <scalar dataType="xsd:double" dictRef="am:density">0.9869</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="3" />
   <templateList>  <template id="section" pattern="(.+=){4}.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record>{X,am:name}={F,am:value}{X,am:name}={F,am:value}{X,am:name}={F,am:value}{X,am:name}={F,am:value}</record>    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="pullup" xpath=".//cml:scalar" repeat="3" />                  
           </template>  <template id="section" pattern="(.+=){3}.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record>{X,am:name}={F,am:value}{X,am:name}={F,am:value}{X,am:name}={F,am:value}</record>    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />    <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />    <transform process="pullup" xpath=".//cml:scalar" repeat="3" />                   
           </template>  <template id="section" pattern="\s*Density\s*=.+" endPattern=".*" endPattern2="~" endOffset="0">    <record>\s*Density\s*={F,am:density}</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
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
