.. _geometry-d3e1550:

geometry
========

.. table:: Implementation level

   +-----------------------------------+-----------------------------------+
   | Type                              | Status                            |
   +===================================+===================================+
   | CML extraction template           | |image0|                          |
   +-----------------------------------+-----------------------------------+
   | HTML5 representation              | |image1|                          |
   +-----------------------------------+-----------------------------------+

.. table:: Template attributes

   +-----------------------------------+-----------------------------------+
   | Attribute                         | Value                             |
   +===================================+===================================+
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | geometry                          |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\sG\sE\sO\sM\sE\sT\sR\sY.*(3     |
   |                                   | D\s*Molecule|Planar\s*Molecule|Li |
   |                                   | near\s*Molecule|Single\s*Atom).\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s+[0-9]+.*$\s*$\s\*             |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | geometry.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    ===============
    G E O M E T R Y  ***  3D  Molecule  ***
    ===============
     

    ATOMS
    =====                            X Y Z                    CHARGE
                                   (Angstrom)             Nucl     +Core       At.Mass
                          --------------------------    ----------------       -------
       1  Lu              0.5510   -0.8582    1.7445     71.00     17.00      174.9408
       2  Lu             -1.3822    1.4940   -0.0964     71.00     17.00      174.9408
       3  Lu              0.5842   -0.9156   -1.8136     71.00     17.00      174.9408
       4  N               0.1194    0.0590   -0.0694      7.00      5.00       14.0031
       5  N               1.2612   -3.1890   -5.7161      7.00      5.00       14.0031
       6  H               0.1199   -1.5550   -6.4368      1.00      1.00        1.0078
       7  H               1.8649   -1.1924   -6.2222      1.00      1.00        1.0078
       8  H               2.3966   -4.3625   -4.3698      1.00      1.00        1.0078
       9  H               3.2480   -2.9007   -4.9668      1.00      1.00        1.0078
      10  H               2.6474   -3.3171   -7.3537      1.00      1.00        1.0078
      11  H               0.9297   -3.6743   -7.7381      1.00      1.00        1.0078
      12  H               1.8943   -4.8586   -6.8242      1.00      1.00        1.0078
      13  C               0.9985   -1.7560   -5.8088      6.00      4.00       12.0000
      14  C               2.2587   -3.3131   -4.6649      6.00      4.00       12.0000
      15  C               1.7107   -3.7836   -6.9715      6.00      4.00       12.0000
      16  C              -2.8978    3.2168   -0.7460      6.00      4.00       12.0000
      17  C              -3.3899    2.0349   -1.4821      6.00      4.00       12.0000
      18  C              -2.6810    1.6122   -2.6756      6.00      4.00       12.0000
      19  C               3.9518   -0.8543   -0.7169      6.00      4.00       12.0000
      20  C              -2.8553    3.1643    0.7715      6.00      4.00       12.0000
      21  C              -2.6687    1.5849    2.7059      6.00      4.00       12.0000
      22  C              -3.3582    2.0001    1.5019      6.00      4.00       12.0000
      23  C              -3.9599    0.9360    0.7401      6.00      4.00       12.0000
      24  C              -3.8899   -0.4381   -1.1609      6.00      4.00       12.0000


       

**Output text.**

