.. _energy.statistics-d3e36081:

energy.statistics
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
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | energy.statistics                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;*+&#92;s*Energy&#92;sStatistics&#92;sfor&#92;sGeometry&#92;sOptimization.\*                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*&#92;*{20,}                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/energystats/energy.statistics.xml                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   *****************************************************************************************************************
   ********************************** Energy Statistics for Geometry Optimization **********************************
   *****************************************************************************************************************

                          Energy     Grad     Grad              Step                 Estimated   Geom     Hessian
   Iter      Energy       Change     Norm     Max    Element    Max     Element     Final Energy Update Update Index
     1  -2909.02654568  0.00000000 0.114368 0.032218 nrc030   0.047436  nrc035    -2909.02994010 RS-RFO  None    0
     2  -2909.03241288 -0.00586720 0.102599-0.030984 nrc032  -0.213224* nrc032    -2909.04444600 RS-RFO  BFGS    0
     3  -2909.04853599 -0.01612311 0.098039 0.022512 nrc019  -0.173013* nrc036    -2909.05388587 RS-RFO  BFGS    0
     4  -2909.05580715 -0.00727116 0.107761 0.026819 nrc015  -0.171971  nrc006    -2909.06086106 RS-RFO  BFGS    0
     5  -2909.06328732 -0.00748018 0.105763-0.028623 nrc023  -0.140847* nrc023    -2909.06806444 RS-RFO  BFGS    0
     6  -2909.07033489 -0.00704757 0.079606 0.015120 nrc009  -0.117132* nrc021    -2909.07398780 RS-RFO  BFGS    0
     7  -2909.07352324 -0.00318835 0.056494-0.011387 nrc042   0.134143  nrc023    -2909.07508132 RS-RFO  BFGS    0
     8  -2909.07508799 -0.00156475 0.038931-0.013177 nrc032   0.043938  nrc042    -2909.07565675 RS-RFO  BFGS    0
     9  -2909.07567159 -0.00058360 0.033592 0.012378 nrc027   0.046281  nrc027    -2909.07624696 RS-RFO  BFGS    0
    10  -2909.07582688 -0.00015529 0.033085 0.011307 nrc036   0.070748  nrc021    -2909.07624902 RS-RFO  BFGS    0
    11  -2909.07599893 -0.00017205 0.031602-0.012602 nrc041  -0.053689  nrc041    -2909.07656286 RS-RFO  BFGS    0
    12  -2909.07601471 -0.00001578 0.033254 0.011180 nrc028  -0.035948  nrc002    -2909.07633701 RS-RFO  BFGS    0
    13  -2909.07601260  0.00000211 0.031626 0.012318 nrc030   0.066310  nrc030    -2909.07671501 RS-RFO  BFGS    0
    14  -2909.07596245  0.00005015 0.031928 0.010589 nrc032   0.036247  nrc008    -2909.07629423 RS-RFO  BFGS    0


            Cartesian Displacements            Gradient in internals
          Value      Threshold  Converged?   Value      Threshold  Converged?
       +----------------------------------+----------------------------------+
   RMS + 0.1726E-01  0.1200E-02     No    + 0.4869E-02  0.3000E-03     No    +
       +----------------------------------+----------------------------------+
   Max + 0.3755E-01  0.1800E-02     No    + 0.1059E-01  0.4500E-03     No    +
       +----------------------------------+----------------------------------+

    Convergence not reached yet!

   *****************************************************************************************************************   
       

.. container:: formalpara-title

   **Input**

