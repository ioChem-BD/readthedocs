.. _energies-d3e24508:

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
   | *source*                          | MOPAC log                         |
   +-----------------------------------+-----------------------------------+
   | id                                | energies                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Energies section                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | .*\sTOTAL\sENERGY\s*=.\*          |
   +-----------------------------------+-----------------------------------+
   | pattern2                          | \\s*ZERO\sPOINT\sENERGY.\*        |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*SCF\sCALCULATIONS.\*          |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*WALL-CLOCK\sTIME.\*           |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | \\                                |
   |                                   | s*NORMAL\sCOORDINATE\sANALYSIS.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern4                       | \\s*CART                          |
   |                                   | ESIAN\sCOORDINATE\sDERIVATIVES.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern5                       | \\                                |
   |                                   | s*NORMAL\sCOORDINATE\sANALYSIS.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern6                       | \\s*GRADIENT\s+NORM.\*            |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | energies.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

             TOTAL ENERGY            =   -3024354.64134 KCAL/MOL
             ENERGY OF ATOMS         =    3019975.06610 KCAL/MOL
                                 SUM =      -4379.57525 KCAL/MOL
             DISPERSION ENERGY       =          0.00000 KCAL/MOL
             MM CORRECTION FOR >N-   =        -10.86572 KCAL/MOL
                                 SUM =      -4390.44097 KCAL/MOL

    WARNING - An energy term is missing!


             TOTAL ENERGY            =    -131148.53702 EV
             ELECTRONIC ENERGY       =   -7116479.16086 EV
             CORE-CORE REPULSION     =    6985330.62384 EV

             GRADIENT NORM           =          3.24521
       

**Input.**

::

             ZERO POINT ENERGY      59.540 KCAL/MOL


              NORMAL COORDINATE ANALYSIS (Total motion = 1 Angstrom)   
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="energies">
           <module cmlx:templateRef="energies">
               <scalar dataType="xsd:double" dictRef="mp:atomener" units="nonsi:hartree">4812.63226533696</scalar>
               <scalar dataType="xsd:double" dictRef="mp:dispenergy" units="nonsi:hartree">0.0</scalar>
               <scalar dataType="xsd:double" dictRef="mp:mmcorrectionforn" units="nonsi:hartree">-0.017315611392</scalar>
               <scalar dataType="xsd:double" dictRef="mp:totalsum" units="nonsi:hartree">-6.996606729791999</scalar>
               <scalar dataType="xsd:double" dictRef="cc:totalener" units="nonsi:hartree">-4819.618085616211</scalar>
               <scalar dataType="xsd:string" dictRef="cc:electener" units="nonsi:hartree">-261525.69025120902</scalar>
               <scalar dataType="xsd:double" dictRef="cc:nucrepener" units="nonsi:hartree">256706.07216559278</scalar>
            </module>         
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="energies2">
           <module cmlx:templateRef="energies">
                  <scalar dataType="xsd:double" dictRef="cc:zeropoint" units="nonsi:hartree">0.094882944</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern=".*ZERO\sPOINT\sENERGY\s*.*" endPattern=".*" endOffset="0">    <record>.*ZERO\sPOINT\sENERGY\s*{F,cc:zeropoint}KCAL/MOL\s*</record>    <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=0.0015936" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />
           </template>  <template pattern="\s*ENERGY\sOF\sATOMS.*KCAL/MOL" endPattern=".*" endOffset="0">    <record>\s*ENERGY\sOF\sATOMS\s*={F,mp:atomener}KCAL/MOL</record>    <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=0.0015936" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />
           </template>  <template pattern="\s*DISPERSION\sENERGY.*KCAL/MOL" endPattern=".*" endOffset="0">    <record>\s*DISPERSION\sENERGY\s*={F,mp:dispenergy}KCAL/MOL</record>    <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=0.0015936" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />
           </template>  <template pattern="\s*MM\sCORRECTION\sFOR.*N-.*KCAL/MOL" endPattern="\s*SUM.*" endOffset="1">    <record>\s*MM\sCORRECTION\sFOR.*N-\s*={F,mp:mmcorrectionforn}KCAL/MOL</record>    <record>\s*SUM\s*={F,mp:totalsum}KCAL/MOL</record>    <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=0.0015936" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />        
           </template>  <template pattern="\s*TOTAL\sENERGY.*EV" endPattern=".*" endOffset="0">    <record>\s*TOTAL\sENERGY\s*={F,cc:totalener}EV</record>    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:totalener']" args="operator=multiply operand=0.0367493088" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />
           </template>  <template pattern="\s*ELECTRONIC\sENERGY.*EV" endPattern=".*" endOffset="0">    <record>\s*ELECTRONIC\sENERGY\s*={X,cc:electener}EV</record>    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:electener']" args="operator=multiply operand=0.0367493088" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />         
           </template>  <template pattern="\s*CORE-CORE\sREPULSION.*EV" endPattern=".*" endOffset="0">    <record>\s*CORE-CORE\sREPULSION\s*={F,cc:nucrepener}EV</record>    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:nucrepener']" args="operator=multiply operand=0.0367493088" />    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
