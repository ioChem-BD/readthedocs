.. _eigenvalues-d3e36024:

eigenvalues
===========

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
   | id                                                                                                                         | eigenvalues                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*SPIN-FREE&#92;sENERGIES.\*                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*Eigenvalues&#92;sof&#92;scomplex&#92;sHamiltonian:.\*                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*[0-9]&#92;s*$&#92;s\*                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/rassi/eigenvalues.xml                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

     SPIN-FREE ENERGIES:
    
    SF State    Relative EVAC(au)   Rel lowest level(eV)      D:o, cm**(-1)
    
      1            -455.94051037            0.000000               0.000
      2            -455.70432382            6.426963           51836.956
      3            -455.65448560            7.783130           62775.181
      4            -455.65032750            7.896278           63687.778
      5            -455.62786207            8.507593           68618.372
    
       

.. container:: formalpara-title

   **Input**

::

      Eigenvalues of complex Hamiltonian:
      -----------------------------------
    
     (Shifted by EVAC (a.u.) =           -2000.0)
    
           Relative EVac(au)    Rel lowest level(eV)    D:o, cm**(-1)
    
      1     -186.96342751            0.000000               0.000
      2     -186.96342660            0.000025               0.200
      3     -186.96341137            0.000439               3.542
      4     -186.96340281            0.000672               5.422
      5     -186.96339968            0.000757               6.109
      6     -186.93813940            0.688125            5550.100
      7     -186.93813525            0.688237            5551.010
      8     -186.93812394            0.688545            5553.494
      9     -186.93810374            0.689095            5557.926
     10     -186.93810253            0.689128            5558.191
     11     -186.89132097            1.962119           15825.556
     12     -186.89131080            1.962396           15827.788
     13     -186.89126100            1.963751           15838.720
     14     -186.89119986            1.965414           15852.137
     15     -186.89119294            1.965603           15853.656
     16     -186.88724052            2.073154           16721.113
     17     -186.88723752            2.073235           16721.771
     18     -186.88707577            2.077637           16757.270
     19     -186.88702485            2.079022           16768.447
     20     -186.88698451            2.080120           16777.301
     21     -186.88282070            2.193423           17691.151
     22     -186.88281132            2.193678           17693.209
     23     -186.88274916            2.195370           17706.853
     24     -186.88269200            2.196925           17719.398
     25     -186.88268252            2.197183           17721.478

       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="eigenvalues">
           <module cmlx:templateRef="eigenvalues">         
               <array dataType="xsd:integer" dictRef="m:sfstate" size="5">1 2 3 4 5</array>
               <array dataType="xsd:double" dictRef="m:relevac" size="5">-455.94051037 -455.70432382 -455.65448560 -455.65032750 -455.62786207</array>
               <array dataType="xsd:double" dictRef="m:rellowlevel" size="5">0.000000 6.426963 7.783130 7.896278 8.507593</array>
               <array dataType="xsd:double" dictRef="m:d.o" size="5">0.000 51836.956 62775.181 63687.778 68618.372</array>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="eigenvalues2">
           <module cmlx:templateRef="eigenvalues">
              <scalar dataType="xsd:double" dictRef="m:evacshift">-2000.0</scalar>
              <array dataType="xsd:integer" dictRef="m:sfstate" size="31">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31</array>
              <array dataType="xsd:double" dictRef="m:relevac" size="31">-186.96338677 -186.93808439 -186.89117601 -186.88711044 -186.88289785 -186.90405956 -186.90096490 -186.89791585 -186.86063176 -186.85200887 -186.84911258 -186.84846304 -186.84702920 -186.83557419 -186.83397597 -186.83350978 -186.83283523 -186.82594686 -186.85166551 -186.84870294 -186.84714373 -186.84489728 -186.84016441 -186.81464059 -186.80625787 -186.80244784 -186.80075824 -186.79275676 -186.78860419 -186.78514470 -186.78422395</array>
              <array dataType="xsd:double" dictRef="m:rellowlevel" size="31">0.000000 0.688513 1.964955 2.075585 2.190215 1.614376 1.698585 1.781554 2.796106 3.030747 3.109559 3.127234 3.166251 3.477957 3.521447 3.534133 3.552488 3.739930 3.040090 3.120706 3.163134 3.224263 3.353051 4.047589 4.275695 4.379371 4.425347 4.643079 4.756076 4.850214 4.875268</array>
              <array dataType="xsd:double" dictRef="m:d.o" size="31">0.000 5553.230 15848.430 16740.720 17665.275 13020.818 13700.016 14369.206 22552.118 24444.624 25080.285 25222.843 25537.536 28051.619 28402.388 28504.705 28652.750 30164.574 24519.982 25170.190 25512.399 26005.438 27044.182 32646.012 34485.808 35322.011 35692.837 37448.959 38360.342 39119.613 39321.695</array>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*\(Shifted\sby\sEVAC\s\(a\.u\.\).*" endPattern=".*">    <record>\s*\(Shifted\sby\sEVAC\s\(a\.u\.\)\s*={F,m:evacshift}\)\s*</record>        
           </template>  <template pattern="\s*1.*" endPattern="~">    <record makeArray="true" repeat="*">{I,m:sfstate}{F,m:relevac}{F,m:rellowlevel}{F,m:d.o}</record>                    
           </template>
       </templateList>
   <template pattern="\s*1.*" endPattern="~">  <record makeArray="true" repeat="*">{I,m:sfstate}{F,m:relevac}{F,m:rellowlevel}{F,m:d.o}</record>                 
       </template>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
