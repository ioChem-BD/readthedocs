.. _multicaspt2-d3e22323:

multicaspt2
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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | multicaspt2                       |
   +-----------------------------------+-----------------------------------+
   | name                              | Multi-state caspt2 sections       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\                                |
   |                                   | s*MULTI-STATE\sCASPT2\sSECTION.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\*{20,}.\*                    |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/caspt2/multicaspt2.xml    |
   +-----------------------------------+-----------------------------------+

**Input.**

::

     MULTI-STATE CASPT2 SECTION
   --------------------------------------------------------------------------------
    
     Output diagonal energies have been shifted. Add   -2189.00000000000     
    
     Effective Hamiltonian matrix (Symmetric):
    
                   1               2               3               4               5
     1        -0.95924664
     2        -0.00029180     -0.95546752
     3        -0.00018887     -0.00012086     -0.95190023
     4         0.00002403      0.00021317      0.00005831     -0.91308010
     5        -0.00066584      0.00017263     -0.00583328     -0.00020086     -0.90919311
     6        -0.00022470     -0.00425668     -0.00067317      0.00142680      0.00081104
     7        -0.00275248     -0.00185426     -0.00070732      0.00069866      0.00061499
     8        -0.00153172      0.00139802      0.00022494     -0.00056091      0.00001442
     9        -0.00382876      0.00069748      0.00019030      0.00035112      0.00044072
    10        -0.00091129     -0.00179997      0.00028100      0.00000536      0.00144478
    11         0.00008973     -0.00211666      0.00012593      0.00004666     -0.00282182
    12        -0.00065849     -0.00038632     -0.00038650     -0.00055712      0.00001588
    13        -0.00024421      0.00094751      0.00000415     -0.00010243      0.00034155
    
                   6               7               8               9              10
     6        -0.90049562
     7        -0.00137587     -0.90261299
     8         0.00322702     -0.00364490     -0.90199874
     9         0.00054740      0.00171405      0.00220185     -0.88680543
    10         0.00119814      0.00055954      0.00021542      0.00056434     -0.88780355
    11         0.00013823     -0.00135117     -0.00065158      0.00159921     -0.00342043
    12         0.00056467     -0.00076122     -0.00033970      0.00033176      0.00007268
    13         0.00265919     -0.00297161      0.00413949      0.00029605      0.00032038
    
                  11              12              13
    11        -0.88596502
    12         0.00024187     -0.89400080
    13         0.00044418     -0.00082835     -0.88396600
    
     Energies and eigenvectors:
    
      -2189.95968493  -2189.95602343  -2189.95268620  -2189.91338192  -2189.90892385
    
         -0.99160913      0.09601181      0.03887011     -0.00142409     -0.00543199
         -0.09316903     -0.98932961      0.04755202     -0.02198437      0.01151394
         -0.04119058     -0.04286650     -0.98912899      0.00671068     -0.12893482
          0.00192938      0.00828509      0.00084772     -0.98356919     -0.09448026
         -0.01603572      0.00006375     -0.13248123     -0.07565259      0.97123017
         -0.00968582     -0.07878736     -0.00733349      0.13127581     -0.09110553
         -0.05174689     -0.03050501     -0.00883803      0.05171791     -0.08575323
         -0.02464604      0.02920754      0.00380146     -0.07124628      0.01664260
         -0.04875067      0.01670576      0.00565990      0.01547584     -0.01763263
         -0.01350697     -0.02489397      0.00914829     -0.00532823     -0.03751129
         -0.00268065     -0.03176705     -0.00205108     -0.00894075      0.11345011
         -0.01111120     -0.00458871     -0.00578169     -0.03171065     -0.01071373
         -0.00215646      0.01350517     -0.00024895      0.00067636     -0.01909555
    
      -2189.90667757  -2189.90216932  -2189.89844148  -2189.89385917  -2189.89059234
    
          0.04368698     -0.01873721      0.00957111      0.00432223      0.00997741
         -0.00774591     -0.08050600     -0.02346594      0.00538200     -0.04905455
          0.00511363     -0.03441248     -0.00043137      0.00790060      0.00650564
          0.05153062      0.13854382      0.02851916      0.02642700      0.00013591
         -0.00731073      0.12669155      0.00745980     -0.01158461     -0.03886290
          0.20457025      0.68881049      0.62643628     -0.11906878      0.07480076
         -0.63764926      0.59406481     -0.40171214      0.12225045     -0.04809125
         -0.71793279     -0.33404626      0.53411316     -0.05752906     -0.06652196
          0.14396326     -0.05114109     -0.04898119      0.02314198     -0.28551437
         -0.00279859     -0.09275066     -0.05582917      0.06747373      0.74671332
         -0.07898466      0.02501944     -0.01818858      0.06945678      0.57970840
         -0.06298349      0.00605909     -0.16546853     -0.97810328      0.07472637
          0.02201446      0.07679687     -0.35523221      0.00516527     -0.05350930
    
      -2189.88591587  -2189.88271763  -2189.88146204
    
          0.05802649      0.00345258      0.01010881
          0.00688199     -0.00651217     -0.00724033
          0.00087824      0.00999883     -0.00209072
         -0.01513434      0.00120207      0.00010627
         -0.03701957     -0.11831531      0.00262337
         -0.03852081     -0.06285315     -0.18485996
         -0.12693557     -0.02243452      0.17756441
         -0.06388651     -0.05660409     -0.25663299
         -0.91398371      0.15252480     -0.17417753
         -0.31870190     -0.56763760      0.00586773
         -0.03204907      0.77915780     -0.17272268
         -0.05201963      0.02861890      0.03902695
          0.18065716     -0.15749827     -0.89807730
    
     THE ORIGINAL CI ARRAYS ARE NOW MIXED AS LINEAR
     COMBINATIONS, GIVEN BY THE EIGENVECTORS.
     A NEW JOBIPH FILE NAMED 'JOBMIX' IS PREPARED.
   ********************************************************************************    
       

