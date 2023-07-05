.. _qespresso.phonon.input-d3e60930:

qespresso.phonon.input
======================

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
   | *source*                                                                                                                   | QuantumEspresso phonon input                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | qespresso.phonon.input                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | QuantumEspresso phonon input                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   &INPUT
   flfrc  =  "ph.fc"
   asr  =  "crystal"
   q_in_band_form  =  .true.
   /
   12
   0 0 0 20 !G
   0.5 0.0 0.5 20 !X
   0.5 0.25 0.75 20 !W
   0.375 0.375 0.75 20 !K
   0 0 0 20 !G
   0.5 0.5 0.5 20 !L
   0.625 0.25 0.625 20 !U
   0.5 0.25 0.75 20 !W
   0.5 0.5 0.5 20 !L
   0.375 0.375 0.75 0 !K
   0.625 0.25 0.625 20 !U
   0.5 0.0 0.5 0 !X
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="qespresso.phonon.input">
           <module id="qespresso.phonon.input">      
             <list cmlx:templateRef="INPUT">
               <list>
                  <scalar dataType="xsd:string" dictRef="cc:parameter">flfrc</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:value">"ph.fc"</scalar>
               </list>
               <list>
                  <scalar dataType="xsd:string" dictRef="cc:parameter">asr</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:value">"crystal"</scalar>
               </list>
               <list>
                  <scalar dataType="xsd:string" dictRef="cc:parameter">q_in_band_form</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
               </list>
              </list>
              <list cmlx:templateRef="kpoints_info">
               <array dataType="xsd:double" dictRef="qex:kpointlist" size="36">0 0 0 0.5 0.0 0.5 0.5 0.25 0.75 0.375 0.375 0.75 0 0 0 0.5 0.5 0.5 0.625 0.25 0.625 0.5 0.25 0.75 0.5 0.5 0.5 0.375 0.375 0.75 0.625 0.25 0.625 0.5 0.0 0.5</array>
               <array dataType="xsd:integer" dictRef="qex:weight" size="12">20 20 20 20 20 20 20 20 20 0 20 0</array>
               <array dataType="xsd:string" dictRef="qex:path" size="12">!G !X !W !K !G !L !U !W !L !K !U !X</array>
              </list>
           </module> 
   </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern="\s*\u0026\S+.*" endPattern="\s*\u002F\s*" endPattern2="\s*\u0026\S+.*" endPattern3="~" endOffset="0" repeat="*">    <record>\s*\u0026{X,x:section}</record>    <record repeat="*">\s*!\s*</record>    <record id="section" repeat="*">{X,cc:parameter}=\s*['\.]?{X,cc:value}['\.]?\s*,?\s*</record>    <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='section']" name="cmlx:templateRef" value="$string(preceding-sibling::cml:list/cml:scalar[@dictRef='x:section']/text())" />
           </template>  <template pattern="\s*(?i)K_POINTS.*(gamma|tpiba|crystal).*" endPattern="\s*" endPattern2="~">    <record id="KPOINTS">\s*K_POINTS\s*{A,qex:meshScheme}.*</record>    <record />    <templateList>      <template pattern="\s*(\S+\s+){3}(\d+)\s*" endPattern="\s*" endPattern2="~">        <record id="kpoints_info" repeat="*" makeArray="true">{3F,qex:kpointlist}{I,qex:weight}</record>        <transform process="pullup" xpath=".//cml:array" repeat="2" />                                     
                   </template>      <template pattern="\s*(\S+\s+){3}(\d+)\s+\S+.*" endPattern="\s*" endPattern2="~">        <record id="kpoints_info" repeat="*" makeArray="true">{3F,qex:kpointlist}{I,qex:weight}{A,qex:path}</record>        <transform process="pullup" xpath=".//cml:array" repeat="2" />                                      
                   </template>
               </templateList>    <transform process="moveRelative" xpath=".//cml:array" to="preceding::cml:scalar[@dictRef='qex:meshScheme']/parent::cml:list" />
           </template>  <template pattern="\s*(?i)K_POINTS\s*automatic.*" endPattern=".*" endPattern2="~" endOffset="1">    <record id="KPOINTS">\s*K_POINTS{X,qex:meshScheme}</record>    <record id="kpoints_info">{3I,qex:subdivisionN}{3F,qex:shiftS}.*</record>    <transform process="moveRelative" xpath=".//cml:array" to="preceding::cml:scalar[@dictRef='qex:meshScheme']/parent::cml:list" />    <transform process="addAttribute" xpath="./cml:list[child::cml:list]" name="cmlx:templateRef" value="KPOINTS" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />                   
           </template>  <template pattern="\s*\d+\s*$\s*(\S+\s+){3}(\d+)\s+\S+.*" endPattern="\s*" endPattern2="~">    <record />    <record id="kpoints_info" repeat="*" makeArray="true">{3F,qex:kpointlist}{I,qex:weight}{A,qex:path}</record>
           </template>  <transform process="delete" xpath=".//cml:list[@cmlx:templateRef='missingID']" />  <transform process="pullup" xpath="./cml:module/cml:list" />  <transform process="delete" xpath="./cml:module" />  <transform process="delete" xpath=".//cml:list[count(*)= 0]" />  <transform process="delete" xpath="//cml:list/text()" />  <transform process="delete" xpath="//cml:list/text()" />  <transform process="delete" xpath="//cml:module/text()" />      
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
