.. _extras-d3e35345:

extras
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
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | extras                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Extra lines                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Type&#92;sof&#92;s+Fock&#92;soperator&#92;sto&#92;suse.\*                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/extras.xml                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         Type of  Fock operator to use: STANDARD
         Type of HZERO operator to use: NON-STANDARD IPEA
         Extra imaginary denominator shift SHIFTI=      0.30000000
         Non-standard "IP-EA" denominator shift IPEAshift=      0.00000000
         The CANONICAL keyword was not used in the RASSCF program.
         Therefore, input orbitals should be transformed.
         The input orbitals and the CI vector will be transformed.

.. container:: formalpara-title

   **Input**

::

    
         Type of  Fock operator to use: STANDARD
         Type of HZERO operator to use: STANDARD IPEA
         Extra denominator shift SHIFT=      0.05000000
         The CANONICAL keyword was not used in the RASSCF program.
         Therefore, input orbitals should be transformed.
         The input orbitals and the CI vector will be transformed.

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="extras">
           <module cmlx:templateRef="extras">
               <scalar dataType="xsd:string" dictRef="m:fockoperator">STANDARD</scalar>
               <scalar dataType="xsd:string" dictRef="m:hzerooperator">NON-STANDARD IPEA</scalar>
               <scalar dataType="xsd:double" dictRef="m:shifti">0.30000000</scalar>
               <scalar dataType="xsd:double" dictRef="m:ipeashift">0.00000000</scalar>
           </module>        
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="extras2">
           <module cmlx:templateRef="extras">
               <scalar dataType="xsd:string" dictRef="m:fockoperator">STANDARD</scalar>
               <scalar dataType="xsd:string" dictRef="m:hzerooperator">STANDARD IPEA</scalar>
               <scalar dataType="xsd:double" dictRef="m:shift">0.05000000</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <template pattern="\s*Type\sof\s+Fock\soperator\sto\suse:\s.*" endPattern=".*" endPattern2="~">  <record>\s*Type\sof\s+Fock\soperator\sto\suse:{X,m:fockoperator}</record>
       </template>
   <template pattern="\s*Type\sof\sHZERO\soperator\sto\suse:\s.*" endPattern=".*" endPattern2="~">  <record>\s*Type\sof\sHZERO\soperator\sto\suse:\s{X,m:hzerooperator}</record>
       </template>
   <template pattern="\s*Extra\simaginary\sdenominator\sshift\sSHIFTI=.*" endPattern=".*" endPattern2="~">  <record>\s*Extra\simaginary\sdenominator\sshift\sSHIFTI={F,m:shifti}</record>
       </template>
   <template pattern="\s*Non-standard\s.IP-EA.\sdenominator\sshift\sIPEAshift=.*" endPattern=".*" endPattern2="~">  <record>\s*Non-standard\s.IP-EA.\sdenominator\sshift\sIPEAshift={F,m:ipeashift}</record>
       </template>
   <template pattern="\s*Extra\sdenominator\sshift\sSHIFT=.*" endPattern=".*" endPattern2="~">  <record>\s*Extra\sdenominator\sshift\sSHIFT={F,m:shift}</record>
       </template>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
