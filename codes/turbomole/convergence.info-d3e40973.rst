.. _convergence.info-d3e40973:

convergence.info
================

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
   | id                                                                                                                         | convergence.info                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Convergence information section                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;*{10,}&#92;s*$&#92;s*CONVERGENCE&#92;sINFORMATION.\*                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;*{10,}&#92;s\*                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | minimumts/convergence.info.xml                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

         ****************************************************************** 
                             CONVERGENCE INFORMATION

                                  Converged?     Value      Criterion
                Energy change         yes      0.0000004   0.0000010
                RMS of displacement   yes      0.0000800   0.0005000
                RMS of gradient       yes      0.0000092   0.0005000
                MAX displacement      yes      0.0003920   0.0010000
                MAX gradient          yes      0.0000313   0.0010000
         ******************************************************************                             
       

.. container:: formalpara-title

   **Input**

::

         ****************************************************************** 
                             CONVERGENCE INFORMATION

                                  Converged?     Value      Criterion
                Energy change         yes      0.0000020   0.0001000
                MAX geom. grad.       yes      0.0008366   0.0010000
         ******************************************************************                            
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="convergence.info">
           <module cmlx:lineCount="10" cmlx:templateRef="convergence.info">
               <list cmlx:templateRef="energyChange">
                 <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:value">0.0000004</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:criterion">0.0000010</scalar>
               </list>
               <list cmlx:templateRef="rmsDisplacement">
                 <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:value">0.0000800</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:criterion">0.0005000</scalar>
               </list>
               <list cmlx:templateRef="rmsGradient">
                 <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:value">0.0000092</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:criterion">0.0005000</scalar>
               </list>
               <list cmlx:templateRef="maxDisplacement">
                 <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:value">0.0003920</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:criterion">0.0010000</scalar>
               </list>
               <list cmlx:templateRef="maxGradient">
                 <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:value">0.0000313</scalar>
                 <scalar dataType="xsd:string" dictRef="cc:criterion">0.0010000</scalar>
               </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output2" id="convergence.info">
          <module cmlx:lineCount="7" cmlx:templateRef="convergence.info">
           <list cmlx:templateRef="energyChange">
            <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.0000020</scalar>
            <scalar dataType="xsd:string" dictRef="cc:criterion">0.0001000</scalar>
           </list>
           <list cmlx:templateRef="maxGradient">
            <scalar dataType="xsd:string" dictRef="cc:converged">yes</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.0008366</scalar>
            <scalar dataType="xsd:string" dictRef="cc:criterion">0.0010000</scalar>
           </list>
          </module>  
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="4" />
   <templateList>  <template pattern="\s*Energy\schange.*" endPattern=".*">    <record id="energyChange">\s*Energy\schange\s*{A,cc:converged}{A,cc:value}{A,cc:criterion}</record>
           </template>  <template pattern="\s*RMS\sof\sdisplacement.*" endPattern=".*">    <record id="rmsDisplacement">\s*RMS\sof\sdisplacement\s*{A,cc:converged}{A,cc:value}{A,cc:criterion}</record>
           </template>  <template pattern="\s*RMS\sof\sgradient.*" endPattern=".*">    <record id="rmsGradient">\s*RMS\sof\sgradient\s*{A,cc:converged}{A,cc:value}{A,cc:criterion}</record>
           </template>  <template pattern="\s*MAX\sdisplacement.*" endPattern=".*">    <record id="maxDisplacement">\s*MAX\sdisplacement\s*{A,cc:converged}{A,cc:value}{A,cc:criterion}</record>
           </template>  <template pattern="\s*MAX.*(gradient|grad\.).*" endPattern=".*">    <record id="maxGradient">\s*MAX.*(?:gradient|grad\.)\s*{A,cc:converged}{A,cc:value}{A,cc:criterion}</record>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="pullup" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
