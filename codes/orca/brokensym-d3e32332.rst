.. _brokensym-d3e32332:

brokensym
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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | brokensym                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Broken symmetry magnetic coupling analysis                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-+&#92;s*$&#92;s*BROKEN&#92;sSYMMETRY&#92;sMAGNETIC&#92;sCOUPLING&#92;sANALYSIS.*$&#92;s*-+&#92;s\*                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*J&#92;(1&#92;):.\*                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/brokensym.xml                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       ------------------------------------------
       BROKEN SYMMETRY MAGNETIC COUPLING ANALYSIS
       ------------------------------------------
       
       S(High-Spin)      =   1.0    
       <S**2>(High-Spin) =   2.0054    
       <S**2>(BrokenSym) =   0.9478    
       E(High-Spin)      = -3947.379193 Eh
       E(BrokenSym)      = -3947.384041 Eh
       E(High-Spin)-E(BrokenSym)= 0.1319 eV   1063.881 cm**-1 (ANTIFERROMAGNETIC coupling)
       
                 ---------------------------------------------------------
                 | Spin-Hamiltonian Analysis based on H(HDvV)= -2J*SA*SB |
           -------                                                       -----------
           | J(1) =   -1063.88 cm**-1    (from -(E[HS]-E[BS])/Smax**2)             |
           | J(2) =    -531.94 cm**-1    (from -(E[HS]-E[BS])/(Smax*(Smax+1))      |
           | J(3) =   -1005.96 cm**-1    (from -(E[HS]-E[BS])/(<S**2>HS-<S**2>BS)) |
           -------------------------------------------------------------------------
       
         J(1): (a) A.P. Ginsberg J. Am. Chem. Soc. 102 (1980), 111
               (b) L. Noodleman J. Chem. Phys. 74 (1981), 5737
               (c) L. Noodleman E.R. Davidson Chem. Phys. 109 (1985), 131
         J(2)  (d) A. Bencini D. Gatteschi J. Am. Chem. Soc. 108 (1980), 5763
         J(3)  (e) K. Yamaguchi Y. Takahara T. Fueno in: V.H. Smith (Ed.)
                   Applied Quantum Chemistry. Reidel, Dordrecht (1986), pp 155
               (f) T.Soda et al. Chem. Phys. Lett., 319, (2000), 223
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="brokensym">
         <module cmlx:templateRef="brokensym">
            <list cmlx:templateRef="spinHamiltonianAnalyis">
               <array dataType="xsd:integer" dictRef="o:jindex" size="3">1 2 3</array>
               <array dataType="xsd:double" dictRef="cc:value" size="3" units="nonsi:cm-1">-1063.88 -531.94 -1005.96</array>
            </list>
            <scalar dataType="xsd:double" dictRef="o:sHighSpin">1.0</scalar>
            <scalar dataType="xsd:double" dictRef="o:s2HighSpin">2.0054</scalar>
            <scalar dataType="xsd:double" dictRef="o:s2BrokenSym">0.9478</scalar>
            <scalar dataType="xsd:double" dictRef="o:eHighSpin" units="nonsi:hartree">-3947.379193</scalar>
            <scalar dataType="xsd:double" dictRef="o:eBrokenSym" units="nonsi:hartree">-3947.384041</scalar>
            <scalar dataType="xsd:double" dictRef="o:ediff" units="nonsi:cm-1">1063.881</scalar>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern="\s*E\(High-Spin\)-E\(BrokenSym\).*" endPattern=".*" endPattern2="~">    <record>\s*E\(High-Spin\)-E\(BrokenSym\)\s*=.*eV{F,o:ediff}.*</record>    <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:ediff']" value="nonsi:cm-1" />
           </template>  <template pattern="\s*S\(High-Spin\).*" endPattern=".*" endPattern2="~">    <record>\s*S\(High-Spin\)\s*={F,o:sHighSpin}</record>
           </template>  <template pattern="\s*\u003CS\*\*2\u003E\(High-Spin\).*" endPattern=".*" endPattern2="~">    <record>\s*\u003CS\*\*2\u003E\(High-Spin\)\s*={F,o:s2HighSpin}</record>
           </template>  <template pattern="\s*\u003CS\*\*2\u003E\(BrokenSym\).*" endPattern=".*" endPattern2="~">    <record>\s*\u003CS\*\*2\u003E\(BrokenSym\)\s*={F,o:s2BrokenSym}</record>
           </template>  <template pattern="\s*E\(High-Spin\).*" endPattern=".*" endPattern2="~">    <record>\s*E\(High-Spin\)\s*={F,o:eHighSpin}.*</record>    <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:eHighSpin']" value="nonsi:hartree" />
           </template>  <template pattern="\s*E\(BrokenSym\).*" endPattern=".*" endPattern2="~">    <record>\s*E\(BrokenSym\)\s*={F,o:eBrokenSym}.*</record>    <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:eBrokenSym']" value="nonsi:hartree" />
           </template>  <template id="spinHamiltonianAnalyis" name="spinHamiltonianAnalyis" pattern="\s*\|\s*Spin-Hamiltonian\sAnalysis\sbased\son.*" endPattern="\s*\|\s*J.*$\s*-{10,}\s*" endOffset="2">    <record repeat="2" />    <record id="spinHamiltonianAnalyis" repeat="*" makeArray="true">\s*\|\s*J\({I,o:jindex}\)\s*={F,cc:value}cm\*\*-1.*</record>    <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='spinHamiltonianAnalyis']" repeat="1" />
           </template>   
       </templateList>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:value']" value="nonsi:cm-1" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
