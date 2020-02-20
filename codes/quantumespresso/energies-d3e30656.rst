.. _energies-d3e30656:

energies
========

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
   | *source*                          | QuantumEspresso log               |
   +-----------------------------------+-----------------------------------+
   | id                                | energies                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Energy section                    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*the\sFermi\senergy\sis.\*     |
   +-----------------------------------+-----------------------------------+
   | pattern2                          | \\s*!\s*total\senergy.\*          |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*absolute\smagnetization.\*    |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*charge\sdensity\sin           |
   |                                   | side\sthe\sWigner\-Seitz\scell.\* |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | energies.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        the Fermi energy is     1.2269 ev

   !    total energy              =  -14856.08746891 Ry
        Harris-Foulkes estimate   =  -14856.08746891 Ry
        estimated scf accuracy    <          9.5E-10 Ry

        The total energy is the sum of the following terms:

        one-electron contribution = -145858.09904553 Ry
        hartree contribution      =   73114.21474057 Ry
        xc contribution           =   -1873.98188981 Ry
        ewald contribution        =   59756.12730301 Ry
        Dispersion Correction     =      -1.71103674 Ry
        Hubbard energy            =       7.44204694 Ry
        smearing contrib. (-TS)   =      -0.07958735 Ry

        total magnetization       =     0.00 Bohr mag/cell
        absolute magnetization    =   198.74 Bohr mag/cell 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="energies">
           <module cmlx:templateRef="energies">
               <scalar dataType="xsd:double" dictRef="qex:fermiener" units="nonsi:electronvolt">1.2269</scalar>
               <scalar dataType="xsd:double" dictRef="qex:totalener" units="nonsi:electronvolt">-202127,440544</scalar>
               <scalar dataType="xsd:double" dictRef="qex:harrisfoulkes" units="nonsi:electronvolt">-202127,440544</scalar>
               <scalar dataType="xsd:string" dictRef="qex:sscfaccuracy" units="nonsi:electronvolt">0,000000</scalar>
               <scalar dataType="xsd:double" dictRef="qex:oneelec" units="nonsi:electronvolt">-1984501,256094</scalar>
               <scalar dataType="xsd:double" dictRef="qex:hartee" units="nonsi:electronvolt">994769,930093</scalar>
               <scalar dataType="xsd:double" dictRef="qex:xc" units="nonsi:electronvolt">-25496,831774</scalar>
               <scalar dataType="xsd:double" dictRef="qex:ewald" units="nonsi:electronvolt">813023,825678</scalar>
               <scalar dataType="xsd:double" dictRef="qex:dispcorr" units="nonsi:electronvolt">-23,279849</scalar>
               <scalar dataType="xsd:double" dictRef="qex:hubbardener" units="nonsi:electronvolt">101,254244</scalar>
               <scalar dataType="xsd:double" dictRef="qex:totalmag" units="bohrmag.cell-1">0.00</scalar>
               <scalar dataType="xsd:double" dictRef="cc:absolutemag" units="bohrmag.cell-1">198.74</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="*">\s+the\sFermi\senergy\sis{F,qex:fermiener}ev</record>
   <record repeat="*">\s*</record>
   <record repeat="*">\s*!\s*total\senergy\s+={F,qex:totalener}Ry</record>
   <record repeat="*">\s+Harris-Foulkes\sestimate\s+={F,qex:harrisfoulkes}Ry</record>
   <record repeat="*">\s+estimated\sscf\saccuracy.{8}{A,qex:sscfaccuracy}\sRy</record>
   <record repeat="3" />
   <record repeat="*">\s+one-electron\scontribution\s={F,qex:oneelec}Ry</record>
   <record repeat="*">\s+hartree\scontribution\s+={F,qex:hartee}Ry</record>
   <record repeat="*">\s+xc\scontribution\s+={F,qex:xc}Ry</record>
   <record repeat="*">\s+ewald\scontribution\s+={F,qex:ewald}Ry</record>
   <record repeat="*">\s+Dispersion\sCorrection\s+={F,qex:dispcorr}Ry</record>
   <record repeat="*">\s+Hubbard\senergy\s+={F,qex:hubbardener}Ry</record>
   <record repeat="*">\s+smearing\scontrib.\s(-TS)\s+={F,qex:smearing}Ry</record>
   <record repeat="1" />
   <record repeat="*">\s+total\smagnetization\s+={F,qex:totalmag}Bohr\smag/cell</record>
   <record repeat="*">\s+absolute\smagnetization\s+={F,cc:absolutemag}Bohr\smag/cell</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='qex:totalener' or                 @dictRef='qex:harrisfoulkes' or                @dictRef='qex:sscfaccuracy' or                 @dictRef='qex:oneelec' or                @dictRef='qex:hartee' or                @dictRef='qex:xc' or                @dictRef='qex:ewald' or                @dictRef='qex:dispcorr' or                @dictRef='qex:hubbardener' or                @dictRef='qex:smearing']" args="operator=multiply operand=13.605698066 format=####0.000000" />
   <transform process="addUnits" xpath=".//cml:scalar[ @dictRef='qex:fermiener' or               @dictRef='qex:totalener' or                @dictRef='qex:harrisfoulkes' or               @dictRef='qex:sscfaccuracy' or                @dictRef='qex:oneelec' or               @dictRef='qex:hartee' or               @dictRef='qex:xc' or               @dictRef='qex:ewald' or               @dictRef='qex:dispcorr' or               @dictRef='qex:hubbardener' or               @dictRef='qex:smearing']" value="nonsi:electronvolt" />
   <transform process="addUnits" xpath=".//cml:scalar[ @dictRef='qex:totalmag' or               @dictRef='cc:absolutemag']" value="bohrmag.cell-1" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
