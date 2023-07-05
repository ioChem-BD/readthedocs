.. _final-geometry-d3e30827:

final-geometry
==============

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
   | *source*                                                                                                                   | GRRM log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | final-geometry                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Optimized structure.\*                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | OPTOPTOPT.\*                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | optiStruc.xml                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       Optimized structure, SYMMETRY = C2v 
       C      0.051911596139     -0.000000000000      0.000000000000
       O      1.251598064141      0.000000000000     -0.000000000000
       H     -0.551754830140      0.944696873126     -0.000000000000
       H     -0.551754830140     -0.944696873126     -0.000000000000
       ENERGY    = -114.415498155971
       Spin(**2) =    0.000000000000
       GRADIENT VECTOR
       -0.000015613036
       0.000000000000
       -0.000000000000
       0.000012953701
       -0.000000000000
       0.000000000000
       0.000001329667
       0.000000558707
       0.000000000000
       0.000001329667
       -0.000000558707
       -0.000000000000

       Stationary point was found
       OPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTOPTO
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="">
         <module cmlx:templateRef="final-geometry">
            <scalar cmlx:templateRef="symmetry-group" dataType="xsd:string" dictRef="cc:pointgroup">C2v</scalar>
            <module cmlx:templateRef="molecule">
               <molecule cmlx:templateRef="atom" id="molecule">
                  <atomArray>
                     <atom elementType="C" id="a1" x3="0.0519116" y3="-0.0000" z3="0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                     </atom>
                     <atom elementType="O" id="a2" x3="1.25159806" y3="0.0000" z3="-0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                     </atom>
                     <atom elementType="H" id="a3" x3="-0.55175483" y3="0.94469687" z3="-0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                     </atom>
                     <atom elementType="H" id="a4" x3="-0.55175483" y3="-0.94469687" z3="-0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                     </atom>
                  </atomArray>
                  <bondArray>
                     <bond atomRefs2="a1 a2" order="S" />
                     <bond atomRefs2="a1 a3" order="S" />
                     <bond atomRefs2="a1 a4" order="S" />
                  </bondArray>
                  <formula concise="CH2O">
                     <atomArray count="1 2 1" elementType="C H O" />
                  </formula>
                  <property dictRef="cml:molmass">
                     <scalar units="unit:dalton">28.0101</scalar>
                  </property>
               </molecule>
            </module>
            <scalar cmlx:templateRef="energy" dataType="xsd:double" dictRef="cc:energy" units="nonsi:hartree">-114.415498155971</scalar>
            <scalar cmlx:templateRef="spinsqr" dataType="xsd:double" dictRef="cc:s2">0.000000000000</scalar>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <record id="symmetry-group">\s*Optimized structure,\s*SYMMETRY ={X,cc:pointgroup}</record>  <template id="molecule" pattern=".*" endPattern="ENERGY\s+=.*">    <record makeArray="true" repeat="*" id="atom">\s*{A,compchem:elementType}\s*{F,compchem:x3}\s*{F,compchem:y3}\s*{F,compchem:z3}\s*
               </record>    <transform process="createMolecule" xpath="./cml:list[@cmlx:templateRef='atom']/cml:array" id="molecule" />    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="energy-par" pattern="ENERGY\s+=.*\(.*" endPattern=".*">    <record id="energy">ENERGY\s*=\s*{F,cc:energy}\s*\(.*\)</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="energy" pattern="ENERGY\s*=.*" endPattern=".*">    <record id="energy">ENERGY\s*=\s*{F,cc:energy}</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="spinsqr" pattern="\s*Spin\(\*\*2\)\s*=.*" endPattern=".*">    <record id="spinsqr">\s*Spin\(\*\*2\)\s*=\s*{F,cc:s2}</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="zpve" pattern="\s*Spin\(\*\*2\)\s*=.*" endPattern=".*">    <record id="zpve">ZPVE\s*=\s*{F,cc:zpe.correction}</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="gradient" pattern="GRADIENT VECTOR" endPattern="HESSIAN MATRIX">    <record id="null" />    <record id="gradient-vector" repeat="*" makeArray="true">\s+{F,cc:grad}</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="hessian" pattern="HESSIAN MATRIX\s*" endPattern="NORMAL MODE EIGENVALUE.*" endPattern2="Normal mode eigenvalues.*">    <record id="null" />    <record id="hess" makeArray="true" repeat="*">\s*{1_5F,cc:hessianmatrix}</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <template id="eigenvals" pattern="NORMAL MODE EIGENVALUE.*" endPattern="~">    <record id="null" />    <record id="normal-mode-eigvals" makeArray="true" repeat="*">\s+{1_5F,cc:eigenval}</record>    <transform process="pullupSingleton" xpath="./cml:list" />
           </template>  <transform process="pullup" xpath="./cml:module/cml:scalar" />  <transform process="pullup" xpath="./cml:module/cml:array" />  <transform process="delete" xpath="(//cml:list[@cmlx:templateRef='null'])" />  <transform process="delete" xpath=".//cml:module[count(*)=0]" />  <transform process="pullupSingleton" xpath="./cml:list" />  <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:energy']" value="nonsi:hartree" />
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
