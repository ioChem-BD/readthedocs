.. _atoms-d3e51167:

atoms
=====

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
   | id                                                                                                                         | atoms                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Atom definition section                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;u0024atoms&#92;s\*                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;u0024.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | atoms.xml                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   $atoms
   ru 1                                                                           \
      basis =ru def2-SVP                                                          \
      ecp   =ru def2-ecp                                                          \
      jbas  =ru def2-SVP
   n  2-7                                                                         \
      basis =n def2-SVP                                                           \
      jbas  =n def2-SVP
   h  8-31                                                                        \
      basis =h def2-SVP                                                           \
      jbas  =h def2-SVP
   c  32-61                                                                       \
      basis =c def2-SVP                                                           \
      jbas  =c def2-SVP    
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="atoms">
          <module cmlx:templateRef="atoms">
             <module cmlx:templateRef="atomdef">
                <list dictRef="t:atom">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">ru</scalar>
                   <scalar dataType="xsd:string" dictRef="t:atomrange">1</scalar>
                </list>
                <list dictRef="t:basis">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">ru</scalar>
                   <scalar dataType="xsd:string" dictRef="t:basis">def2-SVP</scalar>
                </list>
                <list dictRef="t:ecp">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">ru</scalar>
                   <scalar dataType="xsd:string" dictRef="t:ecp">def2-ecp</scalar>
                </list>
             </module>
             <module cmlx:templateRef="atomdef">
                <list dictRef="t:atom">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">n</scalar>
                   <scalar dataType="xsd:string" dictRef="t:atomrange">2-7</scalar>
                </list>
                <list dictRef="t:basis">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">n</scalar>
                   <scalar dataType="xsd:string" dictRef="t:basis">def2-SVP</scalar>
                </list>
             </module>
             <module cmlx:templateRef="atomdef">
                <list dictRef="t:atom">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">h</scalar>
                   <scalar dataType="xsd:string" dictRef="t:atomrange">8-31</scalar>
                </list>
                <list dictRef="t:basis">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">h</scalar>
                   <scalar dataType="xsd:string" dictRef="t:basis">def2-SVP</scalar>
                </list>
             </module>
             <module cmlx:templateRef="atomdef">
                <list dictRef="t:atom">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">c</scalar>
                   <scalar dataType="xsd:string" dictRef="t:atomrange">32-61</scalar>
                </list>
                <list dictRef="t:basis">
                   <scalar dataType="xsd:string" dictRef="cc:elementType">c</scalar>
                   <scalar dataType="xsd:string" dictRef="t:basis">def2-SVP</scalar>
                </list>
             </module>
          </module>  
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="1" />
   <templateList>  <template id="atomdef" pattern="\s*[A-Za-z]{1,3}\s*([0-9,-]+)[\s*\\?]+" endPattern="\s*[A-Za-z]{1,3}\s*([0-9,-]+)[\s*\\?]+" endPattern2="~" endOffset="0" repeat="*">    <record>{A,cc:elementType}{X,t:atomrange}\s*\\?\s*</record>    <templateList>      <template id="basis" pattern="\s*basis.*" endPattern=".*" endOffset="0">        <record>\s*basis\s*=\s*{A,cc:elementType}{X,t:basis}[\s*\\?]+</record>        <transform process="addDictRef" xpath=".//cml:list/cml:list" value="t:basis" />        <transform process="pullup" xpath=".//cml:list/cml:list" repeat="2" />                                     
                   </template>      <template id="jbas" pattern="\s*jbas.*" endPattern=".*" endOffset="0">        <record>\s*jbas\s*=\s*{A,cc:elementType}{X,t:jbas}[\s*\\?]+</record>        <transform process="addDictRef" xpath=".//cml:list/cml:list" value="t:jbas" />        <transform process="pullup" xpath=".//cml:list/cml:list" repeat="2" />                 
                   </template>      <template id="ecp" pattern="\s*ecp.*" endPattern=".*" endOffset="0">        <record>\s*ecp\s*=\s*{A,cc:elementType}{X,t:ecp}[\s*\\?]+</record>        <transform process="addDictRef" xpath=".//cml:list/cml:list" value="t:ecp" />        <transform process="pullup" xpath=".//cml:list/cml:list" repeat="2" />
                   </template>
               </templateList>    <transform process="addDictRef" xpath=".//cml:list/cml:list" value="t:atom" />    <transform process="pullup" xpath=".//cml:list/cml:list" />                      
           </template>   
       </templateList>
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
