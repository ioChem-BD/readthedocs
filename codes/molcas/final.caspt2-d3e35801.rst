.. _final.caspt2-d3e35801:

final.caspt2
============

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
   | id                                                                                                                         | final.caspt2                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Final CASPT2 result                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*FINAL&#92;sCASPT2&#92;sRESULT:.\*                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;+&#92;+&#92;sDenominators                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s{0,4}&#92;S.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/caspt2/final.caspt2.xml                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

     FINAL CASPT2 RESULT:

         Reference energy:        -190.6773098467
         E2 (Non-variational):      -0.6061449426
         Shift correction:          -0.0021160684
         E2 (Variational):          -0.6082610111
         Total energy:            -191.2855708577
         Residual norm:              0.0000004726
         Reference weight:           0.82136

         Contributions to the CASPT2 correlation energy
         Active & Virtual Only:         -0.1862740836
         One Inactive Excited:          -0.2303322543
         Two Inactive Excited:          -0.1895386047

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="final.caspt2">
           <module cmlx:templateRef="final.caspt2">
              <scalar dataType="xsd:double" dictRef="m:referener">-190.6773098467</scalar>
              <scalar dataType="xsd:double" dictRef="m:nonvare2">-0.6061449426</scalar>
              <scalar dataType="xsd:double" dictRef="m:shiftcorr">-0.0021160684</scalar>
              <scalar dataType="xsd:double" dictRef="m:vare2">-0.6082610111</scalar>
              <scalar dataType="xsd:double" dictRef="m:totalenergy">-191.2855708577</scalar>
              <scalar dataType="xsd:double" dictRef="m:residualnorm">0.0000004726</scalar>
              <scalar dataType="xsd:double" dictRef="m:refweight">0.82136</scalar>
              <scalar dataType="xsd:double" dictRef="m:activevirt">-0.1862740836</scalar>
              <scalar dataType="xsd:double" dictRef="m:oneeinactive">-0.2303322543</scalar>
              <scalar dataType="xsd:double" dictRef="m:twoinactive">-0.1895386047</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*Reference\senergy:.*" endPattern=".*" endPattern2="~">    <record>\s*Reference\senergy:{F,m:referener}</record>       
           </template>  <template pattern="\s*E2\s\(Non-variational\):.*" endPattern=".*" endPattern2="~">    <record>\s*E2\s\(Non-variational\):{F,m:nonvare2}</record>
           </template>  <template pattern="\s*Shift\scorrection:.*" endPattern=".*" endPattern2="~">    <record>\s*Shift\scorrection:{F,m:shiftcorr}</record>
           </template>  <template pattern="\s*E2\s\(Variational\):.*" endPattern=".*" endPattern2="~">    <record>\s*E2\s\(Variational\):{F,m:vare2}</record>
           </template>  <template pattern="\s*Total\senergy:.*" endPattern=".*" endPattern2="~">    <record>\s*Total\senergy:{F,m:totalenergy}</record>
           </template>  <template pattern="\s*Residual\snorm:.*" endPattern=".*" endPattern2="~">    <record>\s*Residual\snorm:{F,m:residualnorm}</record>
           </template>  <template pattern="\s*Reference\sweight:.*" endPattern=".*" endPattern2="~">    <record>\s*Reference\sweight:{F,m:refweight}</record>
           </template>  <template pattern="\s*Active.*Virtual\sOnly:.*" endPattern=".*" endPattern2="~">    <record>\s*Active.*Virtual Only:{F,m:activevirt}</record>
           </template>  <template pattern="\s*One\sInactive\sExcited:.*" endPattern=".*" endPattern2="~">    <record>\s*One\sInactive\sExcited:{F,m:oneeinactive}</record>
           </template>  <template pattern="\s*Two\sInactive\sExcited:.*" endPattern=".*" endPattern2="~">    <record>\s*Two\sInactive\sExcited:{F,m:twoinactive}</record>
           </template>       
       </templateList>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