::

   *****************************************************************************************************************
   *                                  Energy Statistics for Geometry Optimization                                  *
   *****************************************************************************************************************
                          Energy     Grad     Grad              Step                 Estimated   Geom     Hessian
   Iter      Energy       Change     Norm     Max    Element    Max     Element     Final Energy Update Update Index
     1   -229.08547493  0.00000000 0.066529-0.030891 nrc006  -0.039045  nrc013     -229.08742903 RS-RFO  None    0
     2   -229.08816099 -0.00268606 0.023901-0.013158 nrc006  -0.026308  nrc006     -229.08861242 RS-RFO  BFGS    0
     3   -229.08865857 -0.00049757 0.010814 0.004299 nrc001   0.008277  nrc002     -229.08869519 RS-RFO  BFGS    0

          +----------------------------------+----------------------------------+
          +    Cartesian Displacements       +    Gradient in internals         +
          +  Value      Threshold Converged? +  Value      Threshold Converged? +
    +-----+----------------------------------+----------------------------------+
    + RMS + 0.5933E-02  0.1200E-02     No    + 0.2792E-02  0.3000E-03     No    +
    +-----+----------------------------------+----------------------------------+
    + Max + 0.1076E-01  0.1800E-02     No    + 0.4299E-02  0.4500E-03     No    +
    +-----+----------------------------------+----------------------------------+

    Convergence not reached yet!

   *****************************************************************************************************************   
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="energy.statistics">
           <module cmlx:templateRef="energystatistics">     
               <list cmlx:templateRef="RMS">
                  <scalar dataType="xsd:double" dictRef="m:cartesianval">0.1726E-01</scalar>
                  <scalar dataType="xsd:double" dictRef="m:cartesiandisp">0.1200E-02</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
                  <scalar dataType="xsd:double" dictRef="m:gradval">0.4869E-02</scalar>
                  <scalar dataType="xsd:double" dictRef="m:graddisp">0.3000E-03</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
               </list>
               <list cmlx:templateRef="Max">
                  <scalar dataType="xsd:double" dictRef="m:cartesianval">0.3755E-01</scalar>
                  <scalar dataType="xsd:double" dictRef="m:cartesiandisp">0.1800E-02</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
                  <scalar dataType="xsd:double" dictRef="m:gradval">0.1059E-01</scalar>
                  <scalar dataType="xsd:double" dictRef="m:graddisp">0.4500E-03</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
               </list>
            </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="energy.statistics2">
            <module cmlx:templateRef="energy.statistics">
               <list cmlx:templateRef="RMS">
                  <scalar dataType="xsd:double" dictRef="m:cartesianval">0.5933E-02</scalar>
                  <scalar dataType="xsd:double" dictRef="m:cartesiandisp">0.1200E-02</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
                  <scalar dataType="xsd:double" dictRef="m:gradval">0.2792E-02</scalar>
                  <scalar dataType="xsd:double" dictRef="m:graddisp">0.3000E-03</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
               </list>
               <list cmlx:templateRef="Max">
                  <scalar dataType="xsd:double" dictRef="m:cartesianval">0.1076E-01</scalar>
                  <scalar dataType="xsd:double" dictRef="m:cartesiandisp">0.1800E-02</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
                  <scalar dataType="xsd:double" dictRef="m:gradval">0.4299E-02</scalar>
                  <scalar dataType="xsd:double" dictRef="m:graddisp">0.4500E-03</scalar>
                  <scalar dataType="xsd:string" dictRef="m:converged">No</scalar>
               </list>
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern=".*\s*Cartesian\sDisplacements\s*\+?\s*Gradient\sin\sinternals.*" endPattern="\s*">    <record repeat="3" />    <record id="RMS">\s*\+?\s*RMS\s\+{E,m:cartesianval}{E,m:cartesiandisp}{A,m:converged}\+{E,m:gradval}{E,m:graddisp}{A,m:converged}\+</record>    <record />    <record id="Max">\s*\+?\s*Max\s\+{E,m:cartesianval}{E,m:cartesiandisp}{A,m:converged}\+{E,m:gradval}{E,m:graddisp}{A,m:converged}\+</record>    <transform process="pullup" xpath=".//cml:list/cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*) = 0]" />    <transform process="delete" xpath=".//cml:list[count(*) = 0]" />    <transform process="pullup" xpath=".//cml:list" />                     
           </template>       
       </templateList>
   <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
