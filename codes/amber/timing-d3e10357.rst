.. _timing-d3e10357:

timing
======

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
   | *source*                                                                                                                   | Amber log                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | timing                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Timings                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{20,}.*$&#92;s*5&#92;.&#92;s+TIMINGS.\*                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*-{20,}.                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/timings.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   --------------------------------------------------------------------------------
      5.  TIMINGS
   --------------------------------------------------------------------------------

   |  NonSetup CPU Time in Major Routines:
   |
   |     Routine           Sec        %
   |     ------------------------------
   |     Nonbond        6798.19   53.24
   |     Bond              0.00    0.00
   |     Angle             0.00    0.00
   |     Dihedral          0.00    0.00
   |     Shake           431.76    3.38
   |     RunMD          5257.13   41.17
   |     Other           282.06    2.21
   |     ------------------------------
   |     Total         12769.14

   |  PME Nonbond Pairlist CPU Time:
   |
   |     Routine              Sec        %
   |     ---------------------------------
   |     Set Up Cit           0.00    0.00
   |     Build List           0.00    0.00
   |     ---------------------------------
   |     Total                0.00    0.00

   |  PME Direct Force CPU Time:
   |
   |     Routine              Sec        %
   |     ---------------------------------
   |     NonBonded Calc       0.00    0.00
   |     Exclude Masked       0.00    0.00
   |     Other               59.60    0.47
   |     ---------------------------------
   |     Total               59.60    0.47

   |  PME Reciprocal Force CPU Time:
   |
   |     Routine              Sec        %
   |     ---------------------------------
   |     1D bspline           0.00    0.00
   |     Grid Charges         0.00    0.00
   |     Scalar Sum           0.00    0.00
   |     Gradient Sum         0.00    0.00
   |     FFT                  0.00    0.00
   |     ---------------------------------
   |     Total                0.00    0.00

   |  Final Performance Info:
   |     -----------------------------------------------------
   |     Average timings for last  100000 steps:
   |     Elapsed(s) =      25.50 Per Step(ms) =       0.25
   |         ns/day =     677.69   seconds/ns =     127.49
   |
   |     Average timings for all steps:
   |     Elapsed(s) =   12766.97 Per Step(ms) =       0.26
   |         ns/day =     676.75   seconds/ns =     127.67
   |     -----------------------------------------------------

   |  Setup CPU time:            0.36 seconds
   |  NonSetup CPU time:     12769.14 seconds
   |  Total CPU time:        12769.50 seconds     3.55 hours

   |  Setup wall time:           0    seconds
   |  NonSetup wall time:    12767    seconds
   |  Total wall time:       12767    seconds     3.55 hours
       

.. container:: formalpara-title

   **Input**

