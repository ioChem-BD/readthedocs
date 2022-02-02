.. _triplesCorr-d3e34530:

triplesCorr
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
   | id                                                                                                                         | triplesCorr                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{15,}$&#92;s*.*TRIPLES&#92;sCORRECTION.\*                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*-{15,}                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | ci/triplescorr.xml                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   -------------------------------------------
   DLPNO BASED TRIPLES CORRECTION
   -------------------------------------------

   Singles multiplier          ...  1.000000
   TCutTNO                     ... 1.000e-09
   TCutMP2Pairs                ... 1.000e-05
   TCutDOStrong                ... 2.000e-03
   TCutMKNStrong               ... 1.000e-02
   TCutDOWeak                  ... 4.000e-03
   TCutMKNWeak                 ... 1.000e-01
   NTCutTNO                    ... 1

   Number of Triples that are to be computed         ...     31456

    . . . . . . . . .
   10% done  
   20% done  
   30% done  
   40% done  
   50% done  
   60% done  
   70% done  
             Batch   1   done (   1154.027 sec)
    . . . . . . . . .
   80% done  
   90% done  
             Batch   2   done (    368.031 sec)

   Triples-Correction TCutTNO=   1.000e-09 (NWeakPairs = 0  1  2  3)  -0.155463563388   -0.002401607160    0.000000000000    0.000000000000
   Triples-Correction  -0.157865170548

   Triples timings:
   Total time                      ...  1587.163 sec

   Triples List generation         ...     0.000 sec
   TNO generation                  ...    65.019 sec
   Pair density generation         ...     0.057 sec
   Look up tables                  ...     0.044 sec
   Generating 3-index integrals    ...   801.547 sec
   Make 4-ind.int. from 3-ind.int  ...     0.979 sec
   Projecting amplitudes (D + S)   ...   553.540 sec
   Sorting integrals for spin cases...    25.415 sec
   Calculate W0/W1                 ...   117.194 sec
   Energy contr. (sum over a,b,c)  ...    23.306 sec

   Everything after 3-index        ...   763.910 sec

   Energy contribution AAA         ...    15.688 sec
   Energy contribution AAB         ...    73.308 sec
   Energy contribution ABB         ...    67.016 sec
   Energy contribution BBB         ...     9.925 sec
   prep                ...     0.711 sec
   makeTTNO            ...   545.242 sec
   copyij              ...     0.057 sec
   copyil              ...     1.732 sec
   transposeij         ...     0.039 sec
   newMatInDoubleProj  ...     9.500 sec
   BlasInDoubleProj    ...   365.913 sec
   ProjSingles         ...     5.031 sec
   ProjDoubles         ...   548.509 sec
   overall Doubles for projection      ... 116222
   used Doubles for projection         ... 2319687


   Number of Triples   (0, 1, 2, 3 weak pairs; overall):  15736   10260       0       0  ( 25996)
   Number of Atoms     (0, 1, 2, 3 weak pairs; overall):   15.7    14.1     0.0     0.0  (    30)
   Number of PAOs      (0, 1, 2, 3 weak pairs; overall):  395.4   380.1     0.0     0.0  (   630)
   Number of AuxFcns   (0, 1, 2, 3 weak pairs; overall):  484.4   402.6     0.0     0.0  (  1548)
   Number of TNOs (0, 1, 2, 3 weak pairs         ):   87.2    60.9     0.0     0.0
   Aver. Number of NTNO, Atoms, PAOs, AuxFcns / Triples:  25996    76.8    15.0   389.4   452.1

   Triples Correction (T)                     ...     -0.157865171
       alpha-alpha-alpha ... -0.004810725 (  3.0%)
       alpha-alpha-beta  ... -0.073782680 ( 46.7%)
       alpha-beta -beta  ... -0.073934126 ( 46.8%)
       beta -beta -beta  ... -0.005337640 (  3.4%)
   Final correlation energy                   ...     -3.519525280
   E(CCSD)                                    ...   -898.784353171
   E(CCSD(T))                                 ...   -898.942218341

       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="triplesCorr">
           <module cmlx:templateRef="triplesCorr">
              <scalar dataType="xsd:double" dictRef="o:tripCorr" units="nonsi:hartree">-0.019986933</scalar>
              <scalar dataType="xsd:double" dictRef="o:finCorrEner" units="nonsi:hartree">-0.685813096</scalar>
              <scalar dataType="xsd:double" dictRef="o:ccsdEner" units="nonsi:hartree">-228.301709575</scalar>
              <scalar dataType="xsd:double" dictRef="o:ccsdtEner" units="nonsi:hartree">-228.321696508</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="1">.*</record>
   <record>\s*{X,o:corrType}\sTRIPLES\sCORRECTION.*</record>
   <transform process="pullup" xpath=".//cml:scalar" repeat="1" />
   <templateList>  <template pattern="\s*Triples\sCorrection.*" endPattern="\s*" endPattern2="~">    <record>\s*Triples\sCorrection\s\(T\)\s*\.\.\.{F,o:tripCorr}</record>    <record repeat="*">\s.*(alpha|beta).*</record>    <record>\s*Final\scorrelation\senergy\s*\.\.\.{F,o:finCorrEner}</record>    <record>\s*E\(CCSD\)\s*\.\.\.{F,o:ccsdEner}</record>    <record>\s*E\(CCSD\(T\)\)\s*\.\.\.{F,o:ccsdtEner}</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="2" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />                  
           </template>   
       </templateList>
   <transform process="delete" xpath=".//cml:module" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
