.. _structure-d3e31297:

structure
=========

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
   | id                                                                                                                         | structure                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | # Geometry of.\*                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | INITIAL STRUCTURE.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern3                                                                                                                   | INPUT ORIENTATION.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | # Geometry of.\*                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ^&#92;s*$                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | CONNECTION.\*                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | singleStruc.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       # Geometry of EQ 0, SYMMETRY = C2v 
       C      0.051911596139     -0.000000000000      0.000000000000
       O      1.251598064141      0.000000000000     -0.000000000000
       H     -0.551754830140      0.944696873126     -0.000000000000
       H     -0.551754830140     -0.944696873126     -0.000000000000
       Energy    = -114.415498155970 (-114.415498155970 :    0.000000000000)
       Spin(**2) =    0.000000000000
       ZPVE      =    0.026536542348
       Normal mode eigenvalues : nmode = 6
       0.053871195   0.060584067   0.088631469   0.131480115   0.311308040
       0.324295946
       

.. container:: formalpara-title

   **Input**

::

       INITIAL STRUCTURE
       C     -0.064198235583     -0.007930187832     -0.000000000000
       O      1.233143761809      0.016481892179      0.000000000000
       H      0.644724226899      1.031280651044      0.000000000000
       H     -0.513669753124     -1.039832355389      0.000000000000
       ENERGY    = -114.276451735641
       Spin(**2) =    0.000000000000
       GRADIENT VECTOR
       -0.000015411633
       -0.000011833303
       0.000000000000
       0.000003349007
       0.000007583517
       0.000000000000
       0.000015586121
       0.000009500992
       -0.000000000000
       -0.000003523494
       -0.000005251206
       -0.000000000000
       HESSIAN MATRIX
       0.483870417
       0.021477761   0.399410092
       0.000000000   0.000000000   0.031760643
       -0.572059444  -0.025014466   0.000000000   0.573554180
       0.167659525   0.037218727  -0.000000000   0.009670607   0.026493405
       -0.000000000  -0.000000000   0.003555306  -0.000000000   0.000000000
       0.133879425   0.029603924  -0.000000000   0.019884615  -0.110041445
       -0.112346200  -0.161842890   0.000000000   0.044034835  -0.092936388
       0.000000000   0.000000000  -0.017647961  -0.000000000  -0.000000000
       -0.045690398  -0.026067220  -0.000000000  -0.021379351  -0.067288687
       -0.076791086  -0.274785929  -0.000000000  -0.028690976   0.029224256
       -0.000000000   0.000000000  -0.017667987   0.000000000   0.000000000
       0.000306969
       0.000000000  -0.129079016
       -0.000000000   0.061067209   0.252234827
       -0.001910541  -0.000000000   0.000000000   0.009768881
       0.000000000  -0.024685024   0.007244156  -0.000000000   0.091754773
       0.000000000   0.019370312   0.002544451  -0.000000000   0.086111750
       -0.001951734   0.000000000  -0.000000000   0.009789622   0.000000000
       0.243017222
       0.000000000   0.009830099
       NORMAL MODE EIGENVALUE : N_MODE = 6
       -0.160200511   0.022117307   0.066664995   0.082519618   0.263111301
       0.313383199

       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="structure2">
         <module cmlx:templateRef="structure">
            <module cmlx:templateRef="molecule">
               <molecule cmlx:templateRef="atom" id="molecule">
                  <atomArray>
                     <atom elementType="C" id="a1" x3="-0.97636194" y3="0.11153149" z3="-0.33793524">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                     </atom>
                     <atom elementType="O" id="a2" x3="0.74275724" y3="-0.10033779" z3="-0.23073234">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                     </atom>
                     <atom elementType="H" id="a3" x3="0.46752383" y3="0.73164846" z3="0.26582554">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                     </atom>
                     <atom elementType="H" id="a4" x3="0.93150704" y3="-0.88276953" z3="0.31747787">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                     </atom>
                  </atomArray>
                  <bondArray>
                     <bond atomRefs2="a1 a2" order="S" />
                     <bond atomRefs2="a2 a3" order="S" />
                     <bond atomRefs2="a2 a4" order="S" />
                  </bondArray>
                  <formula concise="CH2O">
                     <atomArray count="1 2 1" elementType="C H O" />
                  </formula>
                  <property dictRef="cml:molmass">
                     <scalar units="unit:dalton">28.0101</scalar>
                  </property>
               </molecule>
            </module>
            <scalar cmlx:templateRef="energy" dataType="xsd:double" dictRef="cc:energy" units="nonsi:hartree">-114.136991357592</scalar>
            <scalar cmlx:templateRef="spinsqr" dataType="xsd:double" dictRef="cc:s2">0.000000000000</scalar>
            <array cmlx:templateRef="gradient-vector" dataType="xsd:double" dictRef="cc:grad" size="12">0.000015914887 0.000012610186 0.000002846427 -0.000035628051 0.000081501872 0.000040350355 -0.000005755657 -0.000022336099 -0.000053681663 0.000025468820 -0.000071775959 0.000010484881</array>
            <array cmlx:templateRef="hess" dataType="xsd:double" dictRef="cc:hessianmatrix" size="78">0.044205190 -0.006412971 0.007027217 0.004417132 -0.003502960 0.000597432 -0.049966196 -0.010052197 -0.011353132 0.059532869 0.043423072 0.014713894 0.028617102 -0.120888805 0.552367836 -0.003207739 0.011718116 0.009895864 0.033795717 -0.080345449 0.016720679 0.007300593 0.010504324 0.005664706 0.014638871 -0.060855490 -0.028184625 -0.024077536 0.078496524 -0.226600098 -0.011371698 -0.010415119
               -0.012679097 0.033258263 -0.165062130 -0.010959674 0.009164575 -0.003568324 -0.015231379 0.062826862 0.023845389 0.006443513 -0.001036606 0.052444478 -0.340481633 0.010162306 0.002199962 0.002185801 -0.055700848 0.216790477 0.303129498 0.014871439 -0.019199307 -0.117471227 -0.014454998 0.256478752 -0.126730439 -0.021143154 0.151945345 0.124634197 -0.045459417 -0.003186079 -0.003186035 -0.000743410 0.029377132 0.186098559 -0.007484466 -0.001694029 0.023531903 -0.068805401 -0.186294923
               -0.004232610 -0.010396582 0.014775339 0.049771151 0.335732149 -0.208593856 0.169333782</array>
            <array cmlx:templateRef="normal-mode-eigvals" dataType="xsd:double" dictRef="cc:eigenval" size="6">-0.024704258 0.002537847 0.016029896 0.061744645 0.372987694 0.522395019</array>
         </module>
   </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <template id="label-symmetry" pattern="# Geometry of.*" endPattern=".*">  <record id="label-symmetry"># Geometry of {X,cc:label},\s*SYMMETRY ={X,cc:pointgroup}</record>
       </template>
   <template id="initial-structure" pattern="INITIAL STRUCTURE.*" endPattern=".*">  <record id="null" />
       </template>
   <template id="initial-structure" pattern="INPUT ORIENTATION.*" endPattern=".*">  <record id="null" />
       </template>
   <template id="molecule" pattern=".*" endPattern="ENERGY\s*=.*" endPattern2="Energy.*">  <record makeArray="true" repeat="*" id="atom">\s*{A,compchem:elementType}\s*{F,compchem:x3}\s*{F,compchem:y3}\s*{F,compchem:z3}\s*
           </record>  <transform process="createMolecule" xpath="./cml:list[@cmlx:templateRef='atom']/cml:array" id="molecule" />  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="energy" pattern="(ENERGY|Energy)\s*=.*\(.*" endPattern=".*">  <record id="energy">(ENERGY|Energy)\s*=\s*{F,cc:energy}\s*\(.*\)</record>  <transform process="pullupSingleton" xpath="./cml:list" /> 
        </template>
   <template id="energy" pattern="(ENERGY|Energy)\s*=.*[^\(\n]*$" endPattern=".*">  <record id="energy">(ENERGY|Energy)\s*=\s*{F,cc:energy}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="spin" pattern="Spin\(\*\*2\).*" endPattern=".*">  <record id="spinsqr">\s*Spin\(\*\*2\)\s*=\s*{F,cc:s2}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="zpve" pattern="ZPVE\s*=.*" endPattern=".*">  <record id="zpve">ZPVE\s*=\s*{F,cc:zpe.correction}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="gradient" pattern="GRADIENT VECTOR" endPattern="HESSIAN MATRIX\s*">  <record id="null" />  <record id="gradient-vector" repeat="*" makeArray="true">\s+{F,cc:grad}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="hessian" pattern="HESSIAN MATRIX\s*" endPattern="NORMAL MODE EIGENVALUE.*" endPattern2="Normal mode eigenvalues.*">  <record id="null" />  <record id="hess" makeArray="true" repeat="*">\s*{1_5F,cc:hessianmatrix}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="eigenvals" pattern="NORMAL MODE EIGENVALUE.*" endPattern="~">  <record id="null" repeat="1" />  <record id="normal-mode-eigvals" makeArray="true" repeat="*">\s*{1_5F,cc:eigenval}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <template id="eigenvals" pattern="Normal mode eigenvalues.*" endPattern="~">  <record id="null" repeat="1" />  <record id="normal-mode-eigvals" makeArray="true" repeat="*">\s*{1_5F,cc:eigenval}</record>  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <transform process="pullup" xpath="./cml:module/cml:scalar" />
   <transform process="pullup" xpath="./cml:module/cml:array" />
   <transform process="delete" xpath="(//cml:list[@cmlx:templateRef='null'])" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="pullupSingleton" xpath="./cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:energy']" value="nonsi:hartree" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
