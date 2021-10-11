.. _program.header-d3e28:

program.header
==============

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image0|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | program.header                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Generic program header                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;*&#92;s+Amsterdam&#92;sDensity&#92;sFunctional.\*                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*&#92;*&#92;s+Amsterdam&#92;sModeling&#92;sSuite.\*                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -3                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*RunTime.\*                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | program.header.xml                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

**Input.**

::

    *******************************************************************************
    *                                                                             *
    *  -------------------------------------                                      *
    *   Amsterdam Density Functional  (ADF)         2007.01   August 20, 2007     *
    *  -------------------------------------                                      *
    *                                               Build 200708201257            *
    *                                                                             *
    *                                                                             *
    *                            =====================                            *
    *                            |                   |                            *
    *                            |     X X X X X     |                            *
    *                            |                   |                            *
    *                            =====================                            *
    *                                                                             *
    *                                                                             *
    *   Online information and documentation:  http://www.scm.com                 *
    *   E-mail:  support@scm.com   info@scm.com                                   *
    *                                                                             *
    *   Scientific publications using ADF results must be properly referenced     *
    *   See the User Manuals (or the web site) for recommended citations          *
    *   The terms and conditions of the End User License Agreement apply to       *
    *   the use of ADF, http://www.scm.com/Sales/LicAgreement.html                *
    *                                                                             *
    ****************************  pentium_linux_ifc  ******************************
    
    DIRAC 2007.01  RunTime: Oct16-2008 12:08:11    
           

**Input.**

::

    *******************************************************************************
    *                                                                             *
    *  -------------------------------------                                      *
    *   Amsterdam Density Functional  (ADF)         2014                          *
    *  -------------------------------------                                      *
    *                                               r48167 2015-10-14             *
    *                                                                             *
    *                                                                             *
    *                            =====================                            *
    *                            |                   |                            *
    *                            |     D I R A C     |                            *
    *                            |                   |                            *
    *                            =====================                            *
    *                                                                             *
    *                                                                             *
    *   Online information and documentation:  http://www.scm.com                 *
    *   E-mail:  support@scm.com   info@scm.com                                   *
    *                                                                             *
    *   Scientific publications using ADF results must be properly referenced     *
    *   See the User Manuals (or the web site) for recommended citations          *
    *   The terms and conditions of the End User License Agreement apply to       *
    *   the use of ADF, http://www.scm.com/Sales/LicAgreement.html                *
    *                                                                             *
    ********************  x86_64_linux_intel / platform_mpi  **********************
    
    Licensed to: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    SCM User ID: XXXXX
     
    DIRAC 2014  RunTime: Mar01-2016 19:27:34  Nodes: 1  Procs: 1        
           

**Input.**

::

    *******************************************************************************
    *                                                                             *
    *  --------------------------------                                           *
    *   Amsterdam Modeling Suite (AMS)              2019.302                      *
    *  --------------------------------                                           *
    *                                               r80089 2019-12-11             *
    *                                                                             *
    *                                                                             *
    *                            =====================                            *
    *                            |                   |                            *
    *                            |     D I R A C     |                            *
    *                            |                   |                            *
    *                            =====================                            *
    *                                                                             *
    *                                                                             *
    *   Online information and documentation:  https://www.scm.com/support/       *
    *   E-mail:  support@scm.com   info@scm.com                                   *
    *                                                                             *
    *   Scientific publications using AMS results must be properly referenced     *
    *   See the User Manuals (or the web site) for recommended citations          *
    *   The terms and conditions of the End User License Agreement apply to       *
    *   the use of AMS, https://www.scm.com/license-terms/                        *
    *                                                                             *
    ***********************  x86_64_linux_intel / openmpi  ************************

    Licensed to: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    SCM User ID: XXXXX
     
    DIRAC 2019.302  RunTime: May29-2020 06:12:53  Nodes: 1  Procs: 1
           
           

**Output text.**

