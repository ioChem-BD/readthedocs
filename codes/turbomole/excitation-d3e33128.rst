.. _excitation-d3e33128:

excitation
==========

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
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | excitation                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Root values                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*.*excitation\s\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*yz.\*                         |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | tddft/excitation.xml              |
   +-----------------------------------+-----------------------------------+

**Input.**

::

                            1 singlet a excitation


    Total energy:                           -2746.252598530657    

    Excitation energy:                      0.8281956334307625E-01

    Excitation energy / eV:                  2.253635948754857    

    Excitation energy / nm:                  550.1520512883641    

    Excitation energy / cm^(-1):             18176.79307945692    


    Oscillator strength:

       velocity representation:             0.4630007707259613E-03

       length representation:               0.2517378232789616E-03

       mixed representation:                0.3414012393049747E-03


    Rotatory strength:

       velocity representation:             0.6787114468211505E-03

       velocity rep. / 10^(-40)erg*cm^3:     43.84802841470074    

       length representation:               0.5004590569299578E-03

       length rep. / 10^(-40)erg*cm^3:       32.33206549180494    


    Dominant contributions:

       occ. orbital  energy / eV   virt. orbital  energy / eV   |coeff.|^2*100
        135 a         -11.72         148 a          -5.04           56.5
        134 a         -11.84         149 a          -4.99           14.5
        133 a         -11.88         148 a          -5.04           10.8
        135 a         -11.72         146 a          -5.07            6.9
        135 a         -11.72         137 a          -7.60            2.3
    

    Change of electron number:

                0.000000


    Electric transition dipole moment (velocity rep.):

       x        0.000000        Norm:                  0.091574
       y        0.091574
       z        0.000000        Norm / debye:          0.232758


    Electric transition dipole moment (length rep.):

       x        0.000000        Norm:                  0.067523
       y        0.067523
       z        0.000000        Norm / debye:          0.171628


    Magnetic transition dipole moment / i:

       x        0.000000        Norm:                  0.007412
       y        0.007412
       z        0.000000        Norm / Bohr mag.:      2.031327


    Electric quadrupole transition moment:

      xx        0.388503
      yy       -0.349725        1/3*trace:             0.014240
      zz        0.003942
      xy        0.000000
      xz       -0.415837        Anisotropy:            0.963190
      yz        0.000000
       

**Input.**

