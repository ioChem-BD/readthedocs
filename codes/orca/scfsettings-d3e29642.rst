.. _scfsettings-d3e29642:

scfsettings
===========

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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | scfsettings                       |
   +-----------------------------------+-----------------------------------+
   | name                              | SCF Settings                      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*SCF\sSETTINGS\s*$\s*\-+\s\*   |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s+\*{5,}.\*                     |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\-+.*$\S+.*$\-+.\*               |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | \\s*\*{10,}\s\*                   |
   +-----------------------------------+-----------------------------------+
   | endPattern4                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/scf/scfsettings.xml           |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ------------
   SCF SETTINGS
   ------------
   Hamiltonian:
    Density Functional     Method          .... DFT(GTOs)
    Exchange Functional    Exchange        .... B88
      X-Alpha parameter    XAlpha          ....  0.666667
      Becke's b parameter  XBeta           ....  0.004200
    Correlation Functional Correlation     .... LYP
    LDA part of GGA corr.  LDAOpt          .... VWN-5
    Gradients option       PostSCFGGA      .... off
    Hybrid DFT is turned on
      Fraction HF Exchange ScalHFX         ....  0.150000
      Scaling of DF-GGA-X  ScalDFX         ....  0.720000
      Scaling of DF-GGA-C  ScalDFC         ....  0.810000
      Scaling of DF-LDA-C  ScalLDAC        ....  1.000000
      Perturbative correction              ....  0.000000
      NL short-range parameter             ....  4.800000
    RI-approximation to the Coulomb term is turned on
      Number of auxiliary basis functions  .... 1301
      RIJ-COSX (HFX calculated with COS-X)).... on


   General Settings:
    Integral files         IntName         .... run
    Hartree-Fock type      HFTyp           .... RHF
    Total Charge           Charge          ....    2
    Multiplicity           Mult            ....    1
    Number of Electrons    NEL             ....  168
    Basis Dimension        Dim             ....  433
    Nuclear Repulsion      ENuc            ....   2369.9094327323 Eh

   Convergence Acceleration:
    DIIS                   CNVDIIS         .... on
      Start iteration      DIISMaxIt       ....    12
      Startup error        DIISStart       ....  0.200000
      # of expansion vecs  DIISMaxEq       ....     5
      Bias factor          DIISBfac        ....   1.050
      Max. coefficient     DIISMaxC        ....  10.000
    Newton-Raphson         CNVNR           .... off
    SOSCF                  CNVSOSCF        .... off
    Level Shifting         CNVShift        .... on
      Level shift para.    LevelShift      ....    0.2500
      Turn off err/grad.   ShiftErr        ....    0.0010
    Zerner damping         CNVZerner       .... off
    Static damping         CNVDamp         .... on
      Fraction old density DampFac         ....    0.7000
      Max. Damping (<1)    DampMax         ....    0.9800
      Min. Damping (>=0)   DampMin         ....    0.0000
      Turn off err/grad.   DampErr         ....    0.1000
    Fernandez-Rico         CNVRico         .... off


   SCF Procedure:
    Maximum # iterations   MaxIter         ....   300
    SCF integral mode      SCFMode         .... Direct
      Integral package                     .... LIBINT
    Reset frequeny         DirectResetFreq ....    20
    Integral Threshold     Thresh          ....  2.500e-11 Eh
    Primitive CutOff       TCut            ....  2.500e-12 Eh

   Convergence Tolerance:
    Convergence Check Mode ConvCheckMode   .... Total+1el-Energy
    Energy Change          TolE            ....  1.000e-08 Eh
    1-El. energy change                    ....  1.000e-05 Eh
    DIIS Error             TolErr          ....  5.000e-07


   Diagonalization of the overlap matrix:
   Smallest eigenvalue                        ... 1.574e-03
   Time for diagonalization                   ...    0.098 sec
   Threshold for overlap eigenvalues          ... 1.000e-08
   Number of eigenvalues below threshold      ... 0
   Time for construction of square roots      ...    0.061 sec
   Total time needed                          ...    0.161 sec

   ---------------------
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="scfsettings">                                        
            <module cmlx:templateRef="scfsettings">
                <module cmlx:templateRef="section" name="Hamiltonian">
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Method</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">DFT(GTOs)</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Exchange</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">B88</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">XAlpha</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.666667</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">XBeta</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.004200</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Correlation</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">LYP</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">LDAOpt</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">VWN-5</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">PostSCFGGA</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">off</scalar>
                   </list>
                   <scalar dataType="xsd:string" dictRef="o:comment">Hybrid DFT is turned on</scalar>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ScalHFX</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.150000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ScalDFX</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.720000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ScalDFC</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.810000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ScalLDAC</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1.000000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Perturbative correction</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.000000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">NL short-range parameter</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">4.800000</scalar>
                   </list>
                   <scalar dataType="xsd:string" dictRef="o:comment">RI-approximation to the Coulomb term is turned on</scalar>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Number of auxiliary basis functions</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1301</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">RIJ-COSX (HFX calculated with COS-X))</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">on</scalar>
                   </list>
                </module>
                <module cmlx:templateRef="section" name="General Settings">
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">IntName</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">run</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">HFTyp</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">RHF</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Charge</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">2</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Mult</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">NEL</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">168</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Dim</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">433</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ENuc</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">2364.5148376365 Eh</scalar>
                   </list>
                </module>
                <module cmlx:templateRef="section" name="Convergence Acceleration">
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVDIIS</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">on</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DIISMaxIt</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">12</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DIISStart</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.200000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DIISMaxEq</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">5</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DIISBfac</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1.050</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DIISMaxC</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">10.000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVNR</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">off</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVSOSCF</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">off</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVShift</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">on</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">LevelShift</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.2500</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ShiftErr</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.0010</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVZerner</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">off</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVDamp</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">on</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DampFac</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.7000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DampMax</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.9800</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DampMin</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.0000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DampErr</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.1000</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">CNVRico</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">off</scalar>
                   </list>
                </module>
                <module cmlx:templateRef="section" name="SCF Procedure">
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">MaxIter</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">300</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">SCFMode</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">Direct</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Integral package</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">LIBINT</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">DirectResetFreq</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">20</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Thresh</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">2.500e-11 Eh</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">TCut</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">2.500e-12 Eh</scalar>
                   </list>
                </module>
                <module cmlx:templateRef="section" name="Convergence Tolerance">
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">ConvCheckMode</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">Total+1el-Energy</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">TolE</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1.000e-08 Eh</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">1-El. energy change</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1.000e-05 Eh</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">TolErr</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">5.000e-07</scalar>
                   </list>
                </module>
                <module cmlx:templateRef="section" name="Diagonalization of the overlap matrix">
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Smallest eigenvalue</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1.589e-03</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Time for diagonalization</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.104 sec</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Threshold for overlap eigenvalues</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">1.000e-08</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Number of eigenvalues below threshold</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Time for construction of square roots</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.060 sec</scalar>
                   </list>
                   <list>
                      <scalar dataType="xsd:string" dictRef="cc:parameter">Total time needed</scalar>
                      <scalar dataType="xsd:string" dictRef="cc:value">0.166 sec</scalar>
                   </list>
                </module>
             </module>          
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="3" />
   <templateList>  <template id="section" pattern=".*:\s*" endPattern="\s*" endPattern2="~" repeat="*">    <record>{X,o:section}:\s*</record>    <templateList>      <template id="withAbbreviation" pattern=".{23}(\s\w{3,}).*\.\.\.(\.)?.*" endPattern=".*" endPattern2="~" repeat="*">        <record>.{24}{X,cc:parameter}\.\.\.(\.)?{X,cc:value}</record>     
                   </template>      <template id="withoutAbbreviation" pattern=".*\.\.\.(\.)?.*" endPattern=".*" endPattern2="~" repeat="*">        <record>{X,cc:parameter}\.\.\.(\.)?{X,cc:value}</record>
                   </template>      <template id="fullLineInfo" pattern="((?!\.\.\.).)*" endPattern=".*" endPattern2="~" repeat="*">        <record>{X,o:comment}</record>
                   </template>           
               </templateList>                   
           </template>   
       </templateList>
   <transform process="addAttribute" xpath=".//cml:module[@cmlx:templateRef='section']" name="name" value="$string(.//cml:scalar[@dictRef='o:section']/text())" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='o:section']" />
   <transform process="pullup" xpath=".//cml:list[./cml:scalar[not(@dictRef='o:comment')]]" repeat="2" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='o:comment']" repeat="2" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='withAbbreviation']" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='withoutAbbreviation']" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='fullLineInfo']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
