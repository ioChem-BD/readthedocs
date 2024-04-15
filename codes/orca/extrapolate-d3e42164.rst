.. _extrapolate-d3e42164:

extrapolate
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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | extrapolate                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Automatic extrapolation to the basis set limit                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{10,}&#92;s*$&#92;s*EP.*-.*extrapolation:&#92;s\*                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Estimated&#92;s*CBS&#92;s*total&#92;s*energy.*$&#92;s\*                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/extrapolate.xml                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   -----------------------------------------------------------------
                         EP1 - MP2 extrapolation:
   -----------------------------------------------------------------
   NOTE: For the SCF part we extrapolate based on the scheme proposed in J. Chem. Phys. 2008, 129, 184116
   using the exponents from J. Chem. Theory Comput., 7, 33-43 (2011)

   NOTE: For the correlation part we extrapolate based on the scheme proposed in J. Chem. Phys. 1997, 106, 9639
   using the exponents from J. Chem. Theory Comput., 7, 33-43 (2011)


   Alpha(2/3)     :  4.420 (SCF Extrapolation)
   Beta(2/3)      :  2.460 (correlation extrapolation)

   SCF energy with basis cc-pVDZ:                         -187.648544524
   SCF energy with basis cc-pVTZ:                         -187.704294229
   Extrapolated CBS SCF energy (2/3) :                    -187.722424938 (-0.018130709) 

   MP2 energy with basis cc-pVDZ:                           -0.484223441
   MP2 energy with basis cc-pVTZ:                           -0.603305598
   Extrapolated CBS correlation energy (2/3) :              -0.672889627 (-0.069584029)

   Estimated CBS total energy (2/3) :                     -188.395314565   
       

.. container:: formalpara-title

   **Input**

