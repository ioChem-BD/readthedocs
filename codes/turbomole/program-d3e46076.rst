.. _program-d3e46076:

program
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
   | *source*                                                                                                                   | Turbomole log                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | program                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Program version and runtime                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;w*&#92;s*&#92;(.*&#92;)&#92;s*&#92;:&#92;s*TURBOMOLE.\*                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Copyright.\*                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 4                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | program.version.xml                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    statpt(maginet-iv108) : TURBOMOLE V6.3 7 Feb 2011 at 15:58:30
    Copyright (C) 2011 TURBOMOLE GmbH, Karlsruhe
    
    
    2011-12-15 08:13:20.786 
     

.. container:: formalpara-title

   **Input**

::

    relax(maginet-ii146) : TURBOMOLE V5-8-0 24 Nov 2005 at 22:47:17
    Copyright (C) 2005 University of Karlsruhe


    2010-12-23 03:10:52.701
     

.. container:: formalpara-title

   **Input**

::

    grad (p1052) : TURBOMOLE rev. V7.4.1 (b987a8a8) compiled 15 Oct 2019 at 12:10:21
    Copyright (C) 2019 TURBOMOLE GmbH, Karlsruhe


    2020-05-19 20:44:46.639 
     

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="program2">
    ridft (maginet165) : TURBOMOLE V6.6( 19134 ) 3 Jun 2014 at 14:53:30
    Copyright (C) 2014 TURBOMOLE GmbH, Karlsruhe


    2015-02-13 10:10:20.395  
     </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="program">
         <module cmlx:templateRef="program">   
               <list cmlx:templateRef="prog">
                  <scalar dataType="xsd:string" dictRef="t:module">statpt</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:hostname">maginet-iv108</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:program">TURBOMOLE</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:programDate">7 Feb 2011 at 15:58:30</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:programVersion" id="programVersion">6.3</scalar>
               </list>
               <scalar dataType="xsd:date" dictRef="cc:date">2011-12-15T08:13:20.786+01:00</scalar>
         </module>         
     </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="program2">
         <module cmlx:templateRef="program">   
             <list cmlx:templateRef="prog">
                <scalar dataType="xsd:string" dictRef="t:module">ridft</scalar>
                <scalar dataType="xsd:string" dictRef="cc:hostname">maginet165</scalar>
                <scalar dataType="xsd:string" dictRef="cc:program">TURBOMOLE</scalar>
                <scalar dataType="xsd:string" dictRef="cc:programDate">3 Jun 2014 at 14:53:30</scalar>
                <scalar dataType="xsd:string" dictRef="cc:programVersion" id="programVersion">6.6</scalar>
             </list>
             <scalar dataType="xsd:date" dictRef="cc:date">2015-02-13T10:10:20.395+01:00</scalar>     
         </module>         
     </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="program3">
       <module cmlx:templateRef="program">
          <list cmlx:templateRef="prog">
             <scalar dataType="xsd:string" dictRef="t:module">relax</scalar>
             <scalar dataType="xsd:string" dictRef="cc:hostname">maginet-ii146</scalar>
             <scalar dataType="xsd:string" dictRef="cc:program">TURBOMOLE</scalar>
             <scalar dataType="xsd:string" dictRef="cc:programVersion">5-8-0</scalar>
             <scalar dataType="xsd:string" dictRef="cc:programDate">24 Nov 2005 at 22:47:17</scalar>
          </list>
          <scalar dataType="xsd:date" dictRef="cc:date">2010-12-23T03:10:52.701+01:00</scalar>
        </module>
     </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="program4"> 
       <module cmlx:templateRef="program">
           <list cmlx:templateRef="prog">
              <scalar dataType="xsd:string" dictRef="t:module">grad</scalar>
              <scalar dataType="xsd:string" dictRef="cc:hostname">p1052</scalar>
              <scalar dataType="xsd:string" dictRef="cc:program">TURBOMOLE</scalar>
              <scalar dataType="xsd:string" dictRef="cc:programDate">15 Oct 2019 at 12:10:21</scalar>
              <scalar dataType="xsd:string" dictRef="cc:programVersion" id="programVersion">7.4.1</scalar>
           </list>
           <scalar dataType="xsd:date" dictRef="cc:date">2020-05-19T20:44:46.639+02:00</scalar>
       </module>
     </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template name="previous60" pattern="\s*\w*\s*\(.*\)\s*\:\s*TURBOMOLE\s+V\d+-\d+.*" endPattern="~">    <record id="prog">\s*{A,t:module}\({X,cc:hostname}\)\s*:\s*{A,cc:program}\s*V{A,cc:programVersion}\s+{X,cc:programDate}</record>    <record repeat="3" />    <record id="runtime">{X,cc:date}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:date']" format="yyyy-MM-dd HH:mm:ss.SSS" />
       </template>  <template name="previous74" pattern="\s*\w*\s*\(.*\)\s*\:\s*TURBOMOLE\s*(?:rev\.)?\s*V\d+\.\d+[\(|\s)].*" endPattern="~">    <record id="prog">\s*{A,t:module}\({X,cc:hostname}\)\s*:\s*{A,cc:program}\s*(?:rev\.)?\s*V{I,x:programVersionMajor}\.{I,x:programVersionMinor}((\(\s*\S+\s*\))|\s)?(?:\s*compiled\s*)?{X,cc:programDate}</record>    <record repeat="3" />    <record id="runtime">{X,cc:date}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:date']" format="yyyy-MM-dd HH:mm:ss.SSS" />    <transform process="addChild" xpath="." elementName="cml:scalar" id="programVersion" value="$string(concat(.//cml:scalar[@dictRef='x:programVersionMajor']/text(),'.',.//cml:scalar[@dictRef='x:programVersionMinor']/text()))" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:programVersionMajor']" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:programVersionMinor']" />    <transform process="moveRelative" xpath=".//cml:scalar[@id='programVersion']" to="./ancestor::*/cml:list[@cmlx:templateRef='prog']" />    <transform process="addAttribute" xpath=".//cml:scalar[@id='programVersion']" name="dataType" value="xsd:string" />    <transform process="addDictRef" xpath=".//cml:scalar[@id='programVersion']" value="cc:programVersion" />
                
       </template>  <template name="after74" pattern="\s*\w*\s*\(.*\)\s*\:\s*TURBOMOLE\s*(?:rev\.)?\s*V\d+\.\d+\.\d+[\(|\s)].*" endPattern="~">    <record id="prog">\s*{A,t:module}\({X,cc:hostname}\)\s*:\s*{A,cc:program}\s*(?:rev\.)?\s*V{I,x:programVersionMajor}\.{I,x:programVersionMinor}\.{I,x:programVersionBug}(?:(\(\s*\S+\s*\))|\s)(?:\s*compiled)?{X,cc:programDate}</record>    <record repeat="3" />    <record id="runtime">{X,cc:date}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:date']" format="yyyy-MM-dd HH:mm:ss.SSS" />    <transform process="addChild" xpath="." elementName="cml:scalar" id="programVersion" value="$string(concat(.//cml:scalar[@dictRef='x:programVersionMajor']/text(),'.',.//cml:scalar[@dictRef='x:programVersionMinor']/text(),'.',.//cml:scalar[@dictRef='x:programVersionBug']/text()))" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:programVersionMajor']" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:programVersionMinor']" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:programVersionBug']" />    <transform process="moveRelative" xpath=".//cml:scalar[@id='programVersion']" to="./ancestor::*/cml:list[@cmlx:templateRef='prog']" />    <transform process="addAttribute" xpath=".//cml:scalar[@id='programVersion']" name="dataType" value="xsd:string" />    <transform process="addDictRef" xpath=".//cml:scalar[@id='programVersion']" value="cc:programVersion" />
       </template>
     </templateList>
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='prog']" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:date']" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
