.. _jobcpu-d3e24121:

jobcpu
======

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
   | *source*                          | MOPAC log                         |
   +-----------------------------------+-----------------------------------+
   | id                                | jobcpu                            |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*WALL\-CLOCK\sTIME.\*          |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*COMPUTATION\sTIME.\*          |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | jobcpu.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

             WALL-CLOCK TIME         =  6 HOURS 55 MINUTES AND 24.447 SECONDS
             COMPUTATION TIME        =  8 HOURS  3 MINUTES AND 34.471 SECONDS
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="jobcpu">
           <module cmlx:templateRef="jobcpu">
               <scalar dictRef="cc:wall" units="si:seconds">24924.447</scalar>
               <scalar dictRef="cc:cputime" units="si:seconds">29014.471</scalar>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*WALL-CLOCK\sTIME.*DAY.*" endPattern=".*" endOffset="0">    <record>\s*WALL-CLOCK\sTIME\s*={I,cc:wdays}DAYS{I,cc:whours}HOURS{I,cc:wminutes}MINUTES\sAND{F,cc:wseconds}SECONDS\s*</record>         
           </template>  <template pattern="\s*WALL-CLOCK\sTIME.*HOURS.*" endPattern=".*" endOffset="0">    <record>\s*WALL-CLOCK\sTIME\s*={I,cc:whours}HOURS{I,cc:wminutes}MINUTES\sAND{F,cc:wseconds}SECONDS\s*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:wdays" />                    
           </template>  <template pattern="\s*WALL-CLOCK\sTIME.*MINUTES.*" endPattern=".*" endOffset="0">    <record>\s*WALL-CLOCK\sTIME\s*={I,cc:wminutes}MINUTES\sAND{F,cc:wseconds}SECONDS\s*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:wdays" />    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:whours" />
           </template>  <template pattern="\s*WALL-CLOCK\sTIME.*SECONDS.*" endPattern=".*" endOffset="0">    <record>\s*WALL-CLOCK\sTIME\s*={F,cc:wseconds}SECONDS\s*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:wdays" />    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:whours" />    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:wminutes" />
           </template>  <template pattern="\s*COMPUTATION\sTIME.*DAY.*" endPattern="~">    <record>\s*COMPUTATION\sTIME\s*={I,cc:cdays}DAYS{I,cc:chours}HOURS{I,cc:cminutes}MINUTES\sAND{F,cc:cseconds}SECONDS\s*</record>         
           </template>  <template pattern="\s*COMPUTATION\sTIME.*HOURS.*" endPattern="~">    <record>\s*COMPUTATION\sTIME\s*={I,cc:chours}HOURS{I,cc:cminutes}MINUTES\sAND{F,cc:cseconds}SECONDS\s*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:cdays" />                 
           </template>  <template pattern="\s*COMPUTATION\sTIME.*MINUTES.*" endPattern="~">    <record>\s*COMPUTATION\sTIME\s*={I,cc:cminutes}MINUTES\sAND{F,cc:cseconds}SECONDS\s*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:cdays" />    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:chours" />
           </template>  <template pattern="\s*COMPUTATION\sTIME.*SECONDS.*" endPattern="~">    <record>\s*COMPUTATION\sTIME\s*={F,cc:cseconds}SECONDS\s*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:cdays" />    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:chours" />    <transform process="addChild" xpath="." elementName="cml:scalar" value="0" dictRef="cc:cminutes" />
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:list/cml:scalar" repeat="3" />
   <transform process="pullup" xpath=".//cml:module/cml:scalar" />
   <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:wdays' or @dictRef='cc:cdays']" args="operator=multiply operand=86400" />
   <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:whours' or @dictRef='cc:chours']" args="operator=multiply operand=3600" />
   <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:wminutes' or @dictRef='cc:cminutes']" args="operator=multiply operand=60" />
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:wall" />
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:cputime" />
   <transform process="setValue" xpath="./cml:scalar[@dictRef='cc:wall']" value="$number(number(../cml:scalar[@dictRef='cc:wdays']) + number(../cml:scalar[@dictRef='cc:whours']) + number(../cml:scalar[@dictRef='cc:wminutes']) + number(../cml:scalar[@dictRef='cc:wseconds']))" />
   <transform process="setValue" xpath="./cml:scalar[@dictRef='cc:cputime']" value="$number(number(../cml:scalar[@dictRef='cc:cdays']) + number(../cml:scalar[@dictRef='cc:chours']) + number(../cml:scalar[@dictRef='cc:cminutes']) + number(../cml:scalar[@dictRef='cc:cseconds']))" />
   <transform process="addUnits" xpath="./cml:scalar[@dictRef='cc:wall']" value="si:seconds" />
   <transform process="addUnits" xpath="./cml:scalar[@dictRef='cc:cputime']" value="si:seconds" />
   <transform process="delete" xpath=".//cml:scalar[not(@dictRef='cc:cputime') and not(@dictRef='cc:wall')]" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
