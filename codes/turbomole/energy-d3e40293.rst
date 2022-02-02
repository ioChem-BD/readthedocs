.. _energy-d3e40293:

energy
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
   | *source*                                                                                                                   | Turbomole log                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | energy                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Final energies section                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;*{10,}&#92;s*$&#92;s*&#92;*&#92;s*&#92;*&#92;s*$&#92;s*&#92;*&#92;s+RHF&#92;s+energy.\*                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;*{10,}&#92;s\*                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | energy.xml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         *********************************************************************
         *                                                                   *
         *  RHF  energy                             :   -227.9061850367      *
         *  CCSD correlation energy                 :     -0.8835141933      *
         *  E4 doubles and triples contribution     :     -0.0356016214      *
         *  E5 singles and triples contribution     :      0.0019555922      *
         *  total correlation energy                :     -0.9171602226      *
         *                                                                   *
         *  Final CCSD(T) energy                    :   -228.8233452593      *
         *                                                                   *
         *  D1 diagnostic (CCSD)                    :      0.0560            *
         *                                                                   *
         *********************************************************************
       

.. container:: formalpara-title

   **Input**

::

         *********************************************************************
         *                                                                   *
         *  RHF  energy                             :   -227.9061850367      *
         *  MP2 correlation energy (doubles)        :     -0.8639282496      *
         *                                                                   *
         *  Final MP2 energy                        :   -228.7701132863      *
         *                                                                   *
         *   E(S)   =     -0.5531547215      E(T)   =     -0.3107735281      *
         *   E(OS)  =     -0.6567458975      E(SS)  =     -0.2071823521      *
         *                                                                   *
         *  SCS-MP2 energy                          :   -228.7633408977      *
         *  (computed with  C(OS) =   1.2000  and  C(SS) =   0.3333)         *
         *                                                                   *
         *  SOS-MP2 energy                          :   -228.7599547035      *
         *  (computed with  C(OS) =   1.3000)                                *
         *                                                                   *
         *  Norm of MP1 T2 amplitudes               :      0.2766656730      *
         *                                                                   *
         ********************************************************************* 
       

.. container:: formalpara-title

   **Input**

::

         *********************************************************************
         *                                                                   *
         *  RHF  energy                             :   -227.9061850367      *
         *  correlation energy                      :     -0.8835141933      *
         *                                                                   *
         *  Final CCSD energy                       :   -228.7896992300      *
         *                                                                   *
         *  D1 diagnostic                           :      0.0560            *
         *                                                                   *
         ********************************************************************* 
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="energy">
            <module cmlx:templateRef="energy">
              <scalar dataType="xsd:double" dictRef="t:rhfEnergy" units="nonsi:hartree">-227.9061850367</scalar>
               <module dictRef="CCSD(T)">
                  <scalar dataType="xsd:double" dictRef="t:finalEnergy" units="nonsi:hartree">-228.8233452593</scalar>
               </module>
               <scalar dataType="xsd:double" dictRef="t:d1diagnostic">0.0560</scalar>
            </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="energy2">
            <module cmlx:templateRef="energy">
               <scalar dataType="xsd:double" dictRef="t:rhfEnergy" units="nonsi:hartree">-227.9061850367</scalar>
               <module dictRef="MP2">
                  <scalar dataType="xsd:double" dictRef="t:finalEnergy" units="nonsi:hartree">-228.7701132863</scalar>
               </module>
            </module>            
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="energy3">
            <module cmlx:templateRef="energy">
               <scalar dataType="xsd:double" dictRef="t:rhfEnergy" units="nonsi:hartree">-227.9061850367</scalar>
               <module dictRef="CCSD">
                  <scalar dataType="xsd:double" dictRef="t:finalEnergy" units="nonsi:hartree">-228.7896992300</scalar>
               </module>
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template name="rhfenergy" pattern="\s*\*\s+RHF\s+energy\s+:.*" endPattern=".*" endPattern2="~" endOffset="0">    <record>\s*\*\s+RHF\s+energy\s+:{F,t:rhfEnergy}\*</record>            
           </template>  <template name="finalenergy" pattern="\s*\*\s+Final.*energy.*" endPattern=".*" endPattern2="~" endOffset="0">    <record>\s*\*\s+Final\s*{A,t:module}\s*energy\s+:{F,t:finalEnergy}.*</record>    <transform process="addAttribute" xpath="." name="dictRef" value="$string(.//cml:scalar[@dictRef='t:module']/text())" />    <transform process="pullup" xpath=".//cml:scalar[@dictRef='t:finalEnergy']" repeat="2" />    <transform process="delete" xpath=".//cml:list" />
           </template>  <template name="d1diagnostic" pattern="\s*\*\s+D1\sdiagnostic\s\(CCSD\)\s+:.*" endPattern=".*" endPattern2="~" endOffset="0">    <record>\s*\*\s+D1\sdiagnostic\s\(CCSD\)\s+:{F,t:d1diagnostic}\*</record>             
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:list/cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='t:finalEnergy']" value="nonsi:hartree" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='t:rhfEnergy']" value="nonsi:hartree" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