.. code:: xml

   <comment class="example.output" id="program.header">
           <module cmlx:templateRef="program.header">
               <scalar dataType="xsd:string" dictRef="cc:program">ADF</scalar>
               <scalar dataType="xsd:integer" dictRef="cc:programVersion">2007</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programSubversion">01</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programDate">August 20, 2007</scalar>
               <scalar dataType="xsd:string" dictRef="cc:compileDate">200708201257</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programFlavour">pentium_linux_ifc</scalar>
               <scalar dataType="xsd:string" dictRef="cc:runDate">Oct16-2008 12:08:11</scalar>
          </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="program.header2">
           <module cmlx:templateRef="program.header">
               <scalar dataType="xsd:string" dictRef="cc:program">ADF</scalar>
               <scalar dataType="xsd:integer" dictRef="cc:programVersion">2014</scalar>
               <scalar dataType="xsd:string" dictRef="a:compilation">r48167</scalar>
               <scalar dataType="xsd:string" dictRef="cc:compileDate">2015-10-14</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programFlavour">x86_64_linux_intel / platform_mpi</scalar>
               <scalar dataType="xsd:string" dictRef="cc:runDate">Mar01-2016 19:27:34</scalar>
            </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="program.header3">
           <module cmlx:templateRef="program.header">
               <scalar dataType="xsd:integer" dictRef="cc:programVersion">2019</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programSubversion">302</scalar>
               <scalar dataType="xsd:string" dictRef="cc:program">ADF</scalar>
               <scalar dataType="xsd:string" dictRef="a:compilation">r80089</scalar>
               <scalar dataType="xsd:string" dictRef="cc:compileDate">2019-12-11</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programFlavour">x86_64_linux_intel / openmpi</scalar>
               <scalar dataType="xsd:string" dictRef="cc:runDate">May29-2020 06:12:53</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*\*\s*Amsterdam\sDensity\sFunctional\s*\(ADF\)\s*development\sversion\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sDensity\sFunctional\s+\({A,cc:program}\).*</record>
               </template>  <template pattern="\s*\*\s*Amsterdam\sDensity\sFunctional\s*\(ADF\)\s*[\S]+\s+[\S]+.*\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sDensity\sFunctional\s+\({A,cc:program}\)\s*{I,cc:programVersion}\.{A,cc:programSubversion}\s+{X,cc:programDate}\s*\*.*</record>
               </template>  <template pattern="\s*\*\s*Amsterdam\sDensity\sFunctional\s*\(ADF\)\s+[\S]+\s+\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sDensity\sFunctional\s+\({A,cc:program}\)\s+{I,cc:programVersion}.*</record>
               </template>  <template pattern="\s*\*\s*Amsterdam\sDensity\sFunctional\s*\(ADF\)\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sDensity\sFunctional\s+\({A,cc:program}\).*</record>
               </template>  <template pattern="\s*\*\s*Amsterdam\sModeling\sSuite\s*\(AMS\)\s*development\sversion\s*\*.*" endPattern=".*">    <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:program" value="ADF" />    <transform process="addAttribute" xpath="./cml:scalar[@dictRef='cc:program']" name="dataType" value="xsd:string" />                   
               </template>  <template pattern="\s*\*\s*Amsterdam\sModeling\sSuite\s*\(AMS\)\s*[\S]+\s+[\S]+.*\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sModeling\sSuite\s+\(.*\)\s*{I,cc:programVersion}\.{A,cc:programSubversion}\s+{X,cc:programDate}\s*\*.*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:program" value="ADF" />    <transform process="addAttribute" xpath="./cml:scalar[@dictRef='cc:program']" name="dataType" value="xsd:string" />               
               </template>  <template pattern="\s*\*\s*Amsterdam\sModeling\sSuite\s*\(AMS\)\s*[\S]+\.[\S]+.*\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sModeling\sSuite\s+\(.*\)\s+{I,cc:programVersion}\.{A,cc:programSubversion}\s*\*.*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:program" value="ADF" />    <transform process="addAttribute" xpath="./cml:scalar[@dictRef='cc:program']" name="dataType" value="xsd:string" />
               </template>  <template pattern="\s*\*\s*Amsterdam\sModeling\sSuite\s*\(AMS\)\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sModeling\sSuite\s+\(.*\).*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:program" value="ADF" />    <transform process="addAttribute" xpath="./cml:scalar[@dictRef='cc:program']" name="dataType" value="xsd:string" />
               </template>  <template pattern="\s*\*\s*Build\s*.*" endPattern=".*">    <record id="program">\s*\*\s*Build\s*{A,cc:compileDate}.*</record>              
               </template>  <template pattern="\s*\*\s*Amsterdam\sDensity\sFunctional\s*\(ADF\)\s+[0-9]+\s*\*.*" endPattern=".*">    <record id="program">\s*\*\s*Amsterdam\sDensity\sFunctional\s+\({A,cc:program}\)\s*{I,cc:programVersion}\s*\*.*</record>
               </template>  <template pattern="\s*\*\s{40,}[\S]+.*\*.*" endPattern=".*">    <record id="program">\s*\*\s{40,}{A,a:compilation}{A,cc:compileDate}.*</record>                
               </template>  <template pattern="\s*\*{20,}+\s*\S+\s*.*" endPattern=".*" endOffset="0">    <record id="programFlavour">\s*\*{20,}+\s+{X,cc:programFlavour}\s+\*+.*</record>              
               </template>  <template pattern="\s*.*RunTime:.*Nodes.*" endPattern=".*" endPattern2="~" endOffset="0">    <record id="runDate">\s*.*RunTime:{X,cc:runDate}Nodes.*</record>
               </template>  <template pattern="\s*.*RunTime:.*" endPattern=".*" endPattern2="~" endOffset="0">    <record id="runDate">\s*.*RunTime:{X,cc:runDate}</record>
               </template>
           </templateList>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
