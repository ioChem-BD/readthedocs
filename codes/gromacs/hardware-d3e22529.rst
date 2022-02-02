.. _hardware-d3e22529:

hardware
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
   | id                                                                                                                         | hardware                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Hardware section                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Detecting&#92;sCPU&#92;sSIMD&#92;sinstructions.\*                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*GPUs&#92;sauto-selected.\*                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 2                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/hardware.xml                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   Detecting CPU SIMD instructions.
   Present hardware specification:
   Vendor: GenuineIntel
   Brand:  Intel(R) Xeon(R) CPU E5-2697 v2 @ 2.70GHz
   Family:  6  Model: 62  Stepping:  4
   Features: aes apic avx clfsh cmov cx8 cx16 f16c htt lahf_lm mmx msr nonstop_tsc pcid pclmuldq pdcm pdpe1gb popcnt pse rdrnd rdtscp sse2 sse3 sse4.1 sse4.2 ssse3 tdt x2apic
   SIMD instructions most likely to fit this hardware: AVX_256
   SIMD instructions selected at GROMACS compile time: AVX_256


   4 GPUs detected:
     #0: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible
     #1: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible
     #2: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible
     #3: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible

   4 GPUs auto-selected for this run.
   Mapping of GPUs to the 4 PP ranks in this node: #0, #1, #2, #3
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="hardware">
           <module cmlx:templateRef="hardware">
                <list dictRef="hardware">
                   <scalar dataType="xsd:string" dictRef="gm:hardware">Detecting CPU SIMD instructions.</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">Present hardware specification:</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">Vendor: GenuineIntel</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">Brand:  Intel(R) Xeon(R) CPU E5-2697 v2 @ 2.70GHz</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">Family:  6  Model: 62  Stepping:  4</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">Features: aes apic avx clfsh cmov cx8 cx16 f16c htt lahf_lm mmx msr nonstop_tsc pcid pclmuldq pdcm pdpe1gb popcnt pse rdrnd rdtscp sse2 sse3 sse4.1 sse4.2 ssse3 tdt x2apic</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">SIMD instructions most likely to fit this hardware: AVX_256</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">SIMD instructions selected at GROMACS compile time: AVX_256</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">4 GPUs detected:</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">#0: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">#1: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">#2: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible</scalar>
                   <scalar dataType="xsd:string" dictRef="gm:hardware">#3: NVIDIA Tesla K20m, compute cap.: 3.5, ECC: yes, stat: compatible</scalar>
                   <scalar dataType="xsd:integer" dictRef="gm:numProcGPU">4</scalar>
                   <scalar dataType="xsd:integer" dictRef="gm:numRanks">4</scalar>
                </list>
             </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern="\s*Detecting\sCPU\sSIMD\sinstructions.*" pattern2=".*GPUs\sdetected.*" endPattern="\s*" endPattern2="~" endOffset="0" repeat="*">    <record repeat="*">{X,gm:hardware}</record>
           </template>  <template pattern=".*GPUs\sauto-selected.*" endPattern="\s*" endPattern2="~">    <record repeat="*">{I,gm:numProcGPU}GPUs\sauto-selected.*</record>    <record>\s*Mapping\sof\sGPUs\sto\sthe{I,gm:numRanks}.*ranks\sin\sthis\snode:.*</record>
           </template>  <transform process="addChild" xpath="." elementName="cml:list" dictRef="hardware" />  <transform process="moveRelative" xpath=".//cml:scalar" to="../../../cml:list[@dictRef='hardware']" />  <transform process="delete" xpath=".//cml:module" />
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
