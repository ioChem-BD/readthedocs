spin.free
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/molcas/eigenvalues-d3e36024
   /codes/molcas/strengths-d3e36100

=========

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
   | id                                                                                                                         | spin.free                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Spin free section                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;*&#92;s*Spin-free&#92;ssection.\*                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*[0-9]&#92;s*$&#92;s+&#92;-{20,}&#92;s\*                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/rassi/spin.free.xml                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         ****************************************************************************************************
         *                                                                                                  *
         *                                         Spin-free section                                        *
         *                                                                                                  *
         ****************************************************************************************************
    
    
    
     SPIN-FREE ENERGIES:
    
    SF State    Relative EVAC(au)   Rel lowest level(eV)      D:o, cm**(-1)
    
      1            -455.94051037            0.000000               0.000
      2            -455.70432382            6.426963           51836.956
      3            -455.65448560            7.783130           62775.181
      4            -455.65032750            7.896278           63687.778
      5            -455.62786207            8.507593           68618.372
    
   ++ Dipole transition strengths:
      ----------------------------
       for osc. strength at least   0.10000000E-07
    
            To  From     Osc. strength   Einstein coefficients Ax, Ay, Az (sec-1)  
         Total A (sec-1)  
            -----------------------------------------------------------------------
    --------------------
            1    2       0.44908649       325.42995      0.80491315E+09   904.63533      0.80491438E+09
            1    3       0.84575810       35416547.       371.67035      0.21877027E+10  0.22231196E+10
            1    4       0.25628259E-07  0.88069050      0.84981547       67.607607       69.338113    
            2    3       0.18378757E-02  0.11066907E-06   146669.54       3.5999583       146673.14    
            2    4       0.74450773E-05   691.28023      0.36464401E-01   6.1233748       697.44007    
            2    5       0.14629998E-05   272.48692      0.57067986E-02   2.3234797       274.81610    
            4    5       0.18162739E-01   4637.2607      0.21982961E-01   289886.55       294523.84    
            -----------------------------------------------------------------------
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="spin.free">
            <module cmlx:templateRef="spin.free">
               <module cmlx:templateRef="eigenvalues">
                  <array dataType="xsd:integer" dictRef="m:sfstate" size="5">1 2 3 4 5</array>
                  <array dataType="xsd:double" dictRef="m:relevac" size="5">-455.94051037 -455.70432382 -455.65448560 -455.65032750 -455.62786207</array>
                  <array dataType="xsd:double" dictRef="m:rellowlevel" size="5">0.000000 6.426963 7.783130 7.896278 8.507593</array>
                  <array dataType="xsd:double" dictRef="m:d.o" size="5">0.000 51836.956 62775.181 63687.778 68618.372</array>
               </module>
               <module cmlx:templateRef="strengths">
                  <array dataType="xsd:integer" dictRef="m:to" size="7">1 1 1 2 2 2 4</array>
                  <array dataType="xsd:integer" dictRef="m:from" size="7">2 3 4 3 4 5 5</array>
                  <array dataType="xsd:double" dictRef="m:oscstrength" size="7">0.44908649 0.84575810 0.25628259E-07 0.18378757E-02 0.74450773E-05 0.14629998E-05 0.18162739E-01</array>
                  <array dataType="xsd:double" dictRef="m:einsteincoeff" size="21">325.42995 0.80491315E+09 904.63533 35416547. 371.67035 0.21877027E+10 0.88069050 0.84981547 67.607607 0.11066907E-06 146669.54 3.5999583 691.28023 0.36464401E-01 6.1233748 272.48692 0.57067986E-02 2.3234797 4637.2607 0.21982961E-01 289886.55</array>
                  <array dataType="xsd:double" dictRef="m:totala" size="7">0.80491438E+09 0.22231196E+10 69.338113 146673.14 697.44007 274.81610 294523.84</array>
               </module>
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <xi:include href="modules/rassi/eigenvalues.xml" />  <xi:include href="modules/rassi/dipole.transition.xml" />                        
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