.. code:: xml

   <comment class="example.output" id="geometry">
         <module cmlx:lineCount="33" cmlx:templateRef="geometry">
           <molecule id="coordinates">
             <atomArray>
               <atom id="a1" elementType="Lu" x3="0.551" y3="-0.8582" z3="1.7445">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">71</scalar>
               </atom>
               <atom id="a2" elementType="Lu" x3="-1.3822" y3="1.494" z3="-0.0964">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">2</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">71</scalar>
               </atom>
               <atom id="a3" elementType="Lu" x3="0.5842" y3="-0.9156" z3="-1.8136">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">3</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">71</scalar>
               </atom>
               <atom id="a4" elementType="N" x3="0.1194" y3="0.059" z3="-0.0694">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">4</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">7</scalar>
               </atom>
               <atom id="a5" elementType="N" x3="1.2612" y3="-3.189" z3="-5.7161">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">5</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">7</scalar>
               </atom>
               <atom id="a6" elementType="H" x3="0.1199" y3="-1.555" z3="-6.4368">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">6</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a7" elementType="H" x3="1.8649" y3="-1.1924" z3="-6.2222">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">7</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a8" elementType="H" x3="2.3966" y3="-4.3625" z3="-4.3698">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">8</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a9" elementType="H" x3="3.248" y3="-2.9007" z3="-4.9668">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">9</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a10" elementType="H" x3="2.6474" y3="-3.3171" z3="-7.3537">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">10</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a11" elementType="H" x3="0.9297" y3="-3.6743" z3="-7.7381">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">11</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a12" elementType="H" x3="1.8943" y3="-4.8586" z3="-6.8242">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">12</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
               </atom>
               <atom id="a13" elementType="C" x3="0.9985" y3="-1.756" z3="-5.8088">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">13</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a14" elementType="C" x3="2.2587" y3="-3.3131" z3="-4.6649">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">14</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a15" elementType="C" x3="1.7107" y3="-3.7836" z3="-6.9715">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">15</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a16" elementType="C" x3="-2.8978" y3="3.2168" z3="-0.746">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">16</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a17" elementType="C" x3="-3.3899" y3="2.0349" z3="-1.4821">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">17</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a18" elementType="C" x3="-2.681" y3="1.6122" z3="-2.6756">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">18</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a19" elementType="C" x3="3.9518" y3="-0.8543" z3="-0.7169">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">19</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a20" elementType="C" x3="-2.8553" y3="3.1643" z3="0.7715">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">20</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a21" elementType="C" x3="-2.6687" y3="1.5849" z3="2.7059">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">21</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a22" elementType="C" x3="-3.3582" y3="2.0001" z3="1.5019">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">22</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a23" elementType="C" x3="-3.9599" y3="0.936" z3="0.7401">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">23</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
               <atom id="a24" elementType="C" x3="-3.8899" y3="-0.4381" z3="-1.1609">
                 <scalar dataType="xsd:integer" dictRef="cc:serial">24</scalar>
                 <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
               </atom>
             </atomArray>
             <formula formalCharge="0" concise="C 12 H 7 Lu 3 N 2">
               <atomArray elementType="C H Lu N" count="12.0 7.0 3.0 2.0" />
             </formula>
             <bondArray>
               <bond atomRefs2="a1 a2" id="a1_a2" order="S" />
               <bond atomRefs2="a1 a3" id="a1_a3" order="S" />
               <bond atomRefs2="a1 a4" id="a1_a4" order="S" />
               <bond atomRefs2="a2 a3" id="a2_a3" order="S" />
               <bond atomRefs2="a2 a4" id="a2_a4" order="S" />
               <bond atomRefs2="a2 a16" id="a2_a16" order="S" />
               <bond atomRefs2="a2 a17" id="a2_a17" order="S" />
               <bond atomRefs2="a2 a18" id="a2_a18" order="S" />
               <bond atomRefs2="a2 a20" id="a2_a20" order="S" />
               <bond atomRefs2="a2 a22" id="a2_a22" order="S" />
               <bond atomRefs2="a2 a23" id="a2_a23" order="S" />
               <bond atomRefs2="a3 a4" id="a3_a4" order="S" />
               <bond atomRefs2="a5 a13" id="a5_a13" order="S" />
               <bond atomRefs2="a5 a14" id="a5_a14" order="S" />
               <bond atomRefs2="a5 a15" id="a5_a15" order="S" />
               <bond atomRefs2="a6 a13" id="a6_a13" order="S" />
               <bond atomRefs2="a7 a13" id="a7_a13" order="S" />
               <bond atomRefs2="a8 a14" id="a8_a14" order="S" />
               <bond atomRefs2="a9 a14" id="a9_a14" order="S" />
               <bond atomRefs2="a10 a15" id="a10_a15" order="S" />
               <bond atomRefs2="a11 a15" id="a11_a15" order="S" />
               <bond atomRefs2="a12 a15" id="a12_a15" order="S" />
               <bond atomRefs2="a16 a17" id="a16_a17" order="S" />
               <bond atomRefs2="a16 a20" id="a16_a20" order="S" />
               <bond atomRefs2="a17 a18" id="a17_a18" order="S" />
               <bond atomRefs2="a20 a22" id="a20_a22" order="S" />
               <bond atomRefs2="a21 a22" id="a21_a22" order="S" />
               <bond atomRefs2="a22 a23" id="a22_a23" order="S" />
             </bondArray>
             <property dictRef="cml:molmass">
               <scalar dataType="xsd:double" units="unit:dalton">704.0983800000001</scalar>
             </property>
           </molecule>
         </module>   
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="coordinates" name="coordinates" pattern="\s*ATOMS.*" endPattern="\s+[0-9]+.*$\s*$\s*" endPattern2="~" endOffset="1">    <record repeat="4" />    <record id="atom" repeat="*" makeArray="true">{I,cc:serial}{A,cc:elementType}{F,cc:x3,unit:angstrom}{F,cc:y3,unit:angstrom}{F,cc:z3,unit:angstrom}.*</record>    <transform process="createMolecule" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:array" id="coordinates" />    <transform process="pullup" repeat="2" xpath=".//cml:molecule" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:module[count(*)=0]" />            
           </template>   
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
