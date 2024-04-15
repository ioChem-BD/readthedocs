.. _castep.cell-d3e51291:

castep.cell
===========

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
   | *source*                                                                                                                   | CASTEP cell                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | castep.cell                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | CASTEP cell                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   %BLOCK LATTICE_CART
          5.430530000000000       0.000000000000000       0.000000000000000
          0.000000000000000       5.430530000000000       0.000000000000000
          0.000000000000000       0.000000000000000       5.430530000000000
   %ENDBLOCK LATTICE_CART

   %BLOCK POSITIONS_FRAC
    Si   0.0000000000000000    0.0000000000000000    0.0000000000000000
    Si   0.0000000000000000    0.4999999999999999    0.4999999999999999
    Si   0.4999999999999999    0.0000000000000000    0.4999999999999999
    Si   0.4999999999999999    0.4999999999999999    0.0000000000000000
    Si   0.7499999999999999    0.2500000000000000    0.7499999999999999
    Si   0.2500000000000000    0.2500000000000000    0.2500000000000000
    Si   0.2500000000000000    0.7499999999999999    0.7499999999999999
    Si   0.7499999999999999    0.7499999999999999    0.2500000000000000
   %ENDBLOCK POSITIONS_FRAC

   %BLOCK KPOINTS_LIST
      0.3750000000000000    0.3750000000000000    0.3750000000000000       0.125000000000000
      0.3750000000000000    0.3750000000000000    0.1250000000000000       0.375000000000000
      0.3750000000000000    0.1250000000000000    0.1250000000000000       0.375000000000000
      0.1250000000000000    0.1250000000000000    0.1250000000000000       0.125000000000000
   %ENDBLOCK KPOINTS_LIST

   %BLOCK SYMMETRY_OPS
          1.000000000000000       0.000000000000000       0.000000000000000
          0.000000000000000       1.000000000000000       0.000000000000000
          0.000000000000000       0.000000000000000       1.000000000000000
          0.000000000000000        0.000000000000000        0.000000000000000
          1.000000000000000       0.000000000000000       0.000000000000000
          ...
          
          1.000000000000000       0.000000000000000       0.000000000000000
          0.500000000000000        0.500000000000000        0.000000000000000
   %ENDBLOCK SYMMETRY_OPS

   #SpaceGroup : 227
   %BLOCK CELL_CONSTRAINTS
          1       1       1
          0       0       0
   %ENDBLOCK CELL_CONSTRAINTS

   FIX_COM : false
   %BLOCK IONIC_CONSTRAINTS
   %ENDBLOCK IONIC_CONSTRAINTS

   %BLOCK EXTERNAL_EFIELD
       0.0000000000     0.0000000000     0.0000000000 
   %ENDBLOCK EXTERNAL_EFIELD

   %BLOCK EXTERNAL_PRESSURE
       0.0000000000    0.0000000000    0.0000000000
                       0.0000000000    0.0000000000
                                       0.0000000000
   %ENDBLOCK EXTERNAL_PRESSURE

   %BLOCK SPECIES_MASS
         Si     28.0849990845
   %ENDBLOCK SPECIES_MASS

   %BLOCK SPECIES_POT
         Si  3|1.8|3.6|5|7|30UU:31UU:32UU[]
   %ENDBLOCK SPECIES_POT

   %BLOCK SPECIES_LCAO_STATES
         Si         2
   %ENDBLOCK SPECIES_LCAO_STATES

       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="castep.cell">
           <module id="castep.cell">         
              <module cmlx:templateRef="lattice">
                 <list dictRef="ca:axis" id="axis">
                    <array dataType="xsd:double" dictRef="cc:latticeA" size="3">5.430530000000000 0.000000000000000 0.000000000000000</array>
                    <array dataType="xsd:double" dictRef="cc:latticeB" size="3">0.000000000000000 5.430530000000000 0.000000000000000</array>
                    <array dataType="xsd:double" dictRef="cc:latticeC" size="3">0.000000000000000 0.000000000000000 5.430530000000000</array>
                 </list>
              </module>
              <module cmlx:templateRef="atoms">
                 <list cmlx:templateRef="atom">
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.0000000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.0000000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.0000000000000000</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.0000000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.4999999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.4999999999999999</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.4999999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.0000000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.4999999999999999</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.4999999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.4999999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.0000000000000000</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.7499999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.2500000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.7499999999999999</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.2500000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.2500000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.2500000000000000</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.2500000000000000</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.7499999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.7499999999999999</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:elementType">Si</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:xFract">0.7499999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:yFract">0.7499999999999999</scalar>
                       <scalar dataType="xsd:double" dictRef="cc:zFract">0.2500000000000000</scalar>
                    </list>
                 </list>
              </module>
              <module cmlx:templateRef="kpoints">
                 <matrix cols="4" dataType="xsd:double" dictRef="ca:kpoints" rows="4">0.3750000000000000 0.3750000000000000 0.3750000000000000 0.125000000000000 0.3750000000000000 0.3750000000000000 0.1250000000000000 0.375000000000000 0.3750000000000000 0.1250000000000000 0.1250000000000000 0.375000000000000 0.1250000000000000 0.1250000000000000 0.1250000000000000 0.125000000000000</matrix>
              </module>
              <molecule id="coordinates">
                 <crystal>
                    <scalar id="sc1" title="a" units="nonsi:angstrom">5.43053</scalar>
                    <scalar id="sc2" title="b" units="nonsi:angstrom">5.43053</scalar>
                    <scalar id="sc3" title="c" units="nonsi:angstrom">5.43053</scalar>
                    <scalar id="sc4" title="alpha" units="nonsi:degree">90.0</scalar>
                    <scalar id="sc5" title="beta" units="nonsi:degree">90.0</scalar>
                    <scalar id="sc6" title="gamma" units="nonsi:degree">90.0</scalar>
                 </crystal>
                 <atomArray>
                    <atom elementType="Si" id="a1" x3="0.0000" xFract="0.0000" y3="0.0000" yFract="0.0000" z3="0.0000" zFract="0.0000" />
                    <atom elementType="Si" id="a2" x3="0.0000" xFract="0.0000" y3="2.715265" yFract="0.5000" z3="2.715265" zFract="0.5000" />
                    <atom elementType="Si" id="a3" x3="2.715265" xFract="0.5000" y3="0.0000" yFract="0.0000" z3="2.715265" zFract="0.5000" />
                    <atom elementType="Si" id="a4" x3="2.715265" xFract="0.5000" y3="2.715265" yFract="0.5000" z3="0.0000" zFract="0.0000" />
                    <atom elementType="Si" id="a5" x3="4.0728975" xFract="0.7500" y3="1.3576325" yFract="0.2500" z3="4.0728975" zFract="0.7500" />
                    <atom elementType="Si" id="a6" x3="1.3576325" xFract="0.2500" y3="1.3576325" yFract="0.2500" z3="1.3576325" zFract="0.2500" />
                    <atom elementType="Si" id="a7" x3="1.3576325" xFract="0.2500" y3="4.0728975" yFract="0.7500" z3="4.0728975" zFract="0.7500" />
                    <atom elementType="Si" id="a8" x3="4.0728975" xFract="0.7500" y3="4.0728975" yFract="0.7500" z3="1.3576325" zFract="0.2500" />
                 </atomArray>
                 <bondArray />
                 <formula concise="Si8">
                    <atomArray count="8" elementType="Si" />
                 </formula>
                 <property dictRef="cml:molmass">
                    <scalar units="unit:dalton">224.684</scalar>
                 </property>
              </molecule>    
           </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="lattice" pattern="\s*\%BLOCK\sLATTICE_CART.*" endPattern="\s*\%ENDBLOCK\sLATTICE_CART.*">    <record repeat="1" />    <record>{3F,cc:latticeA}.*</record>    <record>{3F,cc:latticeB}.*</record>    <record>{3F,cc:latticeC}.*</record>    <transform process="addChild" xpath="." elementName="cml:list" id="axis" />    <transform process="addAttribute" xpath=".//cml:list[@id='axis']" name="dictRef" value="ca:axis" />    <transform process="move" xpath=".//cml:array[@dictRef='cc:latticeA' or @dictRef='cc:latticeB' or @dictRef='cc:latticeC' ]" to=".//cml:list[@id='axis']" />
           </template>  <template id="atoms" pattern="\s*\%BLOCK\sPOSITIONS_FRAC.*" endPattern="\s*\%ENDBLOCK\sPOSITIONS_FRAC.*">    <record repeat="1" />    <record repeat="*" id="atom">\s*{A,cc:elementType}{F,cc:xFract}{F,cc:yFract}{F,cc:zFract}.*</record>    <transform process="addChild" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:list" elementName="cml:atom" id="atom" />    <transform process="addAttribute" xpath=".//cml:atom" name="id" value="$string(concat('a', count(preceding::cml:atom)+1))" />    <transform process="addAttribute" xpath=".//cml:atom" name="elementType" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:elementType']/text())" />    <transform process="addAttribute" xpath=".//cml:atom" name="xFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:xFract']/text())" />    <transform process="addAttribute" xpath=".//cml:atom" name="yFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:yFract']/text())" />    <transform process="addAttribute" xpath=".//cml:atom" name="zFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:zFract']/text())" />    <transform process="setValue" xpath=".//cml:atom" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:elementType']/text())" />    <transform process="addChild" xpath="." elementName="cml:atomArray" />    <transform process="move" xpath=".//cml:atom" to="./cml:atomArray" />
           </template>  <template id="kpoints" pattern="\s*\%BLOCK\sKPOINTS_LIST.*" endPattern="\s*\%ENDBLOCK\sKPOINTS_LIST">    <record repeat="1" />    <record repeat="*">{4F,ca:kpoint}</record>    <transform process="createMatrix" xpath="." from=".//cml:array[@dictRef='ca:kpoint']" dictRef="ca:kpoints" />    <transform process="pullup" xpath=".//cml:matrix" />                        
           </template>
       </templateList>
   <transform process="createCrystal" xpath=".//cml:atomArray" lattice=".//cml:list[@dictRef='ca:axis']" id="coordinates" connect="no" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='atoms']/cml:atomArray" />
   <transform process="move" xpath="//cml:molecule" to="." />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
