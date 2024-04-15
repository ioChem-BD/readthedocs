.. _frequencies-d3e30997:

frequencies
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
   | *source*                                                                                                                   | GRRM log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | frequencies                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | FREQFREQFREQ.\*                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | FREQFREQFREQ.\*                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | freq.xml                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   FREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQF
   Geometry (Origin = Center of Mass, Axes = Principal Axis), SYMMETRY = Cs  
   C      0.695923922878     -0.078083657444      0.000000000000
   O     -0.593539542416      0.066747898232      0.000000000000
   H     -0.142357946467     -1.016067523497      0.000000000000
   H      1.276014279045      0.886458672976      0.000000000000

                      0               1               2       
   Freq.  :     -2057.48295026    764.48759088   1327.25145851
   Red. M :         1.11011042      1.13331104      1.48466990
   C  - x :       0.0736577931   -0.0000000000    0.1016741031
   C  - y :       0.0269522857   -0.0000000000    0.0816479203
   C  - z :       0.0000000000    0.1063487433   -0.0000000000
   O  - x :       0.0110603025    0.0000000000   -0.1322915082
   O  - y :      -0.0468028304    0.0000000000   -0.0429480082
   O  - z :      -0.0000000000    0.0088125096   -0.0000000000
   H  - x :      -0.9362476713   -0.0000000000   -0.0003848867
   H  - y :       0.2898534479   -0.0000000000    0.1101947651
   H  - z :       0.0000000000   -0.7022360951   -0.0000000000
   H  - x :      -0.1163180795   -0.0000000000    0.8893309965
   H  - y :       0.1320251858   -0.0000000000   -0.4007465080
   H  - z :       0.0000000000   -0.7039010948   -0.0000000000

                      3               4               5       
   Freq.  :      1476.66812187   2636.78083809   2877.67762880
   Red. M :         3.78641458      1.02616200      1.11714936
   C  - x :       0.3645796096   -0.0205570543   -0.0500408456
   C  - y :      -0.1541243024   -0.0022958180   -0.0851005576
   C  - z :       0.0000000000    0.0000000000   -0.0000000000
   O  - x :      -0.2519313691    0.0156845601    0.0017538140
   O  - y :       0.0837797969   -0.0257623597   -0.0119672876
   O  - z :       0.0000000000    0.0000000000    0.0000000000
   H  - x :       0.3509961657    0.2374991109    0.1221460329
   H  - y :       0.1100310570    0.8460836173    0.4395017979
   H  - z :       0.0000000000    0.0000000000    0.0000000000
   H  - x :      -0.6936494699   -0.2416551384    0.4458474423
   H  - y :       0.3954544344   -0.4098803618    0.7637055005
   H  - z :       0.0000000000   -0.0000000000    0.0000000000

   Thermochemistry (use all positive eigenvalues) at  298.15 K,    1.00 Atm
   E(el)         =  -114.276451735640
   ZPVE          =     0.020692289810
   Enthalpie(0K) =  -114.255759445830
   E(tr)         =     0.001416276854
   E(rot)        =     0.001416276854
   E(vib)        =     0.020797050421
   H-E(el)       =     0.024573788698
   Enthalpie     =  -114.251877946942
   S(el)         =     0.000000000000
   S(tr)         =     0.000057576784
   S(rot)        =     0.000027931273 (Symmetry number = 1)
   S(vib)        =     0.000000439335
   G-E(el)       =    -0.001051426350
   Free Energy   =  -114.277503161990

   Small eigenvalues are replaced by MinEigenValue = 0.0000946088 u

   Thermochemistry (after the above replacements) at  298.15 K,    1.00 Atm
   E(el)         =  -114.276451735640
   ZPVE          =     0.020692289810
   Enthalpie(0K) =  -114.255759445830
   E(rot)        =     0.001416276854
   E(vib)        =     0.020797050421
   H-E(el)       =     0.024573788698
   Enthalpie     =  -114.251877946942
   S(el)         =     0.000000000000
   S(tr)         =     0.000057576784
   S(rot)        =     0.000027931273 (Symmetry number = 1)
   S(vib)        =     0.000000439335
   G-E(el)       =    -0.001051426350
   Free Energy   =  -114.277503161990

   FREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQFREQF

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="frequencies">
         <module cmlx:templateRef="frequencies">
            <module cmlx:templateRef="molecule">
               <molecule cmlx:templateRef="atom" id="molecule-rot">
                  <atomArray>
                     <atom elementType="C" id="a1" x3="0.69592392" y3="-0.07808366" z3="0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                     </atom>
                     <atom elementType="O" id="a2" x3="-0.59353954" y3="0.0667479" z3="0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                     </atom>
                     <atom elementType="H" id="a3" x3="-0.14235795" y3="-1.01606752" z3="0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                     </atom>
                     <atom elementType="H" id="a4" x3="1.27601428" y3="0.88645867" z3="0.0000">
                        <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                     </atom>
                  </atomArray>
                  <bondArray>
                     <bond atomRefs2="a1 a2" order="S" />
                     <bond atomRefs2="a1 a3" order="S" />
                     <bond atomRefs2="a1 a4" order="S" />
                     <bond atomRefs2="a2 a3" order="S" />
                  </bondArray>
                  <formula concise="CH2O">
                     <atomArray count="1 2 1" elementType="C H O" />
                  </formula>
                  <property dictRef="cml:molmass">
                     <scalar units="unit:dalton">28.0101</scalar>
                  </property>
               </molecule>
            </module>
            <module cmlx:templateRef="freq-block">
               <array dataType="xsd:integer" dictRef="x:serial" size="6">0 1 2 3 4 5</array>
               <array dataType="xsd:double" dictRef="cc:frequency" size="6">-2057.48295026 764.48759088 1327.25145851 1476.66812187 2636.78083809 2877.67762880</array>
               <array dataType="xsd:double" dictRef="cc:redmass" size="6">1.11011042 1.13331104 1.48466990 3.78641458 1.02616200 1.11714936</array>
               <array dataType="xsd:double" dictRef="cc:displacement" size="72">0.0736577931 0.0269522857 0.0000000000 0.0110603025 -0.0468028304 -0.0000000000 -0.9362476713 0.2898534479 0.0000000000 -0.1163180795 0.1320251858 0.0000000000 -0.0000000000 -0.0000000000 0.1063487433 0.0000000000 0.0000000000 0.0088125096 -0.0000000000 -0.0000000000 -0.7022360951 -0.0000000000 -0.0000000000 -0.7039010948 0.1016741031 0.0816479203 -0.0000000000 -0.1322915082 -0.0429480082 -0.0000000000 -0.0003848867
                  0.1101947651 -0.0000000000 0.8893309965 -0.4007465080 -0.0000000000 0.3645796096 -0.1541243024 0.0000000000 -0.2519313691 0.0837797969 0.0000000000 0.3509961657 0.1100310570 0.0000000000 -0.6936494699 0.3954544344 0.0000000000 -0.0205570543 -0.0022958180 0.0000000000 0.0156845601 -0.0257623597 0.0000000000 0.2374991109 0.8460836173 0.0000000000 -0.2416551384 -0.4098803618 -0.0000000000 -0.0500408456 -0.0851005576 -0.0000000000 0.0017538140 -0.0119672876 0.0000000000 0.1221460329
                  0.4395017979 0.0000000000 0.4458474423 0.7637055005 0.0000000000</array>
            </module>
            <module cmlx:templateRef="thermo">
               <scalar dataType="xsd:double" dictRef="cc:temp" units="si:k">298.15</scalar>
               <scalar dataType="xsd:double" dictRef="cc:press" units="nonsi:atm">1.00</scalar>
               <list cmlx:templateRef="state" />
               <scalar cmlx:templateRef="energy" dataType="xsd:double" dictRef="cc:energy" units="nonsi:hartree">-114.276451735640</scalar>
               <scalar cmlx:templateRef="zpe" dataType="xsd:double" dictRef="cc:zpe.correction" units="nonsi:hartree">0.020692289810</scalar>
               <scalar cmlx:templateRef="elec-zpe" dataType="xsd:double" dictRef="cc:zpe.sumelectzpe" units="nonsi:hartree">-114.255759445830</scalar>
               <scalar cmlx:templateRef="thermal-tr" dataType="xsd:double" dictRef="cc:ethermo.trans" units="nonsi:hartree">0.001416276854</scalar>
               <scalar cmlx:templateRef="thermal-rot" dataType="xsd:double" dictRef="cc:ethermo.rot" units="nonsi:hartree">0.001416276854</scalar>
               <scalar cmlx:templateRef="thermal-vib" dataType="xsd:double" dictRef="cc:ethermo.vib" units="nonsi:hartree">0.020797050421</scalar>
               <scalar cmlx:templateRef="enthalpy-corr" dataType="xsd:double" dictRef="cc:zpe.thermalcorrenthalpy" units="nonsi:hartree">0.024573788698</scalar>
               <scalar cmlx:templateRef="enthalpy" dataType="xsd:double" dictRef="cc:zpe.sumelectthermalent" units="nonsi:hartree">-114.251877946942</scalar>
               <scalar cmlx:templateRef="entropy-el" dataType="xsd:double" dictRef="cc:s.elect" units="nonsi2:hartree.K-1">0.000000000000</scalar>
               <scalar cmlx:templateRef="entropy-tr" dataType="xsd:double" dictRef="cc:s.trans" units="nonsi2:hartree.K-1">0.000057576784</scalar>
               <scalar cmlx:templateRef="entropy-rot" dataType="xsd:double" dictRef="cc:s.rot" units="nonsi2:hartree.K-1">0.000027931273</scalar>
               <scalar dataType="xsd:integer" dictRef="cc:symmnumber" units="nonsi2:hartree.K-1">1</scalar>
               <list cmlx:templateRef="entropy-rot" />
               <scalar cmlx:templateRef="entropy-vib" dataType="xsd:double" dictRef="cc:s.vib" units="nonsi2:hartree.K-1">0.000000439335</scalar>
               <scalar cmlx:templateRef="gibbs-corr" dataType="xsd:double" dictRef="cc:zpe.thermalcorrgfe" units="nonsi:hartree">-0.001051426350</scalar>
               <scalar cmlx:templateRef="gibbs" dataType="xsd:double" dictRef="cc:zpe.sumelectthermalfe" units="nonsi:hartree">-114.277503161990</scalar>
            </module>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <record id="null" repeat="2" />
   <template id="molecule" pattern="[A-Za-z]{1,2}\s+.*" endPattern="Freq\..*" endOffset="-2">  <record makeArray="true" repeat="*" id="atom">\s*{A,compchem:elementType}\s*{F,compchem:x3}\s*{F,compchem:y3}\s*{F,compchem:z3}\s*
           </record>  <transform process="createMolecule" xpath="./cml:list[@cmlx:templateRef='atom']/cml:array" id="molecule-rot" />  <transform process="pullupSingleton" xpath="./cml:list" />
       </template>
   <record id="null" repeat="1" />
   <template id="freq-block" pattern="Freq\..*" endPattern="Freq\..*" endPattern2="Thermochemistry.*" repeat="*" offset="-1">  <record makeArray="true" id="serial">{1_3I,x:serial}</record>  <record makeArray="true" id="freq">Freq\.\s+:\s+{1_3F,cc:frequency}</record>  <record makeArray="true" id="redmass">Red\. M :\s+{1_3F,cc:redmass}</record>  <transform process="pullupSingleton" xpath="./cml:list" />  <templateList>    <template id="displs-3" pattern="[A-Z].*\- [xyz]\s+:\s+{3}.*">      <record makeArray="true" id="displ-all" repeat="*">[A-Z].*\- [xyz]\s+:\s*{F,cc:displace1}\s*{F,cc:displace2}\s*{F,cc:displace3}\s*</record>
               </template>    <template id="displs-2" pattern="[A-Z].*\- [xyz]\s+:\s+{2}.*">      <record makeArray="true" id="displ-all" repeat="*">[A-Z].*\- [xyz]\s+:\s*{F,cc:displace1}\s*{F,cc:displace2}\s*</record>
               </template>    <template id="displs-1" pattern="[A-Z].*\- [xyz]\s+:\s+{1}.*">      <record makeArray="true" id="displ-all" repeat="*">[A-Z].*\- [xyz]\s+:\s*{F,cc:displace1}\s*</record>
               </template>
           </templateList>  <transform process="joinArrays" xpath=".//cml:array[starts-with(@dictRef,'cc:displace')]" />  <transform process="pullupSingleton" xpath="./cml:list" />  <record id="null" repeat="1" />
       </template>
   <transform process="joinArrays" xpath=".//cml:array[starts-with(@dictRef,'cc:displace')]" />
   <transform process="joinArrays" xpath=".//cml:array[@dictRef='x:serial']" />
   <transform process="joinArrays" xpath=".//cml:array[@dictRef='cc:frequency']" />
   <transform process="joinArrays" xpath=".//cml:array[@dictRef='cc:redmass']" />
   <transform process="addUnits" xpath="./cml:array[@dictRef='cc:frequency']" value="nonsi:cm-1" />
   <template id="thermo" pattern="Thermochemistry.*after.*" endPattern="~">  <record id="state">Thermochemistry.*at\s*{F,cc:temp}\s*K,\s*{F,cc:press}\s*Atm\s*</record>  <record id="energy">E\(el\)\s+=\s+{F,cc:energy}</record>  <record id="zpe">ZPVE\s+=\s+{F,cc:zpe.correction}</record>  <record id="elec-zpe">Enthalpie\(0K\)\s+=\s+{F,cc:zpe.sumelectzpe}</record>  <record id="thermal-tr">E\(tr\)\s+=\s+{F,cc:ethermo.trans}</record>  <record id="thermal-rot">E\(rot\)\s+=\s+{F,cc:ethermo.rot}</record>  <record id="thermal-vib">E\(vib\)\s+=\s+{F,cc:ethermo.vib}</record>  <record id="enthalpy-corr">H-E\(el\)\s+=\s+{F,cc:zpe.thermalcorrenthalpy}</record>  <record id="enthalpy">Enthalpie\s+=\s+{F,cc:zpe.sumelectthermalent}</record>  <record id="entropy-el">S\(el\)\s+=\s+{F,cc:s.elect}</record>  <record id="entropy-tr">S\(tr\)\s+=\s+{F,cc:s.trans}</record>  <record id="entropy-rot">S\(rot\)\s+=\s+{F,cc:s.rot}\s+\(Symmetry number\s+={I,cc:symmnumber}.*</record>  <record id="entropy-vib">S\(vib\)\s+=\s+{F,cc:s.vib}</record>  <record id="gibbs-corr">G-E\(el\)\s+=\s+{F,cc:zpe.thermalcorrgfe}</record>  <record id="gibbs">Free Energy\s+=\s+{F,cc:zpe.sumelectthermalfe}</record>  <transform process="pullupSingleton" xpath="./cml:list" />  <transform process="pullup" xpath="./cml:list/cml:scalar" />  <transform process="addAttribute" xpath="./cml:scalar[@dictRef='cc:s.rot']" name="cmlx:templateRef" value="entropy-rot" />  <transform process="addUnits" xpath="./cml:scalar[@dictRef='cc:energy']" value="nonsi:hartree" />  <transform process="addUnits" xpath="./cml:scalar[starts-with(@dictRef,'cc:zpe')]" value="nonsi:hartree" />  <transform process="addUnits" xpath="./cml:scalar[starts-with(@dictRef,'cc:ethermo')]" value="nonsi:hartree" />  <transform process="addUnits" xpath="./cml:scalar[starts-with(@dictRef,'cc:s')]" value="nonsi2:hartree.K-1" />  <transform process="addUnits" xpath="./cml:scalar[@dictRef='cc:temp']" value="si:k" />  <transform process="addUnits" xpath="./cml:scalar[@dictRef='cc:press']" value="nonsi:atm" />
       </template>
   <transform process="delete" xpath="(//cml:list[@cmlx:templateRef='null'])" />
   <transform process="pullupSingleton" xpath="./cml:list" />
   <transform process="move" xpath="./cml:module//cml:array[@dictRef='cc:displace1']" to="(./cml:module[@cmlx:templateRef='freq-block'])[1]" />
   <transform process="delete" xpath="(.//cml:module[@cmlx:templateRef='displs-3'])" />
   <transform process="delete" xpath="(.//cml:module[@cmlx:templateRef='freq-block'])[count(*)=0]" />
   <transform process="createArray" from=".//cml:module[@cmlx:templateRef='freq-block']/cml:array[@dictRef='cc:displace1']" xpath="." dictRef="cc:displacement" dataType="xsd:double" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
