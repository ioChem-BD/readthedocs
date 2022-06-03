.. _excitation.energy-d3e4290:

excitation.energy
=================

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
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | excitation.energy                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Excitation energy calculation                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | .*EXCITATION&#92;sENERGY&#92;sCALCULATION,&#92;sa&#92;spart&#92;sof&#92;sthe&#92;sADF-RESPONSE&#92;scode.\*                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Normal&#92;stermination&#92;sof&#92;sEXCITATION&#92;sprogram&#92;spart.\*                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -2                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | results/excitationenergy/excitation.energy.xml                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   **************************************************************************
   *                                                                        *
   *        EXCITATION ENERGY CALCULATION, a part of the ADF-RESPONSE code  *
   ...

   **************************************************************************
   *                                                                        *
   *   Final excitation energies from Davidson algorithm                    *
   *                                                                        *
   **************************************************************************

    Symmetry A2   

    Excitation energies E in a.u. and eV, dE wrt prev. cycle,
    oscillator strengths f in a.u.

    no.  E/a.u.        E/eV      f           dE/a.u.
    -----------------------------------------------------
      1 0.17896      4.8698     0.41613E-02  0.57E-09
      2 0.18115      4.9292     0.67918E-03  0.26E-08
      3 0.19174      5.2175     0.13150E-06  0.14E-10
      4 0.20939      5.6978     0.29712E-02  0.24E-09
      5 0.21423      5.8296     0.83640E-04  0.18E-11
      6 0.23518      6.3996      1.1274      0.19E-07
    
    Transition dipole moments mu (x,y,z) in a.u.
    (weak excitations are not printed)

    no.  E/eV          f                       mu (x,y,z)
    ------------------------------------------------------------------
      1  4.8698     0.41613E-02   0.0000      0.26355E-16 -0.18676    
      2  4.9292     0.67918E-03   0.0000     -0.47650E-16 -0.74994E-01
      4  5.6978     0.29712E-02   0.0000     -0.21366E-17 -0.14589    
      5  5.8296     0.83640E-04   0.0000      0.19705E-16  0.24200E-01
      6  6.3996      1.1274       0.0000      0.76377E-17   2.6816    
    

   **************************************************************************
   *                                                                        *
   *   Final excitation energies from Davidson algorithm                    *
   *                                                                        *
   **************************************************************************                                                                          

    Symmetry E1   

    Excitation energies E in a.u. and eV, dE wrt prev. cycle,
    oscillator strengths f in a.u.

    no.  E/a.u.        E/eV      f           dE/a.u.
    -----------------------------------------------------
      1 0.11647      3.1694     0.31676E-07  0.92E-09
      2 0.13433      3.6553     0.11852E-06  0.14E-07
      3 0.18185      4.9483     0.73217E-03  0.50E-09
      4 0.18596      5.0602     0.64273E-02  0.83E-07
      5 0.19245      5.2367     0.94836E-03  0.48E-06
      6 0.20111      5.4724     0.15097E-01  0.28E-06
    
    Transition dipole moments mu (x,y,z) in a.u.
    (weak excitations are not printed)

    no.  E/eV          f                       mu (x,y,z)
    ------------------------------------------------------------------
      3  4.9483     0.73217E-03 -0.77714E-01   0.0000       0.0000    
      4  5.0602     0.64273E-02  0.22769       0.0000       0.0000    
      5  5.2367     0.94836E-03  0.85976E-01   0.0000       0.0000    
      6  5.4724     0.15097E-01 -0.33556       0.0000       0.0000    
    
    
    Normal termination of EXCITATION program part 
       

.. container:: formalpara-title

   **Input**

