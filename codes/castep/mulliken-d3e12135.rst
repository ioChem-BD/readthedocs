.. _mulliken-d3e12135:

mulliken
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
   | *source*                                                                                                                   | CASTEP log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | mulliken                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Mulliken atomic population                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Atomic&#92;sPopulations&#92;s&#92;(Mulliken&#92;).\*                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | geomopt/mulliken.xml                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

        Atomic Populations (Mulliken)
        -----------------------------
   Species          Ion Spin      s       p       d       f      Total   Charge(e)   Spin(hbar/2)
   ==============================================================================================
     Si              1   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     1   dn:     0.691   1.309   0.000   0.000   2.000
     Si              2   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     2   dn:     0.691   1.309   0.000   0.000   2.000
     Si              3   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     3   dn:     0.691   1.309   0.000   0.000   2.000
     Si              4   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     4   dn:     0.691   1.309   0.000   0.000   2.000
     Si              5   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     5   dn:     0.691   1.309   0.000   0.000   2.000
     Si              6   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     6   dn:     0.691   1.309   0.000   0.000   2.000
     Si              7   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     7   dn:     0.691   1.309   0.000   0.000   2.000
     Si              8   up:     0.691   1.309   0.000   0.000   2.000     0.000        0.000
                     8   dn:     0.691   1.309   0.000   0.000   2.000
   ==============================================================================================  

       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="mulliken">
         <module cmlx:templateRef="mulliken">
            <list cmlx:templateRef="row" id="row">
               <array dataType="xsd:string" dictRef="cc:elementType" size="8">Si Si Si Si Si Si Si Si</array>
               <array dataType="xsd:integer" dictRef="cc:serial" size="16">1 1 2 2 3 3 4 4 5 5 6 6 7 7 8 8</array>
               <array dataType="xsd:string" dictRef="ca:spin" size="16">up dn up dn up dn up dn up dn up dn up dn up dn</array>
               <array dataType="xsd:double" dictRef="ca:orbitalS" size="16">0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691 0.691</array>
               <array dataType="xsd:double" dictRef="ca:orbitalP" size="16">1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309 1.309</array>
               <array dataType="xsd:double" dictRef="ca:orbitalD" size="16">0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000</array>
               <array dataType="xsd:double" dictRef="ca:orbitalF" size="16">0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000</array>
               <array dataType="xsd:double" dictRef="x:total" size="16">2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000</array>
               <array dataType="xsd:double" dictRef="x:charge" size="8">0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000</array>
               <array dataType="xsd:double" dictRef="x:spin" size="8">0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000</array>
            </list>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="4" />
   <templateList>  <template pattern=".*up:.*" endPattern=".*dn:.*" endPattern2="~" endOffset="1" repeat="*">    <record>{A,cc:elementType}{I,cc:serial}{A,ca:spin}:{F,ca:orbitalS}{F,ca:orbitalP}{F,ca:orbitalD}{F,ca:orbitalF}{F,x:total}{F,x:charge}{F,x:spin}</record>    <record>{I,cc:serial}{A,ca:spin}:{F,ca:orbitalS}{F,ca:orbitalP}{F,ca:orbitalD}{F,ca:orbitalF}{F,x:total}</record>
           </template>  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:serial']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:elementType']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='ca:spin']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='ca:orbitalS']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='ca:orbitalP']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='ca:orbitalD']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='ca:orbitalF']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:total']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:charge']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:spin']" />  <transform process="pullup" repeat="3" xpath=".//cml:scalar" />  <transform process="pullup" repeat="3" xpath=".//cml:array" />  <transform process="delete" xpath=".//cml:array[@dictRef='spin']" />  <transform process="delete" xpath=".//cml:list[count(*)=0]" />  <transform process="delete" xpath=".//cml:list[count(*)=0]" />  <transform process="delete" xpath=".//cml:module[count(*)=0]" />  <transform process="addChild" xpath="." elementName="cml:list" id="row" />  <transform process="addAttribute" xpath=".//cml:list[@id='row']" name="cmlx:templateRef" value="row" />  <transform process="move" xpath=".//cml:array" to=".//cml:list[@cmlx:templateRef='row']" />  <transform process="move" xpath=".//cml:scalar" to=".//cml:list[@cmlx:templateRef='row']" />

       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
