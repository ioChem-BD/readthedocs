sfo.population
-------------------------------------- 

.. toctree::
   :maxdepth: 5    
      
   /codes/adf/molecular.orbitals-d3e3908

==============

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
   | id                                                                                                                         | sfo.population                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | SFO populations, MO analysis                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*S&#92;sF&#92;sO&#92;s+P&#92;sO&#92;sP&#92;sU&#                                                                      |
   |                                                                                                                            | 92;sL&#92;sA&#92;sT&#92;sI&#92;sO&#92;sN&#92;sS.*M&#92;sO&#92;s+A&#92;sN&#92;sA&#92;sL&#92;sY&#92;sS&#92;sI&#92;sS&#92;s\* |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*={10,}+.*$[&#92;s&#92;S]+$&#92;s*={10,}+.\*                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | results/sfopopulation/sfo.population.xml                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Comment**

::

    =======================================================
    S F O   P O P U L A T I O N S ,   M O   A N A L Y S I S
    =======================================================
   ...

    List of all MOs, ordered by energy, with the most significant SFO gross populations
    ===================================================================================

    Each percentage contribution in the table below corresponds to the indicated SFO.
    In general, a SFO may be a linear combination of several Fragment Orbitals on the same,
    or on symmetry-related Fragments. Only the first 'member' of such a combination is
    specified here. A full definition of all SFOs is given in an earlier part of the output.
    The numbering of the SFOs in this table does NOT include the Core Orbitals, and starts
    from one for each symmetry representation, as in the SFO definition list earlier.

          E(eV)  Occ       MO           %     SFO (first member)   E(eV)  Occ   Fragment
    -------------------------------------------------------------------------------------

        -14.381  2.00    11 A1.g      38.37%     1 S             -24.134  2.00    13 O
                                      28.43%     1 S             -24.134  2.00    21 O
                                      14.01%     1 S             -24.134  2.00    25 O
   ...
       
       

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <xi:include href="sfopopulation/molecular.orbitals.xml" />
       </templateList>

.. _molecular.orbitals-d3e3908:

molecular.orbitals
------------------

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image3|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image4|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | molecular.orbitals                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | List of all MOs, ordered by energy                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*List&#92;sof&#92;sall&#92;sMOs,&#92;sordered&#92;sby&#92;senergy.\*                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*$&#92;s\*                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | sfopopulation/molecular.orbitals.xml                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    List of all MOs, ordered by energy, with the most significant SFO gross populations
    ===================================================================================

    Each percentage contribution in the table below corresponds to the indicated SFO.
    In general, a SFO may be a linear combination of several Fragment Orbitals on the same,
    or on symmetry-related Fragments. Only the first 'member' of such a combination is
    specified here. A full definition of all SFOs is given in an earlier part of the output.
    The numbering of the SFOs in this table does NOT include the Core Orbitals, and starts
    from one for each symmetry representation, as in the SFO definition list earlier.

          E(eV)  Occ       MO           %     SFO (first member)   E(eV)  Occ   Fragment
    -------------------------------------------------------------------------------------

        -14.381  2.00    11 A1.g      38.37%     1 S             -24.134  2.00    13 O
                                      28.43%     1 S             -24.134  2.00    21 O
                                      14.01%     1 S             -24.134  2.00    25 O
                                       6.86%     1 S             -24.134  2.00    11 O
                                       3.39%     1 S             -24.134  2.00    33 O
                                       3.36%     2 S              -5.836  2.00     1 W
                                      -1.08%     3 S               1.298  0.00     1 W
                                       1.06%     1 P:x            -9.197  1.33    13 O
        -14.212  2.00    11 A2.u      52.14%     1 S             -24.134  2.00    13 O
                                      26.30%     1 S             -24.134  2.00    21 O
                                       7.86%     1 S             -24.134  2.00    11 O
                                       3.90%     1 S             -24.134  2.00    33 O
                                       1.86%     2 S              -5.836  2.00     1 W
                                       1.19%     1 P:x            -9.197  1.33    13 O
                                       1.12%     1 S             -24.134  2.00    37 O
                                       1.05%     1 D:z2           -4.634  0.80     1 W
                                       1.04%     2 S              -5.836  2.00     9 W
        -13.745  2.00    15 E1.u:1    36.80%     1 S             -24.134  2.00    31 O
                                      33.87%     1 S             -24.134  2.00    13 O
                                      19.25%     1 S             -24.134  2.00    27 O
                                       3.24%     1 S             -24.134  2.00    33 O
                                       1.98%     2 S              -5.836  2.00     1 W
                                       1.46%     1 D:z2           -4.634  0.80     1 W
        -13.745  2.00    15 E1.u:2    36.80%     1 S             -24.134  2.00    25 O
                                      33.87%     1 S             -24.134  2.00    13 O
                                      19.25%     1 S             -24.134  2.00    21 O
                                       3.24%     1 S             -24.134  2.00    39 O
                                       1.98%     2 S              -5.836  2.00     5 W
                                       1.46%     1 D:z2           -4.634  0.80     5 W
       
       

