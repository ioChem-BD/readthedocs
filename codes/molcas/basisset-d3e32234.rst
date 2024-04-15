.. _basisset-d3e32234:

basisset
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
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | basisset                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Basis set section                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Basis&#92;sset&#92;slabel.\*                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;*{10,}.\*                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | &#92;-&#92;-.\*                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern4                                                                                                                | &#92;+&#92;+&#92;s*Molecular&#92;sstructure&#92;sinfo.\*                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/basisset.xml                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         Basis set label:C.CC-PVTZ.......... 

         Valence basis set:
         ==================
         Associated Effective Charge  6.000000 au
         Associated Actual Charge     6.000000 au
         Nuclear Model: Point charge


         Shell  nPrim  nBasis  Cartesian Spherical Contaminant
            s      10       4        X                  
            p       5       3        X                  
            d       2       2                 X         
            f       1       1                 X         
         Basis set label:O.CC-PVTZ......... 

         Valence basis set:
         ==================
         Associated Effective Charge  8.000000 au
         Associated Actual Charge     8.000000 au
         Nuclear Model: Point charge


         Shell  nPrim  nBasis  Cartesian Spherical Contaminant
            s      10       4        X                  
            p       5       3        X                  
            d       2       2                 X         
            f       1       1                 X         
         Basis set label:H.CC-PVTZ......... 

         Valence basis set:
         ==================
         Associated Effective Charge  1.000000 au
         Associated Actual Charge     1.000000 au
         Nuclear Model: Point charge


         Shell  nPrim  nBasis  Cartesian Spherical Contaminant
            s       5       3        X                  
            p       2       2        X                  
            d       1       1                 X         


   ++       Molecular structure info:

       

.. container:: formalpara-title

   **Input**

