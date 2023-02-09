.. _nuclear.coordinates-d3e6979:

nuclear.coordinates
===================

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
   | *source*                                                                                                                   | AMS ADF log                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | nuclear.coordinates                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | NMR nuclear coordinates                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s+NUCLEAR&#92;sCOORDINATES&#92;s*&#92;(ANGSTROMS&#92;).\*                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*={20,}.\*                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | nmr/nuclear.coordinates.xml                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                        NUCLEAR COORDINATES (ANGSTROMS):
                    --------------------------------
    
                    C  (  1):       4.7284      2.1304      0.0000
                    O  (  2):       3.3981      2.6699      0.0000
                    O  (  3):       1.6678     -2.3615      2.9062
                    O  (  4):      -3.2967     -2.4238      0.0000
                    O  (  5):      -1.7912      2.3132     -2.9097
                    O  (  6):      -1.7912      2.3132      2.9097
                    O  (  7):       1.6678     -2.3615     -2.9062
                    O  (  8):      -0.0281      0.0021      2.6674
                    O  (  9):      -0.7233     -2.1541      1.3169
                    O  ( 10):       1.5569     -2.1452      0.0000
                    O  ( 11):       2.3732     -0.0232      1.4424
                    O  ( 12):       0.6437      2.3055      1.4416
                    O  ( 13):      -2.2911     -0.0394      1.3174
                    O  ( 14):      -0.7233     -2.1541     -1.3169
                    O  ( 15):       2.3732     -0.0232     -1.4424
                    O  ( 16):      -1.6234      2.1418      0.0000
                    O  ( 17):      -2.2911     -0.0394     -1.3174
                    O  ( 18):      -0.0281      0.0021     -2.6674
                    O  ( 19):       0.6437      2.3055     -1.4416
                    O  ( 20):       0.0614      0.0669      0.0000
                    Ti ( 21):       1.8539      1.4022      0.0000
                    W  ( 22):      -0.9833      1.3894      1.6824
                    W  ( 23):      -1.9014     -1.3901      0.0000
                    W  ( 24):       1.0249     -1.3118     -1.6819
                    W  ( 25):       1.0249     -1.3118      1.6819
                    W  ( 26):      -0.9833      1.3894     -1.6824
                    H  ( 27):       4.9274      1.5192      0.8941
                    H  ( 28):       4.9274      1.5192     -0.8941
                    H  ( 29):       5.4260      2.9795      0.0000
    
                 ==================================================
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="nuclear.coordinates">
           <module cmlx:lineCount="34" cmlx:templateRef="nuclear.coordinates">
               <molecule id="coordinates.nmr">
                   <atomArray>
                       <atom id="a1" elementType="C" x3="4.7284" y3="2.1304" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                       </atom>
                       <atom id="a2" elementType="O" x3="3.3981" y3="2.6699" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">2</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a3" elementType="O" x3="1.6678" y3="-2.3615" z3="2.9062">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">3</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a4" elementType="O" x3="-3.2967" y3="-2.4238" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">4</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a5" elementType="O" x3="-1.7912" y3="2.3132" z3="-2.9097">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">5</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a6" elementType="O" x3="-1.7912" y3="2.3132" z3="2.9097">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">6</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a7" elementType="O" x3="1.6678" y3="-2.3615" z3="-2.9062">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">7</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a8" elementType="O" x3="-0.0281" y3="0.0021" z3="2.6674">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">8</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a9" elementType="O" x3="-0.7233" y3="-2.1541" z3="1.3169">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">9</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a10" elementType="O" x3="1.5569" y3="-2.1452" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">10</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a11" elementType="O" x3="2.3732" y3="-0.0232" z3="1.4424">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">11</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a12" elementType="O" x3="0.6437" y3="2.3055" z3="1.4416">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">12</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a13" elementType="O" x3="-2.2911" y3="-0.0394" z3="1.3174">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">13</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a14" elementType="O" x3="-0.7233" y3="-2.1541" z3="-1.3169">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">14</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a15" elementType="O" x3="2.3732" y3="-0.0232" z3="-1.4424">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">15</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a16" elementType="O" x3="-1.6234" y3="2.1418" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">16</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a17" elementType="O" x3="-2.2911" y3="-0.0394" z3="-1.3174">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">17</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a18" elementType="O" x3="-0.0281" y3="0.0021" z3="-2.6674">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">18</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a19" elementType="O" x3="0.6437" y3="2.3055" z3="-1.4416">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">19</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a20" elementType="O" x3="0.0614" y3="0.0669" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">20</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                       </atom>
                       <atom id="a21" elementType="Ti" x3="1.8539" y3="1.4022" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">21</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">22</scalar>
                       </atom>
                       <atom id="a22" elementType="W" x3="-0.9833" y3="1.3894" z3="1.6824">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">22</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">74</scalar>
                       </atom>
                       <atom id="a23" elementType="W" x3="-1.9014" y3="-1.3901" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">23</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">74</scalar>
                       </atom>
                       <atom id="a24" elementType="W" x3="1.0249" y3="-1.3118" z3="-1.6819">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">24</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">74</scalar>
                       </atom>
                       <atom id="a25" elementType="W" x3="1.0249" y3="-1.3118" z3="1.6819">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">25</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">74</scalar>
                       </atom>
                       <atom id="a26" elementType="W" x3="-0.9833" y3="1.3894" z3="-1.6824">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">26</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">74</scalar>
                       </atom>
                       <atom id="a27" elementType="H" x3="4.9274" y3="1.5192" z3="0.8941">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">27</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                       </atom>
                       <atom id="a28" elementType="H" x3="4.9274" y3="1.5192" z3="-0.8941">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">28</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                       </atom>
                       <atom id="a29" elementType="H" x3="5.426" y3="2.9795" z3="0.0">
                           <scalar dataType="xsd:integer" dictRef="cc:serial">29</scalar>
                           <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                       </atom>
                   </atomArray>
                   <formula formalCharge="0" concise="C 1 H 3 O 19 Ti 1 W 5">
                       <atomArray elementType="C H O Ti W" count="1.0 3.0 19.0 1.0 5.0" />
                   </formula>
                   <bondArray>
                       <bond atomRefs2="a1 a2" id="a1_a2" order="S" />
                       <bond atomRefs2="a1 a27" id="a1_a27" order="S" />
                       <bond atomRefs2="a1 a28" id="a1_a28" order="S" />
                       <bond atomRefs2="a1 a29" id="a1_a29" order="S" />
                       <bond atomRefs2="a2 a21" id="a2_a21" order="S" />
                       <bond atomRefs2="a3 a25" id="a3_a25" order="S" />
                       <bond atomRefs2="a4 a23" id="a4_a23" order="S" />
                       <bond atomRefs2="a5 a26" id="a5_a26" order="S" />
                       <bond atomRefs2="a6 a22" id="a6_a22" order="S" />
                       <bond atomRefs2="a7 a24" id="a7_a24" order="S" />
                       <bond atomRefs2="a8 a22" id="a8_a22" order="S" />
                       <bond atomRefs2="a8 a25" id="a8_a25" order="S" />
                       <bond atomRefs2="a9 a23" id="a9_a23" order="S" />
                       <bond atomRefs2="a9 a25" id="a9_a25" order="S" />
                       <bond atomRefs2="a10 a24" id="a10_a24" order="S" />
                       <bond atomRefs2="a10 a25" id="a10_a25" order="S" />
                       <bond atomRefs2="a11 a21" id="a11_a21" order="S" />
                       <bond atomRefs2="a11 a25" id="a11_a25" order="S" />
                       <bond atomRefs2="a12 a21" id="a12_a21" order="S" />
                       <bond atomRefs2="a12 a22" id="a12_a22" order="S" />
                       <bond atomRefs2="a13 a22" id="a13_a22" order="S" />
                       <bond atomRefs2="a13 a23" id="a13_a23" order="S" />
                       <bond atomRefs2="a14 a23" id="a14_a23" order="S" />
                       <bond atomRefs2="a14 a24" id="a14_a24" order="S" />
                       <bond atomRefs2="a15 a21" id="a15_a21" order="S" />
                       <bond atomRefs2="a15 a24" id="a15_a24" order="S" />
                       <bond atomRefs2="a16 a22" id="a16_a22" order="S" />
                       <bond atomRefs2="a16 a26" id="a16_a26" order="S" />
                       <bond atomRefs2="a17 a23" id="a17_a23" order="S" />
                       <bond atomRefs2="a17 a26" id="a17_a26" order="S" />
                       <bond atomRefs2="a18 a24" id="a18_a24" order="S" />
                       <bond atomRefs2="a18 a26" id="a18_a26" order="S" />
                       <bond atomRefs2="a19 a21" id="a19_a21" order="S" />
                       <bond atomRefs2="a19 a26" id="a19_a26" order="S" />
                       <bond atomRefs2="a20 a21" id="a20_a21" order="S" />
                       <bond atomRefs2="a20 a22" id="a20_a22" order="S" />
                       <bond atomRefs2="a20 a23" id="a20_a23" order="S" />
                       <bond atomRefs2="a20 a24" id="a20_a24" order="S" />
                       <bond atomRefs2="a20 a25" id="a20_a25" order="S" />
                       <bond atomRefs2="a20 a26" id="a20_a26" order="S" />
                       <bond atomRefs2="a21 a22" id="a21_a22" order="S" />
                       <bond atomRefs2="a21 a24" id="a21_a24" order="S" />
                       <bond atomRefs2="a21 a25" id="a21_a25" order="S" />
                       <bond atomRefs2="a21 a26" id="a21_a26" order="S" />
                       <bond atomRefs2="a22 a23" id="a22_a23" order="S" />
                       <bond atomRefs2="a22 a25" id="a22_a25" order="S" />
                       <bond atomRefs2="a22 a26" id="a22_a26" order="S" />
                       <bond atomRefs2="a23 a24" id="a23_a24" order="S" />
                       <bond atomRefs2="a23 a25" id="a23_a25" order="S" />
                       <bond atomRefs2="a23 a26" id="a23_a26" order="S" />
                       <bond atomRefs2="a24 a25" id="a24_a25" order="S" />
                       <bond atomRefs2="a24 a26" id="a24_a26" order="S" />
                   </bondArray>
                   <property dictRef="cml:molmass">
                       <scalar dataType="xsd:double" units="unit:dalton">1286.09012</scalar>
                   </property>
               </molecule>
           </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="3" />
   <record id="atom" makeArray="true" repeat="*">{A,cc:elementType}\({I,cc:serial}\):{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>
   <transform process="createMolecule" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:array" id="coordinates.nmr" />
   <transform process="pullup" xpath=".//cml:molecule[@id='coordinates.nmr']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
