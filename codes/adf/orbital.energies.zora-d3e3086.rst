.. _orbital.energies.zora-d3e3086:

orbital.energies.zora
=====================

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
   | id                                | orbital.energies.zora             |
   +-----------------------------------+-----------------------------------+
   | name                              | Scaled ZORA Orbital Energies, per |
   |                                   | Irrep and Spin                    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Scaled\sZORA\sOrbital\sEn     |
   |                                   | ergies,\sper\sIrrep\sand\sSpin.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$.*$\s*={1,10}.\*             |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*$\s*={1,10}.\*                |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | results/orbital.energies.zora.xml |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Scaled ZORA Orbital Energies, per Irrep and Spin:
    =================================================
                           Occup              E (au)              E (eV)       Diff (eV) with prev. cycle
                           -----      --------------------        ------       --------------------------
    A
                203        2.000     -0.26799453494505E+00        -7.293              -8.29E-06
                204        2.000     -0.26787674718554E+00        -7.289              -9.53E-06
                205        2.000     -0.26543621800800E+00        -7.223              -5.77E-06
                206        2.000     -0.26542577295741E+00        -7.223              -2.83E-06
                207        2.000     -0.26534384981149E+00        -7.220              -4.78E-06
                208        2.000     -0.25938418557305E+00        -7.058              -4.71E-06
                209        2.000     -0.25930913648310E+00        -7.056              -4.44E-06
                210        2.000     -0.25909320570560E+00        -7.050              -4.24E-06
                211        2.000     -0.24962811826665E+00        -6.793              -3.74E-06
                212        2.000     -0.24954935473765E+00        -6.791              -5.27E-06
                213        0.000     -0.17159990985412E+00        -4.669
                214        0.000     -0.17151397062575E+00        -4.667
                215        0.000     -0.15871426935881E+00        -4.319
                216        0.000     -0.15852383265612E+00        -4.314
                217        0.000     -0.15838074437314E+00        -4.310
                218        0.000     -0.14101919604084E+00        -3.837
                219        0.000     -0.14083030492318E+00        -3.832
                220        0.000     -0.14077423190854E+00        -3.831
                221        0.000     -0.13886798092112E+00        -3.779
                222        0.000     -0.13641178885529E+00        -3.712
     
    HOMO :      212 A                -0.24954935473765E+00
    LUMO :      213 A                -0.17159990985412E+00
     
    cosmo_calcen: 0.5 (esolb+esolc) (Hartrees) =   -0.376338

    Solvation energy (screening term,uncorrected) =   -236.155985 kcal/mol

    Solvation energy (dispersion and cavitation terms) =      1.103434 kcal/mol
    Solvation Energy Contributions (Hartrees)
             esola   esolb+esolc
        0.37633848   -0.75267695
    esol last cycle   -0.37633848


    Scaled ZORA Orbital Energies of the Core Orbitals:
    ================================================== 
       

**Input.**

::

    Scaled ZORA Orbital Energies, per Irrep and Spin:
    =================================================
                           Occup              E (au)              E (eV)       Diff (eV) with prev. cycle
                           -----      --------------------        ------       --------------------------
    S
                  1        2.000     -0.88681592669345E+00       -24.131              -2.56E-11
                  2        0.000      0.89840433219722E+00        24.447
                  3        0.000      0.29556668859678E+02       804.278
    P
                  1        4.000     -0.33794335091447E+00        -9.196              -2.46E-11
                  2        0.000      0.35464320986905E+00         9.650
                  3        0.000      0.38296134087112E+01       104.209
    D
                  1        0.000      0.10608708589688E+01        28.868


    Partially Occupied:
                  1 P                -0.33794335091447E+00
     
    HOMO :        1 S                -0.88681592669345E+00
    LUMO :        2 P                 0.35464320986905E+00
     


    Orbital Energies, all Irreps
    ========================================
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="orbital.energies.zora">   
           <module cmlx:templateRef="orbital.energies.zora">
               <list cmlx:templateRef="energies" dictRef="energies">
                  <array dataType="xsd:integer" dictRef="cc:serial" size="20">203 204 205 206 207 208 209 210 211 212 213 214 215 216 217 218 219 220 221 222</array>
                  <array dataType="xsd:double" dictRef="cc:occup" size="20">2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 2.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000 0.000</array>
                  <array dataType="xsd:double" dictRef="cc:energy" size="20" units="nonsi:electronvolt">-7.293 -7.289 -7.223 -7.223 -7.220 -7.058 -7.056 -7.050 -6.793 -6.791 -4.669 -4.667 -4.319 -4.314 -4.310 -3.837 -3.832 -3.831 -3.779 -3.712</array>               
                  <array dataType="xsd:string" dictRef="cc:irrep" size="20">A A A A A A A A A A A A A A A A A A A A</array>                           
               </list>
            </module>      
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="orbital.energies.zora">
           <module cmlx:templateRef="orbital.energies.zora">
               <list cmlx:templateRef="energies" dictRef="energies">
                  <array dataType="xsd:integer" dictRef="cc:serial" size="7">1 2 3 1 2 3 1</array>
                  <array dataType="xsd:double" dictRef="cc:occup" size="7">2.000 0.000 0.000 4.000 0.000 0.000 0.000</array>
                  <array dataType="xsd:double" dictRef="cc:energy" size="7" units="nonsi:electronvolt">-24.131 24.447 804.278 -9.196 9.650 104.209 28.868</array>
                  <array dataType="xsd:string" dictRef="cc:irrep" size="7">S S S P P P D</array>
               </list>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="4" />
   <templateList>  <template id="section" pattern="\s*\S+\s*" endPattern="\s*\S+\s*" endPattern2="~" endOffset="0" repeat="*">    <record>{A,cc:irrep}</record>    <record repeat="*">{I,cc:serial}{F,cc:occup}\s+\S+\s+{F,cc:energy}.*</record>    <transform process="addChild" xpath="./cml:list/cml:list" elementName="cml:scalar" dictRef="cc:irrep" />    <transform process="addAttribute" xpath=".//cml:scalar[@dictRef='cc:irrep']" name="dataType" value="xsd:string" />    <transform process="setValue" xpath=".//cml:scalar[@dictRef='cc:irrep']" value="$string(ancestor::cml:module[@cmlx:templateRef='section']//cml:scalar[@dictRef='cc:irrep' and text() != ''])" />                       
           </template>
       </templateList>
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='section']/cml:list/cml:scalar" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:serial']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:spin']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:occup']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:energy']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:irrep']" />
   <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:energy']" value="nonsi:electronvolt" />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="delete" xpath=".//cml:module" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0 ]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0 ]" />
   <transform process="addChild" xpath="." elementName="cml:list" dictRef="energies" />
   <transform process="addAttribute" xpath="./cml:list[@dictRef='energies']" name="cmlx:templateRef" value="energies" />
   <transform process="move" xpath=".//cml:array" to=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