::

   **************************************************************************
   *                                                                        *
   *        EXCITATION ENERGY CALCULATION, a part of the ADF-RESPONSE code  *
   ...
   **************************************************************************
   *                                                                        *
   *   Final excitation energies from Davidson algorithm                    *
   *                                                                        *
   **************************************************************************

       Number of loops in Davidson routine     =   11                    
       Number of matrix-vector multiplications =  223                    
       Type of excitations = SINGLET-SINGLET                                 
                                                                             

    Symmetry A1   

    Excitation energies E in a.u. and eV, dE wrt prev. cycle,
    oscillator strengths f in a.u.

    no.  E/a.u.        E/eV      f           dE/a.u.
    -----------------------------------------------------
      1 0.69890E-01  1.9018     0.17607E-03  0.42E-09
      2 0.74927E-01  2.0389     0.51785E-03  0.99E-09
      3 0.75482E-01  2.0540     0.64311E-09  0.81E-13
      4 0.77977E-01  2.1219     0.70275E-04  0.21E-09
      5 0.82967E-01  2.2576     0.13808E-03  0.15E-07
      6 0.98684E-01  2.6853     0.33791E-05  0.50E-11
      7 0.10348      2.8157     0.18201E-03  0.13E-09
      8 0.10356      2.8181     0.69163E-03  0.28E-09
      9 0.10664      2.9018     0.12917E-03  0.21E-09
     10 0.10677      2.9053     0.41951E-06  0.21E-10
     11 0.10732      2.9203     0.30798E-05  0.38E-10
     12 0.10821      2.9445     0.37521E-05  0.22E-09
     13 0.10936      2.9758     0.33188E-02  0.19E-08
     14 0.10993      2.9914     0.66342E-03  0.53E-08
     15 0.11069      3.0120     0.10037E-02  0.57E-09
     16 0.11226      3.0548     0.32440E-05  0.20E-09
     17 0.11419      3.1073     0.20923E-02  0.46E-09
     18 0.11422      3.1081     0.92867E-08  0.11E-12
     19 0.11548      3.1423     0.49782E-05  0.13E-09
     20 0.11762      3.2006     0.53162E-03  0.10E-06
     21 0.11981      3.2602     0.27594E-01  0.32E-07
     22 0.12020      3.2707     0.17331E-01  0.90E-08
     23 0.12131      3.3009     0.15409      0.50E-06
    
    Transition dipole moments mu (x,y,z) in a.u.
    (weak excitations are not printed)

    no.  E/eV          f                       mu (x,y,z)
    ------------------------------------------------------------------
      1  1.9018     0.17607E-03   0.0000       0.0000      0.61472E-01
      2  2.0389     0.51785E-03   0.0000       0.0000      0.10182    
      4  2.1219     0.70275E-04   0.0000       0.0000      0.36767E-01
      5  2.2576     0.13808E-03   0.0000       0.0000     -0.49964E-01
      7  2.8157     0.18201E-03   0.0000       0.0000     -0.51365E-01
      8  2.8181     0.69163E-03   0.0000       0.0000      0.10009    
      9  2.9018     0.12917E-03   0.0000       0.0000      0.42625E-01
     13  2.9758     0.33188E-02   0.0000       0.0000     -0.21336    
     14  2.9914     0.66342E-03   0.0000       0.0000     -0.95144E-01
     15  3.0120     0.10037E-02   0.0000       0.0000     -0.11662    
     17  3.1073     0.20923E-02   0.0000       0.0000      0.16578    
     20  3.2006     0.53162E-03   0.0000       0.0000      0.82339E-01
     21  3.2602     0.27594E-01   0.0000       0.0000      0.58777    
     22  3.2707     0.17331E-01   0.0000       0.0000     -0.46506    
     23  3.3009     0.15409       0.0000       0.0000      -1.3804    
    
    Rotatory strengths R in 10**(-40) esu**2 * cm**2 ,
    (multiply by 1.07827 to obtain reduced rotatory strengths),
    magnetic transition dipole vectors m in a.u.:

    no.    R                              m (x,y,z)
    ---------------------------------------------------------------
      1    0.79122E-15     0.0000         0.0000         0.0000    
      2    0.82945E-14     0.0000         0.0000         0.0000    
      3    0.63050E-17     0.0000         0.0000         0.0000    
      4    0.13202E-14     0.0000         0.0000         0.0000    
      5    0.58909E-14     0.0000         0.0000         0.0000    
      6   -0.43046E-16     0.0000         0.0000         0.0000    
      7    0.57639E-15     0.0000         0.0000         0.0000    
      8    0.11262E-14     0.0000         0.0000         0.0000    
      9    0.23067E-15     0.0000         0.0000         0.0000    
     10   -0.20333E-16     0.0000         0.0000         0.0000    
     11    0.78971E-16     0.0000         0.0000         0.0000    
     12   -0.11537E-15     0.0000         0.0000         0.0000    
     13   -0.21232E-14     0.0000         0.0000         0.0000    
     14   -0.70305E-15     0.0000         0.0000         0.0000    
     15    0.81698E-14     0.0000         0.0000         0.0000    
     16   -0.68114E-15     0.0000         0.0000         0.0000    
     17    0.17148E-14     0.0000         0.0000         0.0000    
     18    0.54807E-16     0.0000         0.0000         0.0000    
     19    0.67651E-16     0.0000         0.0000         0.0000    
     20    0.33923E-14     0.0000         0.0000         0.0000    
     21   -0.47237E-13     0.0000         0.0000         0.0000    
     22   -0.34492E-13     0.0000         0.0000         0.0000    
     23    0.47859E-13     0.0000         0.0000         0.0000    

    Normal termination of EXCITATION program part  
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="excitation.energy">
           <module cmlx:lineCount="493" cmlx:templateRef="excitation.energy">
               <module cmlx:lineCount="72" cmlx:templateRef="excitationEnergies">
                   <scalar dataType="xsd:string" dictRef="cc:symm">A2</scalar>
                   <module cmlx:lineCount="11" cmlx:templateRef="energies">
                       <array dataType="xsd:integer" dictRef="cc:serial" size="6">1 2 3 4 5 6</array>
                       <array dataType="xsd:string" dictRef="cc:energy" size="6">0.17896 0.18115 0.19174 0.20939 0.21423 0.23518</array>
                       <array dataType="xsd:string" dictRef="cc:oscillator" size="6">0.41613E-02 0.67918E-03 0.13150E-06 0.29712E-02 0.83640E-04 1.1274</array>
                       <array dataType="xsd:string" dictRef="cc:energyDiff" size="6">0.57E-09 0.26E-08 0.14E-10 0.24E-09 0.18E-11 0.19E-07</array>
                   </module>
                   <module cmlx:lineCount="10" cmlx:templateRef="dipole">
                       <array dataType="xsd:integer" dictRef="cc:serial" size="5">1 2 4 5 6</array>
                       <array dataType="xsd:string" dictRef="cc:energy" size="5">4.8698 4.9292 5.6978 5.8296 6.3996</array>
                       <array dataType="xsd:string" dictRef="cc:energyDiff" size="5">0.41613E-02 0.67918E-03 0.29712E-02 0.83640E-04 1.1274</array>
                       <array dataType="xsd:string" dictRef="cc:muX" size="5">0.0000 0.0000 0.0000 0.0000 0.0000</array>
                       <array dataType="xsd:string" dictRef="cc:muY" size="5">0.26355E-16 -0.47650E-16 -0.21366E-17 0.19705E-16 0.76377E-17</array>
                       <array dataType="xsd:string" dictRef="cc:muZ" size="5">-0.18676 -0.74994E-01 -0.14589 0.24200E-01 2.6816</array>
                   </module>
               </module>
               <module cmlx:lineCount="72" cmlx:templateRef="excitationEnergies">
                   <scalar dataType="xsd:string" dictRef="cc:symm">E1</scalar>
                   <module cmlx:lineCount="11" cmlx:templateRef="energies">
                       <array dataType="xsd:integer" dictRef="cc:serial" size="6">1 2 3 4 5 6</array>
                       <array dataType="xsd:string" dictRef="cc:energy" size="6">0.11647 0.13433 0.18185 0.18596 0.19245 0.20111</array>
                       <array dataType="xsd:string" dictRef="cc:oscillator" size="6">0.31676E-07 0.11852E-06 0.73217E-03 0.64273E-02 0.94836E-03 0.15097E-01
                       </array>
                       <array dataType="xsd:string" dictRef="cc:energyDiff" size="6">0.92E-09 0.14E-07 0.50E-09 0.83E-07 0.48E-06 0.28E-06</array>
                   </module>
                   <module cmlx:lineCount="9" cmlx:templateRef="dipole">
                       <array dataType="xsd:integer" dictRef="x:serial" size="4">3 4 5 6</array>
                       <array dataType="xsd:string" dictRef="cc:energy" size="4">4.9483 5.0602 5.2367 5.4724</array>
                       <array dataType="xsd:string" dictRef="cc:energyDiff" size="4">0.73217E-03 0.64273E-02 0.94836E-03 0.15097E-01</array>
                       <array dataType="xsd:string" dictRef="cc:muX" size="4">-0.77714E-01 0.22769 0.85976E-01 -0.33556</array>
                       <array dataType="xsd:string" dictRef="cc:muY" size="4">0.0000 0.0000 0.0000 0.0000</array>
                       <array dataType="xsd:string" dictRef="cc:muZ" size="4">0.0000 0.0000 0.0000 0.0000</array>
                   </module>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="excitation.energy2">
          <module cmlx:templateRef="excitation.energy" dictRef="cc:userDefinedModule">
             <module cmlx:templateRef="excitationEnergies">
                <scalar dataType="xsd:string" dictRef="cc:symm">A1</scalar>
                <module cmlx:templateRef="energies">
                   <array dataType="xsd:integer" dictRef="cc:serial" size="23">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23</array>
                   <array dataType="xsd:string" dictRef="cc:energy" size="23">0.69890E-01 0.74927E-01 0.75482E-01 0.77977E-01 0.82967E-01 0.98684E-01 0.10348 0.10356 0.10664 0.10677 0.10732 0.10821 0.10936 0.10993 0.11069 0.11226 0.11419 0.11422 0.11548 0.11762 0.11981 0.12020 0.12131</array>
                   <array dataType="xsd:string" dictRef="cc:oscillator" size="23">0.17607E-03 0.51785E-03 0.64311E-09 0.70275E-04 0.13808E-03 0.33791E-05 0.18201E-03 0.69163E-03 0.12917E-03 0.41951E-06 0.30798E-05 0.37521E-05 0.33188E-02 0.66342E-03 0.10037E-02 0.32440E-05 0.20923E-02 0.92867E-08 0.49782E-05 0.53162E-03 0.27594E-01 0.17331E-01 0.15409</array>
                   <array dataType="xsd:string" dictRef="cc:energyDiff" size="23">0.42E-09 0.99E-09 0.81E-13 0.21E-09 0.15E-07 0.50E-11 0.13E-09 0.28E-09 0.21E-09 0.21E-10 0.38E-10 0.22E-09 0.19E-08 0.53E-08 0.57E-09 0.20E-09 0.46E-09 0.11E-12 0.13E-09 0.10E-06 0.32E-07 0.90E-08 0.50E-06</array>
                </module>
                <module cmlx:templateRef="dipole">
                   <array dataType="xsd:integer" dictRef="cc:serial" size="15">1 2 4 5 7 8 9 13 14 15 17 20 21 22 23</array>
                   <array dataType="xsd:string" dictRef="cc:energy" size="15">1.9018 2.0389 2.1219 2.2576 2.8157 2.8181 2.9018 2.9758 2.9914 3.0120 3.1073 3.2006 3.2602 3.2707 3.3009</array>
                   <array dataType="xsd:string" dictRef="cc:energyDiff" size="15">0.17607E-03 0.51785E-03 0.70275E-04 0.13808E-03 0.18201E-03 0.69163E-03 0.12917E-03 0.33188E-02 0.66342E-03 0.10037E-02 0.20923E-02 0.53162E-03 0.27594E-01 0.17331E-01 0.15409</array>
                   <array dataType="xsd:string" dictRef="cc:muX" size="15">0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000</array>
                   <array dataType="xsd:string" dictRef="cc:muY" size="15">0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000</array>
                   <array dataType="xsd:string" dictRef="cc:muZ" size="15">0.61472E-01 0.10182 0.36767E-01 -0.49964E-01 -0.51365E-01 0.10009 0.42625E-01 -0.21336 -0.95144E-01 -0.11662 0.16578 0.82339E-01 0.58777 -0.46506 -1.3804</array>
                </module>
                <module cmlx:templateRef="rotatory">
                   <array dataType="xsd:integer" dictRef="cc:serial" size="23">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23</array>
                   <array dataType="xsd:string" dictRef="a:strengths" size="23">0.79122E-15 0.82945E-14 0.63050E-17 0.13202E-14 0.58909E-14 -0.43046E-16 0.57639E-15 0.11262E-14 0.23067E-15 -0.20333E-16 0.78971E-16 -0.11537E-15 -0.21232E-14 -0.70305E-15 0.81698E-14 -0.68114E-15 0.17148E-14 0.54807E-16 0.67651E-16 0.33923E-14 -0.47237E-13 -0.34492E-13 0.47859E-13</array>
                   <array dataType="xsd:string" dictRef="cc:mX" size="23">0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000</array>
                   <array dataType="xsd:string" dictRef="cc:mY" size="23">0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000</array>
                   <array dataType="xsd:string" dictRef="cc:mZ" size="23">0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000</array>
                </module>
               </module>
           </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="excitationEnergies" pattern="\s*\*\s+Final\sexcitation\senergies\sfrom\sDavidson\salgorithm.*" endPattern="\s*\*\s+Final\sexcitation\senergies\sfrom\sDavidson\salgorithm.*" endPattern2="\s*Eigenvalues\sof\ssmall.*" endPattern3="\sAll\sSINGLET-SINGLET\sexcitation\senergies.*" endPattern4="~" repeat="*">    <templateList>      <template pattern="\s*Symmetry.*" endPattern=".*" endOffset="0">        <record id="symmetry">\s*Symmetry{A,cc:symm}</record>
                   </template>      <template id="energies" pattern="\s*Excitation\senergies\sE\sin.*" endPattern="\s+\d.*$\s*" endOffset="1">        <record repeat="5" />        <record repeat="*" makeArray="true">{I,cc:serial}{A,cc:energy}\s+\S+\s+{A,cc:oscillator}\s+{A,cc:energyDiff}.*
                       </record>
                   </template>      <template id="dipole" pattern="\s*Transition\sdipole\smoments\smu.*" endPattern="\s+\d.*$\s*" endOffset="1">        <record repeat="5" />        <record repeat="*" makeArray="true">{I,cc:serial}{A,cc:energy}{A,cc:energyDiff}{A,cc:muX}{A,cc:muY}{A,cc:muZ}
                       </record>
                   </template>      <template id="rotatory" pattern="\s*Rotatory\sstrengths\sR\sin.*" endPattern="\s+\d.*$\s*" endOffset="1">        <record repeat="6" />        <record repeat="*" makeArray="true">{I,cc:serial}{A,a:strengths}{A,cc:mX}{A,cc:mY}{A,cc:mZ}
                       </record>
                   </template>               
               </templateList>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:symm']" repeat="2" />
   <transform process="pullup" xpath=".//cml:array" repeat="1" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
