.. _steep-d3e27527:

steep
=====

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
   | id                                                                                                                         | steep                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Steepest Descents                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Initiating&#92;sSteepest&#92;sDescents.\*                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Finished&#92;smdrun&#92;son&#92;srank.\*                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/steep.xml                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   Initiating Steepest Descents
   Started Steepest Descents on rank 0 Thu Mar 24 08:07:52 2022


   Steepest Descents:
      Tolerance (Fmax)   =  1.00000e+03
      Number of steps    =        50000
              Step           Time
                 0        0.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       3.49730e+05   -8.70966e+05    1.28223e+04   -5.08413e+05    2.95889e+04

              Step           Time
                 1        1.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       2.97313e+05   -8.71936e+05    1.27724e+04   -5.61851e+05    2.20612e+04

              Step           Time
                 2        2.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       2.48541e+05   -8.73970e+05    1.26300e+04   -6.12799e+05    1.51424e+04

              Step           Time
                 3        3.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       2.11290e+05   -8.77578e+05    1.23070e+04   -6.53981e+05    9.59498e+03

              Step           Time
                 4        4.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.86020e+05   -8.83698e+05    1.16364e+04   -6.86042e+05    5.63078e+03

              Step           Time
                 5        5.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.64635e+05   -8.95427e+05    1.01248e+04   -7.20668e+05    1.99876e+03

              Step           Time
                 6        6.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.54818e+05   -9.06953e+05    8.62540e+03   -7.43510e+05    5.09000e+01

              Step           Time
                 7        7.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.51869e+05   -9.10532e+05    8.23930e+03   -7.50424e+05   -5.42049e+02

              Step           Time
                 8        8.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.43465e+05   -9.25094e+05    6.61912e+03   -7.75010e+05   -2.40643e+03

              Step           Time
                 9        9.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.41340e+05   -9.28615e+05    6.39286e+03   -7.80882e+05   -2.87211e+03


   step 10: One or more water molecules can not be settled.
   Check for bad contacts and/or reduce the timestep if appropriate.
   Wrote pdb files with previous and current coordinates
              Step           Time
                10       10.00000

              Step           Time
                11       11.00000

      Energies (kJ/mol)
           LJ (SR)   Coulomb (SR)   Coul. recip.      Potential Pressure (bar)
       1.38180e+05   -9.35808e+05    5.83706e+03   -7.91790e+05   -3.64690e+03


   Steepest Descents converged to Fmax < 1000 in 12 steps
   Potential Energy  = -7.9178994e+05
   Maximum force     =  7.6484247e+02 on atom 91
   Norm of force     =  1.2360245e+02
   Finished mdrun on rank 0 Thu Mar 24 08:07:53 2022   
       

.. warning::

   Current template has input comments defined but it's output is missing, please notify software developers.

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="1" />
   <record>\s*Started\sSteepest\sDescents\son\srank\s+\S+\s+{X,cc:runDate}</record>
   <templateList>  <template id="energies" pattern="\s*Energies\s+\(kJ\/mol\).*" endPattern=".*[0-9]\s*$\s*" endOffset="1" repeat="*">    <record repeat="1" />    <record>{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}{A15,x:label}</record>    <record>{E,x:value}{E,x:value}{E,x:value}{E,x:value}{E,x:value}</record>                            
           </template>  <template id="endDate" pattern="\s*Finished\smdrun\son.*" endPattern=".*" endPattern2="~">    <record>\s*Finished\smdrun\son\srank\s+\S+\s+{X,cc:jobdatetime.end}</record>
           </template>   
       </templateList>
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='energies'][position() != last()]" />
   <transform process="createWrapper" xpath=".//cml:scalar[@dictRef='x:label']" elementName="cml:property" />
   <transform process="pullup" xpath=".//cml:property" repeat="2" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='x:value']" repeat="2" />
   <transform process="moveRelative" xpath="./cml:module[@cmlx:templateRef='energies']/cml:scalar[@dictRef='x:value']" to="./preceding-sibling::cml:property[not(exists(cml:scalar[@dictRef='x:value']))][position() =1]" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:runDate']" format="E MMM  d HH:mm:ss yyyy" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:runDate']" format="E MMM dd HH:mm:ss yyyy" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:jobdatetime.end']" format="E MMM  d HH:mm:ss yyyy" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:jobdatetime.end']" format="E MMM dd HH:mm:ss yyyy" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:runDate']" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:jobdatetime.end']" repeat="2" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