::

         Basis set label:C.ANO-S...3S2P. 
    
         Valence basis set:
         ------------------
         Associated Effective Charge  6.000000 au
         Associated Actual Charge     6.000000 au
         Nuclear Model: Point charge
    
         Shell  nPrim  nBasis  Cartesian Spherical Contaminant
            s      10       3        X                  
            p       6       2        X                  
    
    
         Basis set label:O.ANO-S...3S2P. 
    
         Valence basis set:
         ------------------
         Associated Effective Charge  8.000000 au
         Associated Actual Charge     8.000000 au
         Nuclear Model: Point charge
    
         Shell  nPrim  nBasis  Cartesian Spherical Contaminant
            s      10       3        X                  
            p       6       2        X                  
    
    
         Basis set label:H.ANO-S...2S. 
    
         Valence basis set:
         ------------------
         Associated Effective Charge  1.000000 au
         Associated Actual Charge     1.000000 au
         Nuclear Model: Point charge
    
         Shell  nPrim  nBasis  Cartesian Spherical Contaminant
            s       7       2        X                  
   --
    
    
   ++    Molecular structure info: 
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="basisset">
            <module cmlx:templateRef="basisset">
               <module cmlx:templateRef="section">
                  <array dataType="xsd:string" delimiter="|" dictRef="m:basis" size="12">C|CC-PVTZ||||||||||</array>
                  <module cmlx:templateRef="valence">
                     <scalar dataType="xsd:double" dictRef="m:effectivecharge">6.000000</scalar>
                     <scalar dataType="xsd:double" dictRef="m:actualCharge">6.000000</scalar>
                     <list cmlx:templateRef="shells">
                        <array dataType="xsd:string" dictRef="m:shell" size="4">s p d f</array>
                        <array dataType="xsd:integer" dictRef="m:nprim" size="4">10 5 2 1</array>
                        <array dataType="xsd:integer" dictRef="m:nbasis" size="4">4 3 2 1</array>
                     </list>
                  </module>
               </module>
               <module cmlx:templateRef="section">
                  <array dataType="xsd:string" delimiter="|" dictRef="m:basis" size="11">O|CC-PVTZ|||||||||</array>
                  <module cmlx:templateRef="valence">
                     <scalar dataType="xsd:double" dictRef="m:effectivecharge">8.000000</scalar>
                     <scalar dataType="xsd:double" dictRef="m:actualCharge">8.000000</scalar>
                     <list cmlx:templateRef="shells">
                        <array dataType="xsd:string" dictRef="m:shell" size="4">s p d f</array>
                        <array dataType="xsd:integer" dictRef="m:nprim" size="4">10 5 2 1</array>
                        <array dataType="xsd:integer" dictRef="m:nbasis" size="4">4 3 2 1</array>
                     </list>
                  </module>
               </module>
               <module cmlx:templateRef="section">
                  <array dataType="xsd:string" delimiter="|" dictRef="m:basis" size="11">H|CC-PVTZ|||||||||</array>
                  <module cmlx:templateRef="valence">
                     <scalar dataType="xsd:double" dictRef="m:effectivecharge">1.000000</scalar>
                     <scalar dataType="xsd:double" dictRef="m:actualCharge">1.000000</scalar>
                     <list cmlx:templateRef="shells">
                        <array dataType="xsd:string" dictRef="m:shell" size="3">s p d</array>
                        <array dataType="xsd:integer" dictRef="m:nprim" size="3">5 2 1</array>
                        <array dataType="xsd:integer" dictRef="m:nbasis" size="3">3 2 1</array>
                     </list>
                  </module>
               </module>
            </module>    
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="basisset2">
           <module cmlx:templateRef="basisset">
               <module cmlx:templateRef="section">
                  <array dataType="xsd:string" delimiter="|" dictRef="m:basis" size="6">C|ANO-S|||3S2P|</array>
                  <module cmlx:templateRef="valence">
                     <scalar dataType="xsd:double" dictRef="m:effectivecharge">6.000000</scalar>
                     <scalar dataType="xsd:double" dictRef="m:actualCharge">6.000000</scalar>
                     <list cmlx:templateRef="shells">
                        <array dataType="xsd:string" dictRef="m:shell" size="2">s p</array>
                        <array dataType="xsd:integer" dictRef="m:nprim" size="2">10 6</array>
                        <array dataType="xsd:integer" dictRef="m:nbasis" size="2">3 2</array>
                     </list>
                  </module>
               </module>
               <module cmlx:templateRef="section">
                  <array dataType="xsd:string" delimiter="|" dictRef="m:basis" size="6">O|ANO-S|||3S2P|</array>
                  <module cmlx:templateRef="valence">
                     <scalar dataType="xsd:double" dictRef="m:effectivecharge">8.000000</scalar>
                     <scalar dataType="xsd:double" dictRef="m:actualCharge">8.000000</scalar>
                     <list cmlx:templateRef="shells">
                        <array dataType="xsd:string" dictRef="m:shell" size="2">s p</array>
                        <array dataType="xsd:integer" dictRef="m:nprim" size="2">10 6</array>
                        <array dataType="xsd:integer" dictRef="m:nbasis" size="2">3 2</array>
                     </list>
                  </module>
               </module>
               <module cmlx:templateRef="section">
                  <array dataType="xsd:string" delimiter="|" dictRef="m:basis" size="6">H|ANO-S|||2S|</array>
                  <module cmlx:templateRef="valence">
                     <scalar dataType="xsd:double" dictRef="m:effectivecharge">1.000000</scalar>
                     <scalar dataType="xsd:double" dictRef="m:actualCharge">1.000000</scalar>
                     <list cmlx:templateRef="shells">
                        <array dataType="xsd:string" dictRef="m:shell" size="1">s</array>
                        <array dataType="xsd:integer" dictRef="m:nprim" size="1">7</array>
                        <array dataType="xsd:integer" dictRef="m:nbasis" size="1">2</array>
                     </list>
                  </module>
               </module>
            </module>    
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="section" pattern=".*Basis\sset\slabel.*" endPattern=".*Basis\sset\slabel.*" endPattern2="~" endOffset="0" repeat="*">    <templateList>      <template id="param12" pattern="\s*Basis\sset\slabel:(.*\.){11}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}\.{X,m:basis7}\.{X,m:basis8}\.{X,m:basis9}\.{X,m:basis10}\.{X,m:basis11}\.{X,m:basis12}.*</record>              
                   </template>      <template id="param11" pattern="\s*Basis\sset\slabel:(.*\.){10}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}\.{X,m:basis7}\.{X,m:basis8}\.{X,m:basis9}\.{X,m:basis10}\.{X,m:basis11}.*</record>               
                   </template>      <template id="param10" pattern="\s*Basis\sset\slabel:(.*\.){9}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}\.{X,m:basis7}\.{X,m:basis8}\.{X,m:basis9}\.{X,m:basis10}.*</record>               
                   </template>      <template id="param9" pattern="\s*Basis\sset\slabel:(.*\.){8}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}\.{X,m:basis7}\.{X,m:basis8}\.{X,m:basis9}.*</record>               
                   </template>      <template id="param8" pattern="\s*Basis\sset\slabel:(.*\.){7}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}\.{X,m:basis7}\.{X,m:basis8}.*</record>             
                   </template>      <template id="param7" pattern="\s*Basis\sset\slabel:(.*\.){6}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}\.{X,m:basis7}.*</record>               
                   </template>      <template id="param6" pattern="\s*Basis\sset\slabel:(.*\.){5}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}\.{X,m:basis6}.*</record>             
                   </template>      <template id="param5" pattern="\s*Basis\sset\slabel:(.*\.){4}.*" endPattern=".*">        <record>\s*Basis\sset\slabel:{X,m:basis}\.{X,m:basis2}\.{X,m:basis3}\.{X,m:basis4}\.{X,m:basis5}.*</record>               
                   </template>      <template id="valence" pattern="\s*Valence\sbasis\sset:" pattern2="\s*Electronic\svalence\sbasis\sset:" endPattern="\s*Effective\sCore\sPotential.*" endPattern2="~">        <record repeat="2" />        <record>\s*Associated\sEffective\sCharge{F,m:effectivecharge}.*</record>        <record>\s*Associated\sActual\sCharge{F,m:actualCharge}.*</record>        <templateList>          <template id="shells" pattern="\s*Shell\s+nPrim.*" endPattern="~">            <record />            <record id="shells" repeat="*" makeArray="true">{A,m:shell}{I,m:nprim}{I,m:nbasis}.*</record>            <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='shells']" />
                           </template>
                       </templateList>                   
                   </template>
               </templateList>    <transform process="createArray" delimiter="|" xpath="." from=".//cml:scalar[starts-with(@dictRef,'m:basis')]" />    <transform process="pullup" xpath=".//cml:array[@dictRef='m:basis']" repeat="2" />    <transform process="pullup" xpath=".//cml:array[@dictRef='m:basis']" />
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