::

   --------------------------------------------------------------------------------
   5.  TIMINGS
   --------------------------------------------------------------------------------

   |                Build the list            27.49 (99.73% of List )
   |                Other                      0.08 ( 0.27% of List )
   |             List time                 27.57 (13.07% of Nonbo)
   |                   Short_ene time           156.46 (99.34% of Direc)
   |                   Other                      1.03 ( 0.66% of Direc)
   |                Direct Ewald time        157.49 (85.86% of Ewald)
   |                Adjust Ewald time          0.70 ( 0.38% of Ewald)
   |                Self Ewald time            0.01 ( 0.01% of Ewald)
   |                   Fill Bspline coeffs        0.95 ( 3.79% of Recip)
   |                   Fill charge grid           2.35 ( 9.36% of Recip)
   |                   Scalar sum                 9.44 (37.67% of Recip)
   |                   Grad sum                   4.60 (18.35% of Recip)
   |                   FFT time                   7.72 (30.78% of Recip)
   |                   Other                      0.01 ( 0.06% of Recip)
   |                Recip Ewald time          25.07 (13.67% of Ewald)
   |                Force Adjust               0.02 ( 0.01% of Ewald)
   |                Virial junk                0.07 ( 0.04% of Ewald)
   |                Other                      0.05 ( 0.03% of Ewald)
   |             Ewald time               183.42 (86.92% of Nonbo)
   |             Other                      0.02 ( 0.01% of Nonbo)
   |          Nonbond force            211.01 (99.89% of Force)
   |          Bond/Angle/Dihedral        0.20 ( 0.10% of Force)
   |          Other                      0.03 ( 0.02% of Force)
   |       Force time               211.25 (99.39% of Runmd)
   |       Shake time                 0.81 ( 0.38% of Runmd)
   |       Verlet update time         0.43 ( 0.20% of Runmd)
   |       Other                      0.06 ( 0.03% of Runmd)
   |    Runmd Time               212.55 (100.0% of Total)
   |    Other                      0.07 ( 0.03% of Total)
   | Total time               212.63 (100.0% of ALL  )

   | Number of list builds   :        253

   | Highest rstack allocated:     453370
   | Highest istack allocated:       7628

   | Final Performance Info:
   | -----------------------------------------------------
   | Average timings for all steps:
   |     Elapsed(s) =     212.55 Per Step(ms) =      85.02
   |         ns/day =       2.03   seconds/ns =   42510.43
   | -----------------------------------------------------

   |           Job began  at 11:14:57.831  on 11/16/2021
   |           Setup done at 11:14:57.912  on 11/16/2021
   |           Run   done at 11:18:30.463  on 11/16/2021
   |     wallclock() was called  110524 times

   |3D-RISM memory allocation summary
   |Type          Maximum        Current   
   |Integer       0.00000 GB     0.00000 GB
   |Real          0.00000 GB     0.00000 GB
   |Logical       0.00000 GB     0.00000 GB
   |Character     0.00000 GB     0.00000 GB
   |---------------------------------------
   |Total         0.00000 GB     0.00000 GB
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="timing">
           <module cmlx:templateRef="timing">
            <module cmlx:templateRef="walltime">
               <scalar dataType="xsd:double" dictRef="cc:elapsedtime" units="si:s">12766.97</scalar>
               <scalar dataType="xsd:double" dictRef="am:elapsedstep" units="nonsi:milliseconds">0.26</scalar>
               <scalar dataType="xsd:double" dictRef="am:nsperday">676.75</scalar>
               <scalar dataType="xsd:double" dictRef="am:secondsperns">127.67</scalar>
               <scalar dataType="xsd:integer" dictRef="cc:wallTime" units="si:s">12767</scalar>
               <scalar dataType="xsd:double" dictRef="cc:cpuTime" units="si:s">12769.50</scalar>
            </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="timing2">
           <module cmlx:templateRef="timing">
               <module cmlx:templateRef="walltime">
                   <scalar dataType="xsd:double" dictRef="cc:elapsedtime" units="si:s">212.55</scalar>
                   <scalar dataType="xsd:double" dictRef="am:elapsedstep" units="nonsi:milliseconds">85.02</scalar>
                   <scalar dataType="xsd:double" dictRef="am:nsperday">2.03</scalar>
                   <scalar dataType="xsd:double" dictRef="am:secondsperns">42510.43</scalar>
                   <scalar dataType="xsd:date" dictRef="cc:runDate">2021-11-16T11:14:57.831</scalar>
                   <scalar dataType="xsd:date" dictRef="cc:dateEnd">2021-11-16T11:18:30.463</scalar>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="walltime" pattern="\s*\|\s+Final\sPerformance\sInfo:.*" endPattern="\s*" endPattern2=".*[0-9]$\s*\|\s+-{20,}]">    <templateList>      <template pattern="\s*\|\s+Average\stimings\sfor\sall\ssteps.*" endPattern="\s*\|\s*" endPattern2="~">        <record />        <record>\s*\|\s+Elapsed\(s\)\s*={F,cc:elapsedtime}Per\sStep\(ms\)\s*={F,am:elapsedstep}</record>        <record>\s*\|\s+ns\/day\s*={F,am:nsperday}seconds/ns\s*={F,am:secondsperns}</record>        <transform process="pullup" xpath=".//cml:scalar" />
                   </template>
               </templateList>
           </template>  <template id="cputime" pattern="\s*\|\s+.*Setup\sCPU\stime:.*" endPattern=".*Total\sCPU\stime.*" endOffset="1">    <record repeat="2" />    <record>\s*\|\s+.*Total\sCPU\stime:{F,cc:cpuTime}seconds.*</record>
           </template>  <template id="walltime2" pattern="\s*\|\s+.*Setup\swall\stime:.*" endPattern="\s+" endPattern2="~" endOffset="1">    <record repeat="2" />    <record>\s*\|\s+.*Total\swall\stime:{I,cc:wallTime}seconds.*</record>
           </template>  <template id="jobDates" pattern="\s*\|\s*Job\s*began\s*at.*" endPattern="\s*\|\s*Run\s*done\s*at.*" endOffset="1">    <record>\s*\|\s*Job\s*began\s*at{X,cc:runDate}</record>    <record />    <record>\s*\|\s*Run\s*done\s*at{X,cc:dateEnd}</record>    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:runDate']" format="HH:mm:ss.SSS  'on' MM/dd/yyyy" />    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:dateEnd']" format="HH:mm:ss.SSS  'on' MM/dd/yyyy" />
           </template>
       </templateList>
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:elapsedtime']" value="si:s" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='am:elapsedstep']" value="nonsi:milliseconds" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:wallTime']" value="si:s" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:cpuTime']" value="si:s" />
   <transform process="pullup" xpath=".//cml:module[@cmlx:templateRef='walltime']//cml:scalar" repeat="2" />
   <transform process="moveRelative" xpath=".//cml:module[@cmlx:templateRef='walltime2']//cml:scalar" to="ancestor::cml:module[@cmlx:templateRef='timing']//cml:module[@cmlx:templateRef='walltime']" />
   <transform process="moveRelative" xpath=".//cml:module[@cmlx:templateRef='cputime']//cml:scalar" to="ancestor::cml:module[@cmlx:templateRef='timing']//cml:module[@cmlx:templateRef='walltime']" />
   <transform process="moveRelative" xpath=".//cml:module[@cmlx:templateRef='jobDates']//cml:scalar" to="ancestor::cml:module[@cmlx:templateRef='timing']//cml:module[@cmlx:templateRef='walltime']" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='walltime2']" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='cputime']" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='jobDates']" />
   <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
