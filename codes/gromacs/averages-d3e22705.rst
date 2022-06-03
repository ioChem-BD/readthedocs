.. _averages-d3e22705:

averages
========

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
   | *source*                                                                                                                   | GROMACS log                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | averages                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Averages                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | .*$.*A&#92;sV&#92;sE&#92;sR&#92;sA&#92;sG&#92;sE&#92;sS.\*                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s\*                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/averages.xml                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       <======  ###############  ==>
       <====  A V E R A G E S  ====>
       <==  ###############  ======>

       Statistics over 8000001 steps using 800001 frames

      Energies (kJ/mol)
     Harmonic Pot.            U-B    Proper Dih.          LJ-14     Coulomb-14
       8.27585e+04    4.39759e+05    8.93986e+04   -8.50504e+03   -4.55445e+06
           LJ (SR)  Disper. corr.   Coulomb (SR)   Coul. recip.      Potential
      -4.62212e+05   -1.95856e+04   -2.14402e+05    3.95741e+03   -4.64328e+06
       Kinetic En.   Total Energy    Temperature Pres. DC (bar) Pressure (bar)
       7.07850e+05   -3.93543e+06    3.00049e+02   -1.01381e+02    1.00144e+00
      Constr. rmsd
       0.00000e+00

             Box-X          Box-Y          Box-Z
       1.47498e+01    1.47498e+01    1.47498e+01

      Total Virial (kJ/mol)
       2.35874e+05    2.02336e+02   -2.18297e+02
       2.02521e+02    2.35934e+05   -1.01075e+02
      -2.18124e+02   -1.01058e+02    2.35752e+05

      Pressure (bar)
       1.46167e+00    1.28431e+00   -7.25274e-01
       1.28239e+00    1.00327e+00   -6.64799e-01
      -7.27066e-01   -6.64975e-01    5.39391e-01

     Epot (kJ/mol)        Coul-SR          LJ-SR        Coul-14          LJ-14   
           LIG-LIG   -2.14402e+05   -4.62212e+05   -4.54958e+06   -1.16995e+04
           LIG-COT    0.00000e+00    0.00000e+00    0.00000e+00    0.00000e+00
           LIG-TBA    0.00000e+00    0.00000e+00    0.00000e+00    0.00000e+00
           COT-COT    0.00000e+00    0.00000e+00    4.29776e+02    3.21521e+03
           COT-TBA    0.00000e+00    0.00000e+00    0.00000e+00    0.00000e+00
           TBA-TBA    0.00000e+00    0.00000e+00   -5.30264e+03   -2.07346e+01

             T-COT          T-TBA          T-LIG
       3.12294e+02    3.00056e+02    3.00005e+02


       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="averages">
           <module cmlx:templateRef="averages">
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Constr. rmsd</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">0.00000e+00</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Harmonic Pot.</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">8.27585e+04</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">U-B</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">4.39759e+05</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Proper Dih.</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">8.93986e+04</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">LJ-14</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-8.50504e+03</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Coulomb-14</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-4.55445e+06</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">LJ (SR)</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-4.62212e+05</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Disper. corr.</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-1.95856e+04</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Coulomb (SR)</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-2.14402e+05</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Coul. recip.</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">3.95741e+03</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Potential</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-4.64328e+06</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Kinetic En.</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">7.07850e+05</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Total Energy</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-3.93543e+06</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Temperature</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">3.00049e+02</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Pres. DC (bar)</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">-1.01381e+02</scalar>
               </property>
               <property>
                  <scalar dataType="xsd:string" dictRef="x:label">Pressure (bar)</scalar>
                  <scalar dataType="xsd:double" dictRef="x:value">1.00144e+00</scalar>
               </property>
               <vector3 dictRef="gm:box.coords">147.498 147.498 147.498</vector3>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern="\s*Energies\s*\(kJ/mol\).*" endPattern="\s*">    <record />    <record>{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}</record>    <record>{E,x:value}{E,x:value}{E,x:value}{E,x:value}{E,x:value}</record>    <record>{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}</record>    <record>{E,x:value}{E,x:value}{E,x:value}{E,x:value}{E,x:value}</record>    <record>{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}</record>    <record>{E,x:value}{E,x:value}{E,x:value}{E,x:value}{E,x:value}</record>    <record>{A15,x:label}</record>    <record>{E,x:value}</record>    <transform process="createWrapper" xpath=".//cml:scalar[@dictRef='x:label']" elementName="cml:property" />    <transform process="pullup" xpath=".//cml:property" repeat="2" />    <transform process="pullup" xpath=".//cml:property" />    <transform process="pullup" xpath=".//cml:scalar[@dictRef='x:value']" repeat="2" />    <transform process="pullup" xpath=".//cml:scalar[@dictRef='x:value']" />    <transform process="moveRelative" xpath="../cml:scalar[@dictRef='x:value']" to="../cml:property[not(exists(cml:scalar[@dictRef='x:value']))][position() =1]" />
           </template>  <template pattern="\s*Box-X.*" endPattern=".*" endOffset="1">    <record />    <record>{E,x:coord}{E,x:coord}{E,x:coord}</record>    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='x:coord']" args="operator=multiply operand=10" />    <transform process="createVector3" xpath="." dictRef="gm:box.coords" from=".//cml:scalar[@dictRef='x:coord']" />    <transform process="pullup" xpath=".//cml:vector3" repeat="3" />       
           </template>
       </templateList>
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