**Input.**

::

   ********************************************************************************
     MULTI-STATE CASPT2 SECTION
   --------------------------------------------------------------------------------

     Output diagonal energies have been shifted. Add   -741.000000000000

     Effective Hamiltonian matrix (Symmetric):

                   1               2               3               4               5
     1        -0.15945227
     2         0.00142922      0.03836877
     3         0.00148404     -0.01134618      0.02239270
     4        -0.00060037      0.00417400      0.00094443      0.08247087
     5        -0.00035465      0.00853446     -0.00016769     -0.01447031      0.07653251
     6        -0.00619529     -0.00220523     -0.01377546      0.00874649     -0.01871907

                   6
     6         0.08086502

          Total MS-CASPT2 energies:
   ::    MS-CASPT2 Root  1     Total energy:   -741.15963375
   ::    MS-CASPT2 Root  2     Total energy:   -740.98641939
   ::    MS-CASPT2 Root  3     Total energy:   -740.96033385
   ::    MS-CASPT2 Root  4     Total energy:   -740.93667844
   ::    MS-CASPT2 Root  5     Total energy:   -740.92462959
   ::    MS-CASPT2 Root  6     Total energy:   -740.89112737

          Eigenvectors:
               0.99961375     -0.00422420      0.01068273      0.01438919      0.01431476
              -0.00752419     -0.43391149      0.81728889     -0.36213541      0.10166258
              -0.00669306     -0.87608589     -0.37351594      0.25722968      0.14030238
               0.00194605      0.06616268     -0.14868520     -0.25774477      0.79974157
               0.00391121      0.01247138     -0.35553801     -0.71550040      0.08699198
               0.02553152     -0.19910663     -0.20951378     -0.47340320     -0.56799725
               0.01511382
               0.04717770
               0.08403982
              -0.51719676
               0.59490626
              -0.60751725

     THE ORIGINAL CI ARRAYS ARE NOW MIXED AS LINEAR
     COMBINATIONS, GIVEN BY THE EIGENVECTORS.
     A NEW JOBIPH FILE NAMED 'JOBMIX' IS PREPARED.
   ********************************************************************************    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="multicaspt2">
           <module cmlx:templateRef="multicaspt2">
               <scalar dataType="xsd:double" dictRef="m:diagonalenershift">-2189.00000000000</scalar>
               <module cmlx:templateRef="hamiltonianmatrix">
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="1">-0.95924664</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="2">-0.00029180 -0.95546752</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="3">-0.00018887 -0.00012086 -0.95190023</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="4">0.00002403 0.00021317 0.00005831 -0.91308010</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00066584 0.00017263 -0.00583328 -0.00020086 -0.90919311</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00022470 -0.00425668 -0.00067317 0.00142680 0.00081104</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00275248 -0.00185426 -0.00070732 0.00069866 0.00061499</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00153172 0.00139802 0.00022494 -0.00056091 0.00001442</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00382876 0.00069748 0.00019030 0.00035112 0.00044072</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00091129 -0.00179997 0.00028100 0.00000536 0.00144478</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">0.00008973 -0.00211666 0.00012593 0.00004666 -0.00282182</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00065849 -0.00038632 -0.00038650 -0.00055712 0.00001588</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00024421 0.00094751 0.00000415 -0.00010243 0.00034155</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="1">-0.90049562</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="2">-0.00137587 -0.90261299</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="3">0.00322702 -0.00364490 -0.90199874</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="4">0.00054740 0.00171405 0.00220185 -0.88680543</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">0.00119814 0.00055954 0.00021542 0.00056434 -0.88780355</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">0.00013823 -0.00135117 -0.00065158 0.00159921 -0.00342043</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">0.00056467 -0.00076122 -0.00033970 0.00033176 0.00007268</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">0.00265919 -0.00297161 0.00413949 0.00029605 0.00032038</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="1">-0.88596502</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="2">0.00024187 -0.89400080</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="3">0.00044418 -0.00082835 -0.88396600</array>
               </module>
               <module cmlx:templateRef="eigenvectors">
                  <array dataType="xsd:double" dictRef="m:rootenergy" size="5">-2189.95968493 -2189.95602343 -2189.95268620 -2189.91338192 -2189.90892385</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">-0.99160913 -0.09316903 -0.04119058 0.00192938 -0.01603572 -0.00968582 -0.05174689 -0.02464604 -0.04875067 -0.01350697 -0.00268065 -0.01111120 -0.00215646</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.09601181 -0.98932961 -0.04286650 0.00828509 0.00006375 -0.07878736 -0.03050501 0.02920754 0.01670576 -0.02489397 -0.03176705 -0.00458871 0.01350517</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.03887011 0.04755202 -0.98912899 0.00084772 -0.13248123 -0.00733349 -0.00883803 0.00380146 0.00565990 0.00914829 -0.00205108 -0.00578169 -0.00024895</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">-0.00142409 -0.02198437 0.00671068 -0.98356919 -0.07565259 0.13127581 0.05171791 -0.07124628 0.01547584 -0.00532823 -0.00894075 -0.03171065 0.00067636</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">-0.00543199 0.01151394 -0.12893482 -0.09448026 0.97123017 -0.09110553 -0.08575323 0.01664260 -0.01763263 -0.03751129 0.11345011 -0.01071373 -0.01909555</array>
                  <array dataType="xsd:double" dictRef="m:rootenergy" size="5">-2189.90667757 -2189.90216932 -2189.89844148 -2189.89385917 -2189.89059234</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.04368698 -0.00774591 0.00511363 0.05153062 -0.00731073 0.20457025 -0.63764926 -0.71793279 0.14396326 -0.00279859 -0.07898466 -0.06298349 0.02201446</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">-0.01873721 -0.08050600 -0.03441248 0.13854382 0.12669155 0.68881049 0.59406481 -0.33404626 -0.05114109 -0.09275066 0.02501944 0.00605909 0.07679687</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.00957111 -0.02346594 -0.00043137 0.02851916 0.00745980 0.62643628 -0.40171214 0.53411316 -0.04898119 -0.05582917 -0.01818858 -0.16546853 -0.35523221</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.00432223 0.00538200 0.00790060 0.02642700 -0.01158461 -0.11906878 0.12225045 -0.05752906 0.02314198 0.06747373 0.06945678 -0.97810328 0.00516527</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.00997741 -0.04905455 0.00650564 0.00013591 -0.03886290 0.07480076 -0.04809125 -0.06652196 -0.28551437 0.74671332 0.57970840 0.07472637 -0.05350930</array>
                  <array dataType="xsd:double" dictRef="m:rootenergy" size="3">-2189.88591587 -2189.88271763 -2189.88146204</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.05802649 0.00688199 0.00087824 -0.01513434 -0.03701957 -0.03852081 -0.12693557 -0.06388651 -0.91398371 -0.31870190 -0.03204907 -0.05201963 0.18065716</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.00345258 -0.00651217 0.00999883 0.00120207 -0.11831531 -0.06285315 -0.02243452 -0.05660409 0.15252480 -0.56763760 0.77915780 0.02861890 -0.15749827</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="13">0.01010881 -0.00724033 -0.00209072 0.00010627 0.00262337 -0.18485996 0.17756441 -0.25663299 -0.17417753 0.00586773 -0.17272268 0.03902695 -0.89807730</array>
               </module>
            </module>                
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="multicaspt2_2">
               <module cmlx:templateRef="multicaspt2">
               <scalar dataType="xsd:double" dictRef="m:diagonalenershift">-741.000000000000</scalar>
               <module cmlx:templateRef="hamiltonianmatrix">
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="1">-0.15945227</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="2">0.00142922 0.03836877</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="3">0.00148404 -0.01134618 0.02239270</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="4">-0.00060037 0.00417400 0.00094443 0.08247087</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00035465 0.00853446 -0.00016769 -0.01447031 0.07653251</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="5">-0.00619529 -0.00220523 -0.01377546 0.00874649 -0.01871907</array>
                  <array dataType="xsd:double" dictRef="cc:hamiltonian" size="1">0.08086502</array>
               </module>
               <module cmlx:templateRef="ms-caspt2">
                  <array dataType="xsd:integer" dictRef="m:root" size="6">1 2 3 4 5 6</array>
                  <array dataType="xsd:double" dictRef="m:mscaspt2energy" size="6">-741.15963375 -740.98641939 -740.96033385 -740.93667844 -740.92462959 -740.89112737</array>
               </module>
               <module cmlx:templateRef="eigenvectors">
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="12">0.99961375 -0.00752419 -0.00669306 0.00194605 0.00391121 0.02553152 0.01511382 0.04717770 0.08403982 -0.51719676 0.59490626 -0.60751725</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="6">-0.00422420 -0.43391149 -0.87608589 0.06616268 0.01247138 -0.19910663</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="6">0.01068273 0.81728889 -0.37351594 -0.14868520 -0.35553801 -0.20951378</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="6">0.01438919 -0.36213541 0.25722968 -0.25774477 -0.71550040 -0.47340320</array>
                  <array dataType="xsd:double" dictRef="m:eigenvector" size="6">0.01431476 0.10166258 0.14030238 0.79974157 0.08699198 -0.56799725</array>
               </module>
            </module>
     
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Output\sdiagonal\senergies\shave\sbeen\sshifted\.\sAdd.*" endPattern=".*">    <record>\s*Output\sdiagonal\senergies\shave\sbeen\sshifted\.\sAdd{F,m:diagonalenershift}</record>    <transform process="pullup" xpath=".//cml:scalar[@dictRef='m:diagonalenershift']" repeat="2" />      
           </template>  <template id="hamiltonianmatrix" pattern="\s*Effective\sHamiltonian\smatrix\s\(Symmetric\):.*" endPattern="\s*$\s*[a-zA-Z].*">    <record repeat="2" />    <templateList>      <template pattern="\s{14,}[0-9].*" endPattern="\s*" endPattern2="~" repeat="*">        <record />        <record repeat="*">{I,cc:dummy}{1_6F,cc:hamiltonian}</record>                          
                   </template>
               </templateList>    <transform process="move" xpath=".//cml:array" to="." />    <transform process="delete" xpath=".//cml:list" />    <transform process="delete" xpath=".//cml:module" />
           </template>  <template id="eigenvectors" pattern="\s*Energies\sand\seigenvectors:.*" endPattern="\s*[a-zA-Z].*">    <record />    <templateList>      <template pattern="\s+\S+.*$\s*" endPattern=".*\S+$.*\S+$\s*" endOffset="2" repeat="*">        <record>{1_5F,m:rootenergy}</record>        <record />        <templateList>          <template pattern="(\s+\S+){5}\s*" endPattern="~">            <record repeat="*">{F,m:eigenvector1}\s+{F,m:eigenvector2}\s+{F,m:eigenvector3}\s+{F,m:eigenvector4}\s+{F,m:eigenvector5}</record>
                           </template>          <template pattern="(\s+\S+){4}\s*" endPattern="~">            <record repeat="*">{F,m:eigenvector1}\s+{F,m:eigenvector2}\s+{F,m:eigenvector3}\s+{F,m:eigenvector4}</record>
                           </template>          <template pattern="(\s+\S+){3}\s*" endPattern="~">            <record repeat="*">{F,m:eigenvector1}\s+{F,m:eigenvector2}\s+{F,m:eigenvector3}</record>
                           </template>          <template pattern="(\s+\S+){2}\s*" endPattern="~">            <record repeat="*">{F,m:eigenvector1}\s+{F,m:eigenvector2}</record>
                           </template>          <template pattern="(\s+\S+){1}\s*" endPattern="~">            <record repeat="*">{F,m:eigenvector1}</record>
                           </template>
                       </templateList>        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector1']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector2']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector3']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector4']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector5']" dictRef="m:eigenvector" />                    
                   </template>
               </templateList>    <transform process="move" xpath=".//cml:array" to="." />    <transform process="delete" xpath=".//cml:list" />    <transform process="delete" xpath=".//cml:module" />           
           </template>  <template id="eigenvectors" pattern="\s*Eigenvectors:.*" endPattern="\s*[a-zA-Z].*" endPattern2="~">    <record />    <templateList>      <template id="section" pattern="\s+\S+.*" endPattern=".*\S+$.*\S+$\s*" endOffset="2" repeat="*">        <templateList>          <template pattern="(\s+\S+){5}\s*" endPattern=".*" endPattern2="~" repeat="*">            <record>{F,m:eigenvector1}\s+{F,m:eigenvector2}\s+{F,m:eigenvector3}\s+{F,m:eigenvector4}\s+{F,m:eigenvector5}</record>
                           </template>          <template pattern="(\s+\S+){4}\s*" endPattern=".*" endPattern2="~" repeat="*">            <record>{F,m:eigenvector1}\s+{F,m:eigenvector2}\s+{F,m:eigenvector3}\s+{F,m:eigenvector4}</record>
                           </template>          <template pattern="(\s+\S+){3}\s*" endPattern=".*" endPattern2="~" repeat="*">            <record>{F,m:eigenvector1}\s+{F,m:eigenvector2}\s+{F,m:eigenvector3}</record>
                           </template>          <template pattern="(\s+\S+){2}\s*" endPattern=".*" endPattern2="~" repeat="*">            <record>{F,m:eigenvector1}\s+{F,m:eigenvector2}</record>
                           </template>          <template pattern="(\s+\S+){1}\s*" endPattern=".*" endPattern2="~" repeat="*">            <record>{F,m:eigenvector1}</record>
                           </template>
                       </templateList>        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector1']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector2']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector3']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector4']" dictRef="m:eigenvector" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:eigenvector5']" dictRef="m:eigenvector" />                                        
                   </template>               
               </templateList>    <transform process="move" xpath=".//cml:array" to="." />    <transform process="delete" xpath=".//cml:list" />    <transform process="delete" xpath=".//cml:module" />           
           </template>  <transform process="delete" xpath=".//cml:list[count(*)=0]" />  <transform process="delete" xpath=".//cml:module[count(*)=0]" />  <template id="ms-caspt2" pattern="\s*Total\sMS-CASPT2\senergies.*" endPattern="\s*">    <record />    <record makeArray="true" repeat="*">.*MS-CASPT2\sRoot{I,m:root}Total\senergy:{F,m:mscaspt2energy}</record>    <transform process="move" xpath=".//cml:array" to="." />    <transform process="delete" xpath=".//cml:list" />
           </template>
                   
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
