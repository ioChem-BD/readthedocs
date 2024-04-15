.. _parameters-d3e55047:

parameters
==========

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
   | *source*                                                                                                                   | Turbomole control file                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | parameters                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Control parameters                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;u0024(?i:(scfinstab|ricc2|statpt|exopt)).\*                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*&#92;u0024(?i:(ri|rij|rir12))&#92;s\*                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;u0024.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | parameters.xml                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   $scfinstab rpas     
       

.. container:: formalpara-title

   **Input**

::

   $rij
       

.. container:: formalpara-title

   **Input**

::

   $rir12
     ansatz      2
     ccsdapprox  ccsd(f12)
     no_f12metric
     r12model    B
     comaprox    F+K
     cabs        svd  1.0000E-08
     examp       fixed  noflip
     corrfac     LCG
     cabsingles  on    
       

.. container:: formalpara-title

   **Input**

::

   $ricc2
     mp2
     ccsd
     ccsd(t)   
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="parameters">
           <module cmlx:templateRef="parameters">
               <scalar dataType="xsd:string" dictRef="t:scfinstab">rpas</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="parameters2">
           <module cmlx:templateRef="parameters">
               <scalar dataType="xsd:string" dictRef="t:rir12">rir12</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="parameters3">
           <module cmlx:templateRef="parameters">
               <scalar dataType="xsd:string" dictRef="t:ri">rir12</scalar>
           </module> 
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="parameters4">
           <module cmlx:templateRef="parameters">
               <scalar dataType="xsd:string" dictRef="t:ricc2">ricc2</scalar>
           </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*\s*\u0024(?i:scfinstab).*" endPattern="\s*\u0024.*" endPattern2="~" repeat="*">    <record>\s*\u0024(?i:scfinstab){X,t:scfinstab}</record>
           </template>  <template pattern="\s*\u0024(?i:exopt).*" endPattern="\s*\u0024.*" endPattern2="~" repeat="*">    <record>\s*\u0024(?i:exopt){I,t:exopt}</record>
           </template>  <template id="ricc2" pattern="\s*\u0024ricc2.*" endPattern="\s*\u0024.*" endPattern2="~" repeat="*">    <record>\s*\u0024{X,t:ricc2}</record>    <record repeat="*" />
           </template>  <template pattern="\s*\u0024(?i:(ri|rij))\s*" endPattern="\s*\u0024.*" endPattern2="~" repeat="*">    <record>\s*\u0024{X,t:ri}</record>
           </template>  <template pattern="\s*\u0024(?i:rir12)\s*" endPattern="\s*\u0024.*" endPattern2="~" repeat="*">    <record>\s*\u0024{X,t:rir12}</record>
           </template>  <template id="statpt" pattern="\s*\u0024(?i:(statpt)).*" endPattern="\s*\u0024.*" endPattern2="~" repeat="*">    <templateList>      <template pattern="\s*(?i:(itrvec)).*" endPattern=".*" endPattern2="~">        <record>\s*(?i:(itrvec)){I,t:itrvec}</record>
                   </template>
               </templateList>    <transform process="addChild" xpath="." elementName="cml:list" id="statpt" />    <transform process="addAttribute" xpath=".//cml:list" name="cmlx:templateRef" value="parameters" />    <transform process="addAttribute" xpath=".//cml:list" name="dictRef" value="t:statpt" />    <transform process="move" xpath=".//cml:scalar" to=".//cml:list[@id='statpt']" />      
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:list[@id='statpt']" />
   <transform process="pullup" xpath=".//cml:list[not(@id='statpt')]/*" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