.. container:: formalpara-title

   **Input**

::

    List of all MOs, ordered by energy, with the most significant SFO gross populations
    ===================================================================================

    Each percentage contribution in the table below corresponds to the indicated SFO.
    In general, a SFO may be a linear combination of several Fragment Orbitals on the same,
    or on symmetry-related Fragments. Only the first 'member' of such a combination is
    specified here. A full definition of all SFOs is given in an earlier part of the output.
    The numbering of the SFOs in this table does NOT include the Core Orbitals, and starts
    from one for each symmetry representation, as in the SFO definition list earlier.


                                          *** SPIN 1 ***


          E(eV)  Occ       MO           %     SFO (first member)   E(eV)  Occ   Fragment
    -------------------------------------------------------------------------------------

         -8.225  1.00    20 A1        32.51%     1 S             -24.134  2.00    17 O
                                      17.93%     1 S             -24.134  2.00    23 O
                                      13.22%     1 S             -24.134  2.00    13 O
                                      10.33%     1 S             -24.134  2.00    25 O
                                       6.46%     1 S             -24.134  2.00    12 O
                                       4.22%     1 S             -24.134  2.00    21 O
                                       3.39%     1 S             -24.134  2.00    35 O
                                       2.62%     2 S              -5.836  2.00     3 W
                                       1.59%     1 S             -24.134  2.00    11 O
                                       1.24%     1 S             -24.134  2.00    33 O
         -8.067  1.00    21 A1        48.78%     1 S             -24.134  2.00    13 O
                                      15.26%     1 S             -24.134  2.00    17 O
                                       8.55%     1 S             -24.134  2.00    21 O
                                       5.21%     1 S             -24.134  2.00    23 O
                                       4.55%     1 S             -24.134  2.00    11 O
                                       3.93%     1 S             -24.134  2.00    33 O
                                       2.55%     1 S             -24.134  2.00    12 O
                                       1.36%     1 S             -24.134  2.00    35 O
                                       1.20%     1 D:z2           -4.634  0.80     1 W
               

                                          *** SPIN 2 ***


          E(eV)  Occ       MO           %     SFO (first member)   E(eV)  Occ   Fragment
    -------------------------------------------------------------------------------------

         -8.215  1.00    20 A1        34.44%     1 S             -24.134  2.00    17 O
                                      16.27%     1 S             -24.134  2.00    23 O
                                      13.49%     1 S             -24.134  2.00    13 O
                                      10.22%     1 S             -24.134  2.00    25 O
                                       6.54%     1 S             -24.134  2.00    12 O
                                       3.66%     1 S             -24.134  2.00    21 O
                                       3.54%     1 S             -24.134  2.00    35 O
                                       2.46%     2 S              -5.836  2.00     3 W
                                       1.58%     1 S             -24.134  2.00    11 O
                                       1.25%     1 S             -24.134  2.00    33 O
         -8.060  1.00    21 A1        50.37%     1 S             -24.134  2.00    13 O
                                      15.77%     1 S             -24.134  2.00    17 O
                                       7.28%     1 S             -24.134  2.00    21 O
                                       4.53%     1 S             -24.134  2.00    11 O
                                       4.43%     1 S             -24.134  2.00    23 O
                                       4.02%     1 S             -24.134  2.00    33 O
                                       2.49%     1 S             -24.134  2.00    12 O
                                       1.37%     1 S             -24.134  2.00    35 O
                                       1.34%     1 D:z2           -4.634  0.80     1 W



       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="molecular.orbitals">
           <module cmlx:lineCount="1683" cmlx:templateRef="molecular.orbitals">    
             <list cmlx:templateRef="mo">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-14.381</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">2.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">11</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">A1.g</scalar>
              <array dataType="xsd:double" size="8" dictRef="cc:percent">38.37 28.43 14.01 6.86 3.39 3.36 -1.08 1.06</array>
              <array dataType="xsd:integer" size="8" dictRef="cc:sfo1">1 1 1 1 1 2 3 1</array>
              <array dataType="xsd:string" size="8" dictRef="cc:sfo2">S S S S S S S P:x</array>
              <array dataType="xsd:double" size="8" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -24.134 -5.836 1.298 -9.197</array>
              <array dataType="xsd:double" size="8" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 2.0 0.0 1.33</array>
              <array dataType="xsd:integer" size="8" dictRef="cc:fragment1">13 21 25 11 33 1 1 13</array>
              <array dataType="xsd:string" size="8" dictRef="cc:fragment2">O O O O O W W O</array>
             </list>
             <list cmlx:templateRef="mo">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-14.212</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">2.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">11</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">A2.u</scalar>
              <array dataType="xsd:double" size="9" dictRef="cc:percent">52.14 26.3 7.86 3.9 1.86 1.19 1.12 1.05 1.04</array>
              <array dataType="xsd:integer" size="9" dictRef="cc:sfo1">1 1 1 1 2 1 1 1 2</array>
              <array dataType="xsd:string" size="9" dictRef="cc:sfo2">S S S S S P:x S D:z2 S</array>
              <array dataType="xsd:double" size="9" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -5.836 -9.197 -24.134 -4.634 -5.836</array>
              <array dataType="xsd:double" size="9" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 1.33 2.0 0.8 2.0</array>
              <array dataType="xsd:integer" size="9" dictRef="cc:fragment1">13 21 11 33 1 13 37 1 9</array>
              <array dataType="xsd:string" size="9" dictRef="cc:fragment2">O O O O W O O W W</array>
             </list>
             <list cmlx:templateRef="mo">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-13.745</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">2.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">15</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">E1.u:1</scalar>
              <array dataType="xsd:double" size="6" dictRef="cc:percent">36.8 33.87 19.25 3.24 1.98 1.46</array>
              <array dataType="xsd:integer" size="6" dictRef="cc:sfo1">1 1 1 1 2 1</array>
              <array dataType="xsd:string" size="6" dictRef="cc:sfo2">S S S S S D:z2</array>
              <array dataType="xsd:double" size="6" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -5.836 -4.634</array>
              <array dataType="xsd:double" size="6" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 0.8</array>
              <array dataType="xsd:integer" size="6" dictRef="cc:fragment1">31 13 27 33 1 1</array>
              <array dataType="xsd:string" size="6" dictRef="cc:fragment2">O O O O W W</array>
             </list>
             <list cmlx:templateRef="mo">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-13.745</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">2.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">15</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">E1.u:2</scalar>
              <array dataType="xsd:double" size="6" dictRef="cc:percent">36.8 33.87 19.25 3.24 1.98 1.46</array>
              <array dataType="xsd:integer" size="6" dictRef="cc:sfo1">1 1 1 1 2 1</array>
              <array dataType="xsd:string" size="6" dictRef="cc:sfo2">S S S S S D:z2</array>
              <array dataType="xsd:double" size="6" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -5.836 -4.634</array>
              <array dataType="xsd:double" size="6" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 0.8</array>
              <array dataType="xsd:integer" size="6" dictRef="cc:fragment1">25 13 21 39 5 5</array>
              <array dataType="xsd:string" size="6" dictRef="cc:fragment2">O O O O W W</array>
             </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="molecular.orbitals2">
         <module cmlx:lineCount="4714" cmlx:templateRef="molecular.orbitals">
             <list cmlx:templateRef="mo" spin="1">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-8.225</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">1.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">20</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">A1</scalar>
              <array dataType="xsd:double" size="10" dictRef="cc:percent">32.51 17.93 13.22 10.33 6.46 4.22 3.39 2.62 1.59 1.24</array>
              <array dataType="xsd:integer" size="10" dictRef="cc:sfo1">1 1 1 1 1 1 1 2 1 1</array>
              <array dataType="xsd:string" size="10" dictRef="cc:sfo2">S S S S S S S S S S</array>
              <array dataType="xsd:double" size="10" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -5.836 -24.134 -24.134</array>
              <array dataType="xsd:double" size="10" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0</array>
              <array dataType="xsd:integer" size="10" dictRef="cc:fragment1">17 23 13 25 12 21 35 3 11 33</array>
              <array dataType="xsd:string" size="10" dictRef="cc:fragment2">O O O O O O O W O O</array>
             </list>
             <list cmlx:templateRef="mo" spin="1">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-8.067</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">1.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">21</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">A1</scalar>
              <array dataType="xsd:double" size="9" dictRef="cc:percent">48.78 15.26 8.55 5.21 4.55 3.93 2.55 1.36 1.2</array>
              <array dataType="xsd:integer" size="9" dictRef="cc:sfo1">1 1 1 1 1 1 1 1 1</array>
              <array dataType="xsd:string" size="9" dictRef="cc:sfo2">S S S S S S S S D:z2</array>
              <array dataType="xsd:double" size="9" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -4.634</array>
              <array dataType="xsd:double" size="9" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0 0.8</array>
              <array dataType="xsd:integer" size="9" dictRef="cc:fragment1">13 17 21 23 11 33 12 35 1</array>
              <array dataType="xsd:string" size="9" dictRef="cc:fragment2">O O O O O O O O W</array>
             </list>
             <list cmlx:templateRef="mo" spin="2">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-8.215</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">1.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">20</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">A1</scalar>
              <array dataType="xsd:double" size="10" dictRef="cc:percent">34.44 16.27 13.49 10.22 6.54 3.66 3.54 2.46 1.58 1.25</array>
              <array dataType="xsd:integer" size="10" dictRef="cc:sfo1">1 1 1 1 1 1 1 2 1 1</array>
              <array dataType="xsd:string" size="10" dictRef="cc:sfo2">S S S S S S S S S S</array>
              <array dataType="xsd:double" size="10" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -5.836 -24.134 -24.134</array>
              <array dataType="xsd:double" size="10" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0</array>
              <array dataType="xsd:integer" size="10" dictRef="cc:fragment1">17 23 13 25 12 21 35 3 11 33</array>
              <array dataType="xsd:string" size="10" dictRef="cc:fragment2">O O O O O O O W O O</array>
             </list>
             <list cmlx:templateRef="mo" spin="2">
              <scalar dataType="xsd:double" dictRef="cc:mo.energy" units="nonsi:electronvolt">-8.06</scalar>
              <scalar dataType="xsd:double" dictRef="cc:mo.occupation">1.0</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:mo.number">21</scalar>
              <scalar dataType="xsd:string" dictRef="cc:mo.label">A1</scalar>
              <array dataType="xsd:double" size="9" dictRef="cc:percent">50.37 15.77 7.28 4.53 4.43 4.02 2.49 1.37 1.34</array>
              <array dataType="xsd:integer" size="9" dictRef="cc:sfo1">1 1 1 1 1 1 1 1 1</array>
              <array dataType="xsd:string" size="9" dictRef="cc:sfo2">S S S S S S S S D:z2</array>
              <array dataType="xsd:double" size="9" dictRef="cc:energy" units="nonsi:electronvolt">-24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -24.134 -4.634</array>
              <array dataType="xsd:double" size="9" dictRef="cc:occupation">2.0 2.0 2.0 2.0 2.0 2.0 2.0 2.0 0.8</array>
              <array dataType="xsd:integer" size="9" dictRef="cc:fragment1">13 17 21 11 23 33 12 35 1</array>
              <array dataType="xsd:string" size="9" dictRef="cc:fragment2">O O O O O O O O W</array>
             </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="restricted" pattern="\s+E\(eV\)\s+Occ.*" endPattern="~" endOffset="1" repeat="*">    <record repeat="3" />    <templateList>      <template pattern="(\s*\S+\s*){11}+" endPattern=".*$(\s*\S+\s*){11}+" endPattern2="~" repeat="*" endOffset="1">        <record id="mo">\s*{F,cc:mo.energy}{F,cc:mo.occupation}{I,cc:mo.number}{A,cc:mo.label}{F,cc:percent}%{I,cc:sfo1}{A,cc:sfo2}{F,cc:energy}{F,cc:occupation}{I,cc:fragment1}{A,cc:fragment2}\s*</record>        <record id="mo" repeat="*">\s*{F,cc:percent}%{I,cc:sfo1}{A,cc:sfo2}{F,cc:energy}{F,cc:occupation}{I,cc:fragment1}{A,cc:fragment2}\s*</record>        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:percent']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:sfo1']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:sfo2']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:energy']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:occupation']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:fragment1']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:fragment2']" />                                        
                   </template>                       
               </templateList>       
           </template>  <template id="unrestricted" pattern="\s*\*\*\*\s*SPIN.*" endPattern="(\s*\S+\s*){7,}+\s*$\s*" endPattern2="~" endOffset="1" repeat="*">    <record id="spin">\s*\*\*\*\s*SPIN{I,cc:spin}.*</record>    <record repeat="5" />    <templateList>      <template pattern="(\s*\S+\s*){11}+" endPattern=".*$(\s*\S+\s*){11}+\s*" endPattern2="~" endOffset="1" repeat="*">        <record id="mo">\s*{F,cc:mo.energy}{F,cc:mo.occupation}{I,cc:mo.number}{A,cc:mo.label}{F,cc:percent}%{I,cc:sfo1}{A,cc:sfo2}{F,cc:energy}{F,cc:occupation}{I,cc:fragment1}{A,cc:fragment2}\s*</record>        <record id="mo" repeat="*">\s*{F,cc:percent}%{I,cc:sfo1}{A,cc:sfo2}{F,cc:energy}{F,cc:occupation}{I,cc:fragment1}{A,cc:fragment2}\s*</record>        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:percent']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:sfo1']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:sfo2']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:energy']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:occupation']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:fragment1']" />        <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:fragment2']" />                                        
                   </template>                       
               </templateList>    <transform process="pullup" repeat="1" xpath=".//cml:scalar[@dictRef='cc:spin']" />    <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='mo']" name="spin" value="$string(../../cml:scalar[@dictRef='cc:spin'])" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='cc:spin']" />
           </template>
       </templateList>
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:mo.energy']" value="nonsi:electronvolt" />
   <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:energy']" value="nonsi:electronvolt" />
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='mo']/cml:list/*" />
   <transform process="move" xpath=".//cml:list[@cmlx:templateRef='mo']" to="." />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
.. |image3| image:: ../../imgs/Total.png
.. |image4| image:: ../../imgs/Total.png