::

                                1 a excitation


    Total energy:                           -2486.721896788767    

    Excitation energy:                      0.2232721523357345E-01

    Excitation energy / eV:                 0.6075546990936264    

    Excitation energy / nm:                  2040.709160696689    

    Excitation energy / cm^(-1):             4900.257317947948    


    Oscillator strength:

       velocity representation:             0.7239785565166725E-05

       length representation:               0.7472091694219293E-04

       mixed representation:                0.1620137669579867E-04


    Rotatory strength:

       velocity representation:             0.3453247981258833E-05

       velocity rep. / 10^(-40)erg*cm^3:    0.2230964518344803    

       length representation:               0.1425092244094837E-04

       length rep. / 10^(-40)erg*cm^3:      0.9206782279171773    


    Dominant contributions:

       occ. orbital  energy / eV   virt. orbital  energy / eV   |coeff.|^2*100
      110 a   beta        -9.34    114 a   beta        -5.25         65.3
      113 a   beta        -8.43    114 a   beta        -5.25         10.6
      106 a   beta       -10.52    114 a   beta        -5.25          8.4
      110 a   beta        -9.34    115 a   beta        -4.41          4.9
      102 a   beta       -11.59    114 a   beta        -5.25          1.8
    

    Change of electron number:

                0.000000


    Electric transition dipole moment (velocity rep.):

       x       -0.007809        Norm:                  0.022054
       y        0.018838
       z        0.008400        Norm / debye:          0.056057


    Electric transition dipole moment (length rep.):

       x       -0.004553        Norm:                  0.070852
       y        0.026700
       z        0.065470        Norm / debye:          0.180088


    Magnetic transition dipole moment / i:

       x        0.002706        Norm:                  0.003038
       y        0.001374
       z       -0.000154        Norm / Bohr mag.:      0.832734


    Electric quadrupole transition moment:

      xx       -0.393458
      yy        0.483604        1/3*trace:             0.012132
      zz       -0.053751
      xy        0.118843
      xz       -0.168409        Anisotropy:            0.984457
      yz        0.291550       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="excitation">
         <module cmlx:templateRef="excitation">
           <list cmlx:templateRef="label">
             <scalar dataType="xsd:integer" dictRef="t:serial">1</scalar>
             <scalar dataType="xsd:string" dictRef="t:type">singlet</scalar>
             <scalar dataType="xsd:string" dictRef="t:label">a</scalar>
           </list>
           <module cmlx:templateRef="energies">
             <scalar dataType="xsd:double" dictRef="t:totalEnergy">-2746.252598530657</scalar>
             <scalar dataType="xsd:double" dictRef="t:excitationEnergy" units="nonsi:electronvolt">2.253635948754857</scalar>
           </module>
           <module cmlx:templateRef="oscillator">
             <scalar dataType="xsd:double" dictRef="t:velocity">4.630007707259613E-4</scalar>
           </module> 
           <module cmlx:templateRef="contributions">
             <array dataType="xsd:integer" dictRef="t:occOrbitalNumber" size="5">135 134 133 135 135</array>
             <array dataType="xsd:string" dictRef="t:occOrbitalLabel" size="5">a a a a a</array>
             <array dataType="xsd:double" dictRef="t:occEnergy" size="5">-11.72 -11.84 -11.88 -11.72 -11.72</array>
             <array dataType="xsd:integer" dictRef="t:virtOrbitalNumber" size="5">148 149 148 146 137</array>
             <array dataType="xsd:string" dictRef="t:virtOrbitalLabel" size="5">a a a a a</array>
             <array dataType="xsd:double" dictRef="t:virtEnergy" size="5">-5.04 -4.99 -5.04 -5.07 -7.6</array>
             <array dataType="xsd:double" dictRef="t:coeff" size="5">56.5 14.5 10.8 6.9 2.3</array>
           </module>
           <module cmlx:templateRef="dipole">
             <scalar dataType="xsd:double" dictRef="cc:x3">0.0</scalar>
             <scalar dataType="xsd:double" dictRef="cc:y3">0.091574</scalar>
             <scalar dataType="xsd:double" dictRef="cc:z3">0.0</scalar>
             <scalar dataType="xsd:double" dictRef="t:norm">0.091574</scalar>
             <scalar dataType="xsd:double" dictRef="t:normDebye">0.232758</scalar>
           </module> 
         </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output2" id="excitation">
        <module cmlx:templateRef="excitation">
           <list cmlx:templateRef="label">
               <scalar dataType="xsd:integer" dictRef="t:serial">1</scalar>
               <scalar dataType="xsd:string" dictRef="t:label">a</scalar>
            </list>
            <module cmlx:templateRef="energies">
               <scalar dataType="xsd:double" dictRef="t:totalEnergy">-2486.721896788767</scalar>
               <scalar dataType="xsd:double" dictRef="t:excitationEnergy" units="nonsi:electronvolt">0.6075546990936264</scalar>
            </module>
            <module cmlx:templateRef="oscillator">
               <scalar dataType="xsd:double" dictRef="t:velocity">0.7239785565166725E-05</scalar>
            </module>
            <module cmlx:templateRef="contributions">
               <array dataType="xsd:integer" dictRef="t:occOrbitalNumber" size="5">110 113 106 110 102</array>
               <array dataType="xsd:string" dictRef="t:occOrbitalLabel" size="5">a a a a a</array>
               <array dataType="xsd:string" dictRef="t:occOrbitalSpin" size="5">beta beta beta beta beta</array>
               <array dataType="xsd:double" dictRef="t:occEnergy" size="5">-9.34 -8.43 -10.52 -9.34 -11.59</array>
               <array dataType="xsd:integer" dictRef="t:virtOrbitalNumber" size="5">114 114 114 115 114</array>
               <array dataType="xsd:string" dictRef="t:virtOrbitalLabel" size="5">a a a a a</array>
               <array dataType="xsd:string" dictRef="t:virtOrbitalSpin" size="5">beta beta beta beta beta</array>
               <array dataType="xsd:double" dictRef="t:virtEnergy" size="5">-5.25 -5.25 -5.25 -4.41 -5.25</array>
               <array dataType="xsd:double" dictRef="t:coeff" size="5">65.3 10.6 8.4 4.9 1.8</array>
            </module>
            <module cmlx:templateRef="dipole">
               <scalar dataType="xsd:double" dictRef="cc:x3">-0.007809</scalar>
               <scalar dataType="xsd:double" dictRef="t:norm">0.022054</scalar>
               <scalar dataType="xsd:double" dictRef="cc:y3">0.018838</scalar>
               <scalar dataType="xsd:double" dictRef="cc:z3">0.008400</scalar>
               <scalar dataType="xsd:double" dictRef="t:normDebye">0.056057</scalar>
            </module>
        </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="header" pattern="(\s+\w+){4}" endPattern=".*" endOffset="0">    <record id="label">{I,t:serial}{A,t:type}{A,t:label}excitation\s*</record>
           </template>  <template id="header" pattern="(\s+\w+){3}" endPattern=".*" endOffset="0">    <record id="label">{I,t:serial}{A,t:label}excitation\s*</record>
           </template>       
       </templateList>
   <templateList>  <template id="energies" pattern="\s*Total\senergy.*" endPattern="\s*Excitation.*cm.*" endOffset="1">    <record id="energy">\s*Total\senergy:{F,t:totalEnergy}</record>    <record repeat="3" />    <record>\s*Excitation\senergy\s\/\seV:{F,t:excitationEnergy}</record>    <record repeat="*" />
           </template>  <template id="oscillator" pattern="\s*Oscillator\s*strength.*" endPattern="\s*mixed\srepresentation.*">    <record repeat="2" />    <record>\s*velocity\srepresentation:{E,t:velocity}</record>    <record repeat="*" />
           </template>  <template id="contributions" pattern="\s*Dominant\scontributions:.*" endPattern="\s\w.*$\s*" endOffset="0">    <record repeat="3" />    <templateList>      <template id="open" pattern=".*(alpha|beta).*" endPattern="~">        <record repeat="*" makeArray="true">{I,t:occOrbitalNumber}{A,t:occOrbitalLabel}{A,t:occOrbitalSpin}{F,t:occEnergy}{I,t:virtOrbitalNumber}{A,t:virtOrbitalLabel}{A,t:virtOrbitalSpin}{F,t:virtEnergy}{F,t:coeff}</record>        <transform process="pullup" xpath=".//cml:array" repeat="2" />
                   </template>      <template id="closed" pattern=".*" endPattern="">        <record repeat="*" makeArray="true">{I,t:occOrbitalNumber}{A,t:occOrbitalLabel}{F,t:occEnergy}{I,t:virtOrbitalNumber}{A,t:virtOrbitalLabel}{F,t:virtEnergy}{F,t:coeff}</record>        <transform process="pullup" xpath=".//cml:array" repeat="2" />
                   </template>
               </templateList>                   
           </template>  <template id="contributions" pattern="\s*Dominant\scontributions:.*" endPattern="\s\w.*$\s*" endOffset="0">    <record repeat="3" />    <record repeat="*" makeArray="true">{I,t:occOrbitalNumber}{A,t:occOrbitalLabel}{F,t:occEnergy}{I,t:virtOrbitalNumber}{A,t:virtOrbitalLabel}{F,t:virtEnergy}{F,t:coeff}</record>    <transform process="pullup" xpath=".//cml:array" />         
           </template>  <template id="dipole" pattern="\s*Electric\stransition\sdipole\smoment\s*\(velocity\srep.*" endPattern="\s*z.*" endOffset="1">    <record repeat="2" />    <record>\s*x{F,cc:x3}Norm:{F,t:norm}</record>    <record>\s*y{F,cc:y3}</record>    <record>\s*z{F,cc:z3}Norm\s/\sdebye:{F,t:normDebye}</record>    <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:x3']" />    <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:z3']" />    <transform process="pullup" xpath=".//cml:scalar[@dictRef='t:norm']" />    <transform process="pullup" xpath=".//cml:scalar[@dictRef='t:normDebye']" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:module[@ cmlx:templateRef='header']/cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='t:excitationEnergy']" value="nonsi:electronvolt" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
