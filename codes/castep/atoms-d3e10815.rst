.. _atoms-d3e10815:

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
   | *source*                                                                                                                   | CASTEP log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | atoms                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;-{10,}.*$&#92;s*Cell&#92;sContents.\*                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*&#92;-{10,}                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | setup/atoms.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                              -------------------------------
                                        Cell Contents
                              -------------------------------
                            Total number of ions in cell =    8
                         Total number of species in cell =    1
                           Max number of any one species =    8
    
               xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
               x  Element    Atom        Fractional coordinates of atoms  x
               x            Number           u          v          w      x
               x----------------------------------------------------------x
               x  Si           1         0.000000   0.000000   0.000000   x 
               x  Si           2         0.000000   0.500000   0.500000   x 
               x  Si           3         0.500000   0.000000   0.500000   x 
               x  Si           4         0.500000   0.500000   0.000000   x 
               x  Si           5         0.750000   0.250000   0.750000   x 
               x  Si           6         0.250000   0.250000   0.250000   x 
               x  Si           7         0.250000   0.750000   0.750000   x 
               x  Si           8         0.750000   0.750000   0.250000   x 
               xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
    
    
                            No user defined ionic velocities
    
                              -------------------------------  
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="atoms">
           <module cmlx:templateRef="atoms">
               <module cmlx:templateRef="atomtable">
                  <list cmlx:templateRef="atom">
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.000000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.000000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.000000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">2</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.000000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.500000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.500000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">3</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.500000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.000000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.500000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">4</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.500000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.500000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.000000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">5</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.750000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.250000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.750000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">6</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.250000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.250000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.250000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">7</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.250000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.750000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.750000</scalar>
                     </list>
                     <list>
                        <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                        <scalar dataType="xsd:integer" dictRef="cc:serial">8</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:xFract">0.750000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:yFract">0.750000</scalar>
                        <scalar dataType="xsd:double" dictRef="cc:zFract">0.250000</scalar>
                     </list>
                  </list>
                  <atomArray>
                     <atom elementType="Si" id="a1" xFract="0.000000" yFract="0.000000" zFract="0.000000">Si</atom>
                     <atom elementType="Si" id="a2" xFract="0.000000" yFract="0.500000" zFract="0.500000">Si</atom>
                     <atom elementType="Si" id="a3" xFract="0.500000" yFract="0.000000" zFract="0.500000">Si</atom>
                     <atom elementType="Si" id="a4" xFract="0.500000" yFract="0.500000" zFract="0.000000">Si</atom>
                     <atom elementType="Si" id="a5" xFract="0.750000" yFract="0.250000" zFract="0.750000">Si</atom>
                     <atom elementType="Si" id="a6" xFract="0.250000" yFract="0.250000" zFract="0.250000">Si</atom>
                     <atom elementType="Si" id="a7" xFract="0.250000" yFract="0.750000" zFract="0.750000">Si</atom>
                     <atom elementType="Si" id="a8" xFract="0.750000" yFract="0.750000" zFract="0.250000">Si</atom>
                  </atomArray>
               </module>
            </module>    
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="atomtable" pattern="\s+x{20,}x.*" endPattern="\s+x{20,}x.*">    <record repeat="4" />    <record repeat="*" id="atom">\s*x{A,cc:elementType}{I,cc:serial}{F,cc:xFract}{F,cc:yFract}{F,cc:zFract}\s*x.*</record>    <transform process="addChild" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:list" elementName="cml:atom" id="atom" />    <transform process="addAttribute" xpath=".//cml:atom" name="id" value="$string(concat('a', count(preceding::cml:atom)+1))" />    <transform process="addAttribute" xpath=".//cml:atom" name="elementType" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:elementType']/text())" />    <transform process="addAttribute" xpath=".//cml:atom" name="xFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:xFract']/text())" />    <transform process="addAttribute" xpath=".//cml:atom" name="yFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:yFract']/text())" />    <transform process="addAttribute" xpath=".//cml:atom" name="zFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:zFract']/text())" />    <transform process="setValue" xpath=".//cml:atom" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:elementType']/text())" />    <transform process="addChild" xpath="." elementName="cml:atomArray" />    <transform process="move" xpath=".//cml:atom" to="./cml:atomArray" />                
               </template>
           </templateList>
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