::

   -----------------------------------------------------------------
                         EP1 - MDCI extrapolation:
   -----------------------------------------------------------------
   NOTE: We use as reference SCF energy, for the extrapolation, the one from the MDCI module and not the one 
   from the SCF calculation. In case the first step is a DFT calculation these two might be different.

   NOTE: For the SCF part we extrapolate based on the scheme proposed in J. Chem. Phys. 2008, 129, 184116
   using the exponents from J. Chem. Theory Comput., 7, 33-43 (2011)

   NOTE: For the correlation part we extrapolate based on the scheme proposed in J. Chem. Phys. 1997, 106, 9639
   using the exponents from J. Chem. Theory Comput., 7, 33-43 (2011)


   Alpha(2/3)     :  4.420 (SCF Extrapolation)
   Beta(2/3)      :  2.460 (correlation extrapolation)

   Alpha(3/4)     :  5.460 (SCF Extrapolation)
   Beta(3/4)      :  3.050 (correlation extrapolation)

   Alpha(4/5)     :  9.190 (SCF Extrapolation)
   Beta(4/5)      :  3.000 (correlation extrapolation)

   SCF energy with basis cc-pVDZ:                          -76.026430944
   SCF energy with basis cc-pVTZ:                          -76.056728252
   SCF energy with basis cc-pVQZ:                          -76.064381269
   SCF energy with basis cc-pV5Z:                          -76.066641010
   Extrapolated CBS SCF energy (2/3) :                     -76.066581429 (-0.009853177) 
   Extrapolated CBS SCF energy (3/4) :                     -76.066687152 (-0.002305884) 
   Extrapolated CBS SCF energy (4/5) :                     -76.066932454 (-0.000291444) 

   MDCI energy with basis cc-pVDZ:                          -0.214591061
   MDCI energy with basis cc-pVTZ:                          -0.275383015
   MDCI energy with basis cc-pVQZ:                          -0.295324345
   MDCI energy with basis cc-pV5Z:                          -0.302327391
   Extrapolated CBS correlation energy (2/3) :              -0.310905962 (-0.035522947)
   Extrapolated CBS correlation energy (3/4) :              -0.309520369 (-0.014196023)
   Extrapolated CBS correlation energy (4/5) :              -0.309674848 (-0.007347457)

   Estimated CBS total energy (2/3) :                      -76.377487391
   Estimated CBS total energy (3/4) :                      -76.376207521
   Estimated CBS total energy (4/5) :                      -76.376607302
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="extrapolate">
           <module cmlx:templateRef="extrapolate" dictRef="cc:userDefinedModule">
               <module cmlx:templateRef="scf">
                  <array dataType="xsd:string" dictRef="cc:basis" size="2">cc-pVDZ cc-pVTZ</array>
                  <array dataType="xsd:double" dictRef="o:scfener" size="2">-187.648544524 -187.704294229</array>
                  <array dataType="xsd:string" dictRef="o:zetas" size="1">2/3</array>
                  <array dataType="xsd:double" dictRef="o:scfcbsextra" size="1">-187.722424938</array>
               </module>
               <module cmlx:templateRef="correlation">
                  <array dataType="xsd:string" dictRef="o:corrmethod" size="2">MP2 MP2</array>
                  <array dataType="xsd:string" dictRef="cc:basis" size="2">cc-pVDZ cc-pVTZ</array>
                  <array dataType="xsd:double" dictRef="o:correner" size="2">-0.484223441 -0.603305598</array>
                  <array dataType="xsd:string" dictRef="o:zetas" size="1">2/3</array>
                  <array dataType="xsd:double" dictRef="o:corrcbsextra" size="1">-0.672889627</array>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="extrapolate2">
           <module cmlx:templateRef="extrapolate" dictRef="cc:userDefinedModule">
               <module cmlx:templateRef="scf">
                  <array dataType="xsd:string" dictRef="cc:basis" size="4">cc-pVDZ cc-pVTZ cc-pVQZ cc-pV5Z</array>
                  <array dataType="xsd:double" dictRef="o:scfener" size="4">-76.026430944 -76.056728252 -76.064381269 -76.066641010</array>
                  <array dataType="xsd:string" dictRef="o:zetas" size="3">2/3 3/4 4/5</array>
                  <array dataType="xsd:double" dictRef="o:scfcbsextra" size="3">-76.066581429 -76.066687152 -76.066932454</array>
               </module>
               <module cmlx:templateRef="correlation">
                  <array dataType="xsd:string" dictRef="o:corrmethod" size="4">MDCI MDCI MDCI MDCI</array>
                  <array dataType="xsd:string" dictRef="cc:basis" size="4">cc-pVDZ cc-pVTZ cc-pVQZ cc-pV5Z</array>
                  <array dataType="xsd:double" dictRef="o:correner" size="4">-0.214591061 -0.275383015 -0.295324345 -0.302327391</array>
                  <array dataType="xsd:string" dictRef="o:zetas" size="3">2/3 3/4 4/5</array>
                  <array dataType="xsd:double" dictRef="o:corrcbsextra" size="3">-0.310905962 -0.309520369 -0.309674848</array>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="scf" pattern="\s*SCF\senergy\swith\sbasis.*" endPattern="\s*">    <record repeat="*" makeArray="true">\s*SCF\senergy\swith\sbasis{A,cc:basis}:{F,o:scfener}</record>    <record repeat="*" makeArray="true">\s*Extrapolated\sCBS\sSCF\senergy\s*\S{A,o:zetas}\S\s*:{F,o:scfcbsextra}.*</record>    <record repeat="*" makeArray="true">\s*Extrapolated\sCBS\sSCF\senergy\s*:{F,o:scfcbsextra}.*</record>          
           </template>  <template id="correlation" pattern=".*(MP2|MDCI)\senergy\swith\sbasis\s.*" endPattern="\s*">    <record repeat="*" makeArray="true">\s*{X,o:corrmethod}\senergy\swith\sbasis{A,cc:basis}:{F,o:correner}</record>    <record repeat="*" makeArray="true">\s*Extrapolated\sCBS\scorrelation\senergy\s*\S{A,o:zetas}\S\s*:{F,o:corrcbsextra}.*</record>    <record repeat="*" makeArray="true">\s*Extrapolated\sCBS\scorrelation\senergy\s*:{F,o:corrcbsextra}.*</record>
           </template>  <template id="correlation2" pattern="\s*CCSD.T.\s*-.*energy\swith\sbasis.*" endPattern="\s*" endPattern2="~" endOffset="1">    <record>\s*CCSD.T.\s*-.*energy\swith\sbasis.*:{F,o:corrcbs2}</record>
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:list/cml:array" />
   <transform process="pullup" xpath=".//cml:list/cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
