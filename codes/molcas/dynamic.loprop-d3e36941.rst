.. _dynamic.loprop-d3e36941:

dynamic.loprop
==============

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
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | dynamic.loprop                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | The localized properties                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#                                                                                                                         |
   |                                                                                                                            | 92;s*D&#92;sy&#92;sn&#92;sa&#92;sm&#92;si&#92;sc&#92;s*P&#92;sr&#92;so&#92;sp&#92;se&#92;sr&#92;st&#92;si&#92;se&#92;ss.\* |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | -3                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/loprop/dynamic.loprop.xml                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

     D y n a m i c  P r o p e r t i e s
    
     Properties computed with FFPT
    
    
    **********************************************************************************
    *                                                                                *
    *                            The Localized properties                            *
    *                                                                                *
    **********************************************************************************
    
    
    
    ====================
    ATOMIC DOMAIN: C1    
    ====================
    Domain center:  :  1.44186120  0.00000000  0.00000000 / bohr
    Expansion center:  1.44186120  0.00000000  0.00000000 / bohr
    Total charge    : -0.37899941
    
    Electronic multipole moments:
   Electronic Charge
    -6.37899941
    
   Electronic Dipole
    -0.09892881  0.00000401  0.00000000
   ... with nuclear contribution
    -0.09892881  0.00000401  0.00000000
    
   Electronic Quadrupole
    -4.19001771 -0.00000604 -0.00000001 -4.13923380  0.00000000 -4.13924816
   ... with nuclear contribution
    -4.19001771 -0.00000604 -0.00000001 -4.13923380  0.00000000 -4.13924816
    
    
   Dipole magnitude:  0.09892881
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       1.53099372
       0.00029156  1.29790318
       0.00030398 -0.00000832  1.29797839
    
   Isotropic Polarizability:  1.37562510
    
    
    
    =========================
    BOND DOMAIN: H2    ,C1    
    =========================
    Domain center:  :  1.81813685 -0.95667315  0.00000000 / bohr
    Expansion center:  1.81813685 -0.95667315  0.00000000 / bohr
    Total charge    : -0.00000000
    
    Electronic multipole moments:
   Electronic Charge
    -0.00000000
    
   Electronic Dipole
    -0.12480349  0.35467694 -0.00000000
    
   Electronic Quadrupole
    -0.08976328 -0.38669225  0.00000000  0.97318007 -0.00000000 -0.17513843
    
    
   Dipole magnitude:  0.37599420
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       2.03937964
      -2.77340339  5.82816829
       0.00018415 -0.00023158  0.76825434
    
   Isotropic Polarizability:  2.87860075
    
    
    
    ====================
    ATOMIC DOMAIN: H2    
    ====================
    Domain center:  :  2.19441250 -1.91334630  0.00000000 / bohr
    Expansion center:  2.19441250 -1.91334630  0.00000000 / bohr
    Total charge    :  0.12633167
    
    Electronic multipole moments:
   Electronic Charge
    -0.87366833
    
   Electronic Dipole
    -0.04281599  0.12525366 -0.00000000
   ... with nuclear contribution
    -0.04281599  0.12525366 -0.00000000
    
   Electronic Quadrupole
    -0.54417492  0.14350476  0.00000000 -0.78559026  0.00000000 -0.47329791
   ... with nuclear contribution
    -0.54417492  0.14350476  0.00000000 -0.78559026  0.00000000 -0.47329791
    
    
   Dipole magnitude:  0.13236952
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       0.78528154
      -0.23934591  1.03721561
       0.00009999 -0.00017775  0.56448696
    
   Isotropic Polarizability:  0.79566137
    
    
    
    =========================
    BOND DOMAIN: H3    ,C1    
    =========================
    Domain center:  :  1.81813685  0.47833657  0.82850325 / bohr
    Expansion center:  1.81813685  0.47833657  0.82850325 / bohr
    Total charge    : -0.00000000
    
    Electronic multipole moments:
   Electronic Charge
    -0.00000000
    
   Electronic Dipole
    -0.12480629 -0.17733663 -0.30715890
    
   Electronic Quadrupole
    -0.08976538  0.19334402  0.33488285  0.11194371  0.49724107  0.68610462
    
    
   Dipole magnitude:  0.37599399
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
      2.03940558
      1.38697003 2.03473342
      2.40214664 2.19356704 4.56665620
    
   Isotropic Polarizability:  2.88026506
    
    
    
    ====================
    ATOMIC DOMAIN: H3    
    ====================
    Domain center:  :  2.19441250  0.95667315  1.65700650 / bohr
    Expansion center:  2.19441250  0.95667315  1.65700650 / bohr
    Total charge    :  0.12633379
    
    Electronic multipole moments:
   Electronic Charge
    -0.87366621
    
   Electronic Dipole
    -0.04281865 -0.06262678 -0.10847171
   ... with nuclear contribution
    -0.04281865 -0.06262678 -0.10847171
    
   Electronic Quadrupole
    -0.54417674 -0.07175400 -0.12427979 -0.55136637 -0.13522556 -0.70751336
   ... with nuclear contribution
    -0.54417674 -0.07175400 -0.12427979 -0.55136637 -0.13522556 -0.70751336
    
    
   Dipole magnitude:  0.13236941
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
      0.78530169
      0.11980808 0.68292423
      0.20745041 0.20505418 0.91958394
    
   Isotropic Polarizability:  0.79593662
    
    
    
    =========================
    BOND DOMAIN: H4    ,C1    
    =========================
    Domain center:  :  1.81813685  0.47833657 -0.82850325 / bohr
    Expansion center:  1.81813685  0.47833657 -0.82850325 / bohr
    Total charge    :  0.00000000
    
    Electronic multipole moments:
   Electronic Charge
     0.00000000
    
   Electronic Dipole
    -0.12480629 -0.17733663  0.30715889
    
   Electronic Quadrupole
    -0.08976538  0.19334402 -0.33488285  0.11194373 -0.49724107  0.68610463
    
    
   Dipole magnitude:  0.37599399
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       2.03940246
       1.38696340  2.03471997
      -2.40180083 -2.19332805  4.56285207
    
   Isotropic Polarizability:  2.87899150
    
    
    
    ====================
    ATOMIC DOMAIN: H4    
    ====================
    Domain center:  :  2.19441250  0.95667315 -1.65700650 / bohr
    Expansion center:  2.19441250  0.95667315 -1.65700650 / bohr
    Total charge    :  0.12633379
    
    Electronic multipole moments:
   Electronic Charge
    -0.87366621
    
   Electronic Dipole
    -0.04281865 -0.06262678  0.10847171
   ... with nuclear contribution
    -0.04281865 -0.06262678  0.10847171
    
   Electronic Quadrupole
    -0.54417673 -0.07175400  0.12427978 -0.55136636  0.13522556 -0.70751337
   ... with nuclear contribution
    -0.54417673 -0.07175400  0.12427978 -0.55136636  0.13522556 -0.70751337
    
    
   Dipole magnitude:  0.13236942
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       0.78530315
       0.11980683  0.68292783
      -0.20726312 -0.20486946  0.91896513
    
   Isotropic Polarizability:  0.79573204
    
    
    
    =========================
    BOND DOMAIN: C5    ,C1    
    =========================
    Domain center:  :  0.00000000  0.00000000  0.00000000 / bohr
    Expansion center:  0.00000000  0.00000000  0.00000000 / bohr
    Total charge    :  0.00000000
    
    Electronic multipole moments:
   Electronic Charge
     0.00000000
    
   Electronic Dipole
    -0.00000002 -0.00000001  0.00000000
    
   Electronic Quadrupole
     2.79566827  0.00000802 -0.00000001  0.50932527 -0.00000001  0.50930269
    
    
   Dipole magnitude:  0.00000002
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
      11.93962893
       0.00000627  0.49388088
       0.00000447  0.00000621  0.49406291
    
   Isotropic Polarizability:  4.30919091
    
    
    
    ====================
    ATOMIC DOMAIN: C5    
    ====================
    Domain center:  : -1.44186120  0.00000000  0.00000000 / bohr
    Expansion center: -1.44186120  0.00000000  0.00000000 / bohr
    Total charge    : -0.37899903
    
    Electronic multipole moments:
   Electronic Charge
    -6.37899903
    
   Electronic Dipole
     0.09892874 -0.00000401 -0.00000002
   ... with nuclear contribution
     0.09892874 -0.00000401 -0.00000002
    
   Electronic Quadrupole
    -4.19001661 -0.00000602 -0.00000001 -4.13923307 -0.00000002 -4.13924795
   ... with nuclear contribution
    -4.19001661 -0.00000602 -0.00000001 -4.13923307 -0.00000002 -4.13924795
    
    
   Dipole magnitude:  0.09892874
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       1.53088890
      -0.00025259  1.29789653
      -0.00029482 -0.00000500  1.29797490
    
   Isotropic Polarizability:  1.37558677
    
    
    
    =========================
    BOND DOMAIN: H6    ,C5    
    =========================
    Domain center:  : -1.81813685  0.95667315  0.00000000 / bohr
    Expansion center: -1.81813685  0.95667315  0.00000000 / bohr
    Total charge    :  0.00000000
    
    Electronic multipole moments:
   Electronic Charge
     0.00000000
    
   Electronic Dipole
     0.12480351 -0.35467694 -0.00000000
    
   Electronic Quadrupole
    -0.08976330 -0.38669222 -0.00000000  0.97318006 -0.00000001 -0.17513847
    
    
   Dipole magnitude:  0.37599421
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       2.03921665
      -2.77340676  5.83216284
      -0.00016236  0.00022492  0.76825711
    
   Isotropic Polarizability:  2.87987887
    
    
    
    ====================
    ATOMIC DOMAIN: H6    
    ====================
    Domain center:  : -2.19441250  1.91334630  0.00000000 / bohr
    Expansion center: -2.19441250  1.91334630  0.00000000 / bohr
    Total charge    :  0.12633159
    
    Electronic multipole moments:
   Electronic Charge
    -0.87366841
    
   Electronic Dipole
     0.04281604 -0.12525367  0.00000000
   ... with nuclear contribution
     0.04281604 -0.12525367  0.00000000
    
   Electronic Quadrupole
    -0.54417497  0.14350481 -0.00000000 -0.78559039  0.00000000 -0.47329799
   ... with nuclear contribution
    -0.54417497  0.14350481 -0.00000000 -0.78559039  0.00000000 -0.47329799
    
    
   Dipole magnitude:  0.13236954
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       0.78525213
      -0.23949017  1.03786679
      -0.00009159  0.00017684  0.56448166
    
   Isotropic Polarizability:  0.79586686
    
    
    
    =========================
    BOND DOMAIN: H7    ,C5    
    =========================
    Domain center:  : -1.81813685 -0.47833657  0.82850325 / bohr
    Expansion center: -1.81813685 -0.47833657  0.82850325 / bohr
    Total charge    :  0.00000000
    
    Electronic multipole moments:
   Electronic Charge
     0.00000000
    
   Electronic Dipole
     0.12480628  0.17733661 -0.30715887
    
   Electronic Quadrupole
    -0.08976533  0.19334400 -0.33488286  0.11194375 -0.49724103  0.68610463
    
    
   Dipole magnitude:  0.37599396
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       2.03923701
       1.38649561  2.03273622
      -2.40187707 -2.19046925  4.56669947
    
   Isotropic Polarizability:  2.87955756
    
    
    
    ====================
    ATOMIC DOMAIN: H7    
    ====================
    Domain center:  : -2.19441250 -0.95667315  1.65700650 / bohr
    Expansion center: -2.19441250 -0.95667315  1.65700650 / bohr
    Total charge    :  0.12633380
    
    Electronic multipole moments:
   Electronic Charge
    -0.87366620
    
   Electronic Dipole
     0.04281868  0.06262679 -0.10847170
   ... with nuclear contribution
     0.04281868  0.06262679 -0.10847170
    
   Electronic Quadrupole
    -0.54417672 -0.07175402  0.12427980 -0.55136637  0.13522556 -0.70751336
   ... with nuclear contribution
    -0.54417672 -0.07175402  0.12427980 -0.55136637  0.13522556 -0.70751336
    
    
   Dipole magnitude:  0.13236942
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
       0.78527137
       0.11962343  0.68260102
      -0.20742815 -0.20477471  0.91959281
    
   Isotropic Polarizability:  0.79582173
    
    
    
    =========================
    BOND DOMAIN: H8    ,C5    
    =========================
    Domain center:  : -1.81813685 -0.47833657 -0.82850325 / bohr
    Expansion center: -1.81813685 -0.47833657 -0.82850325 / bohr
    Total charge    : -0.00000000
    
    Electronic multipole moments:
   Electronic Charge
    -0.00000000
    
   Electronic Dipole
     0.12480628  0.17733662  0.30715887
    
   Electronic Quadrupole
    -0.08976533  0.19334400  0.33488287  0.11194374  0.49724103  0.68610463
    
    
   Dipole magnitude:  0.37599396
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
      2.03925164
      1.38650842 2.03273110
      2.40154316 2.19023494 4.56279489
    
   Isotropic Polarizability:  2.87825921
    
    
    
    ====================
    ATOMIC DOMAIN: H8    
    ====================
    Domain center:  : -2.19441250 -0.95667315 -1.65700650 / bohr
    Expansion center: -2.19441250 -0.95667315 -1.65700650 / bohr
    Total charge    :  0.12633381
    
    Electronic multipole moments:
   Electronic Charge
    -0.87366619
    
   Electronic Dipole
     0.04281868  0.06262678  0.10847170
   ... with nuclear contribution
     0.04281868  0.06262678  0.10847170
    
   Electronic Quadrupole
    -0.54417671 -0.07175402 -0.12427980 -0.55136635 -0.13522556 -0.70751335
   ... with nuclear contribution
    -0.54417671 -0.07175402 -0.12427980 -0.55136635 -0.13522556 -0.70751335
    
    
   Dipole magnitude:  0.13236941
    
    
    
     Symmetrized Local Polarizability Tensor                                                                                 
     ---------------------------------------                                                                                 
     mat. size =    3x   3
    
      0.78527415
      0.11962028 0.68260389
      0.20723910 0.20459186 0.91895538
    
   Isotropic Polarizability:  0.79561114
    
    === Charge capacitance for bonds ===
   H2    C1      1.24378143
   H3    C1      1.24461373
   H4    C1      1.24416201
   C5    C1      1.31217497
   H6    C5      1.24435768
   H7    C5      1.24401665
   H8    C5      1.24355862
    === =========================== ===
    
    
    
    
    **********************************************************************************
    *                                                                                *
    *                        The Molecular Multipole Moments                         *
    *                                                                                *
    **********************************************************************************
    Expansion center:  0.00000000  0.00000000  0.00000000 / bohr
    
    
    
   l=0
    
   xyz    Nuclear        Electronic     Molecular   
    
   000     18.00000000    -18.00000000     -0.00000000
    
   l=1
    
   xyz    Nuclear        Electronic     Molecular   
    
   100     -0.00000000     -0.00000044     -0.00000044
   010      0.00000000     -0.00000020     -0.00000020
   001      0.00000000     -0.00000003     -0.00000003
    
   l=2
    
   xyz    Nuclear        Electronic     Molecular   
    
   200     53.84024192    -65.57504663    -11.73480470
   110      0.00000000      0.00000924      0.00000924
   101      0.00000000      0.00000003      0.00000003
   020     10.98268218    -22.22064059    -11.23795841
   011      0.00000000      0.00000000      0.00000000
   002     10.98268216    -22.22066299    -11.23798083
    
     Molecular Polarizability Tensor                                                                                         
     -------------------------------                                                                                         
     mat. size =    3x   3
    
      31.94908856
       0.00019507 27.69107178
       0.00005394 -0.00000813 27.69159614
    
    **********************************************************************************

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="dynamic.loprop">
           <module cmlx:templateRef="dynamic.loprop">
               <array dataType="xsd:string" dictRef="m:label" size="7">C1 H2 H3 H4 C5 H6 H7</array>
               <array dataType="xsd:double" dictRef="m:lopropatomiccharge" size="7">-0.37899941 0.12633167 0.12633379 0.12633379 -0.37899903 0.12633159 0.12633380</array>
               <array dataType="xsd:double" dictRef="m:loproptotalatomicdipole" size="3">-0.00000044 -0.00000020 -0.00000003</array>
               <array dataType="xsd:double" dictRef="m:loproptotalatomicquadrupole" size="6">-11.73480470 0.00000924 0.00000003 -11.23795841 0.00000000 -11.23798083</array>
               <array dataType="xsd:double" dictRef="m:loproppolarizability" size="6">31.94908856 0.00019507 0.00005394 27.69107178 -0.00000813 27.69159614</array>
               <matrix cols="3" dataType="xsd:double" dictRef="m:lopropatomicdipole" rows="7">-0.09892881 0.00000401 0.00000000 -0.04281599 0.12525366 -0.00000000 -0.04281865 -0.06262678 -0.10847171 -0.04281865 -0.06262678 0.10847171 0.09892874 -0.00000401 -0.00000002 0.04281604 -0.12525367 0.00000000 0.04281868 0.06262679 -0.10847170</matrix>
               <matrix cols="6" dataType="xsd:double" dictRef="m:lopropatomicquadrupole" rows="7">-4.19001771 -0.00000604 -0.00000001 -4.13923380 0.00000000 -4.13924816 -0.54417492 0.14350476 0.00000000 -0.78559026 0.00000000 -0.47329791 -0.54417674 -0.07175400 -0.12427979 -0.55136637 -0.13522556 -0.70751336 -0.54417673 -0.07175400 0.12427978 -0.55136636 0.13522556 -0.70751337 -4.19001661 -0.00000602 -0.00000001 -4.13923307 -0.00000002 -4.13924795 -0.54417497 0.14350481 -0.00000000 -0.78559039 0.00000000 -0.47329799 -0.54417672 -0.07175402 0.12427980 -0.55136637 0.13522556 -0.70751336</matrix>
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="atomicdomain" pattern="\s*\=*\s*$\s*ATOMIC\sDOMAIN:.*" endPattern="\s*Isotropic\sPolarizability.*" endOffset="1" repeat="*">    <record />    <record>\s*ATOMIC\sDOMAIN:{A,m:label}</record>    <record repeat="3" />    <record>\s*Total\scharge\s*:{F,m:lopropatomiccharge}</record>    <record repeat="8" />    <record>{3F,m:lopropatomicdipole}</record>    <record repeat="4" />    <record>{6F,m:lopropatomicquadrupole}</record>      
           </template>  <template id="moments" pattern="\s*\*+\s*The\sMolecular\sMultipole\sMoments.*" endPattern="\s*$\s*\*+" offset="-2">    <record repeat="19" />    <record repeat="3" makeArray="true">.*\s+{F,m:loproptotalatomicdipole}</record>    <record repeat="5" />    <record repeat="6" makeArray="true">.*\s+{F,m:loproptotalatomicquadrupole}</record>    <record repeat="5" />    <record>\s*{F,x:col1}</record>    <record>\s*{F,x:col1}\s+{F,x:col2}</record>    <record>\s*{F,x:col1}\s+{F,x:col2}\s+{F,x:col3}</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:col1']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:col2']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:col3']" />    <transform process="joinArrays" xpath=".//cml:array[starts-with(@dictRef,'x:col')]" />    <transform process="addAttribute" xpath=".//cml:array[@dictRef='x:col1']" name="dictRef" value="m:loproppolarizability" />                                          
           </template>
       </templateList>
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:label']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:lopropatomiccharge']" />
   <transform process="createMatrix" xpath="." from=".//cml:array[@dictRef='m:lopropatomicdipole']" dictRef="m:lopropatomicdipole" />
   <transform process="createMatrix" xpath="." from=".//cml:array[@dictRef='m:lopropatomicquadrupole']" dictRef="m:lopropatomicquadrupole" />
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="move" xpath=".//cml:matrix" to="." />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
