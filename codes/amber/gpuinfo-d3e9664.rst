.. _gpuinfo-d3e9664:

gpuinfo
=======

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
   | id                                                                                                                         | gpuinfo                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | GPU device info                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;|-{10,}&#92;s*GPU&#92;sDEVICE&#92;sINFO.\*                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;|-{20,}                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | gpuinfo.xml                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   |------------------- GPU DEVICE INFO --------------------
   |
   |            CUDA_VISIBLE_DEVICES: 0
   |   CUDA Capable Devices Detected:      1
   |           CUDA Device ID in use:      0
   |                CUDA Device Name: Tesla V100-SXM2-16GB
   |     CUDA Device Global Mem Size:  16128 MB
   | CUDA Device Num Multiprocessors:     80
   |           CUDA Device Core Freq:   1.53 GHz
   |
   |--------------------------------------------------------
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="gpuinfo">
            <module cmlx:templateRef="gpuinfo">
                 <list cmlx:templateRef="gpu">
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA_VISIBLE_DEVICES</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">0</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA Capable Devices Detected</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">1</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA Device ID in use</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">0</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA Device Name</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">Tesla V100-SXM2-16GB</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA Device Global Mem Size</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">16128 MB</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA Device Num Multiprocessors</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">80</scalar>
                    </list>
                    <list>
                       <scalar dataType="xsd:string" dictRef="cc:parameter">CUDA Device Core Freq</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:value">1.53 GHz</scalar>
                    </list>
                 </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*\|.*:.*" endPattern="\s*\|\s+\S.*$\s*\|\s*" endPattern2="~" endOffset="1" repeat="*">    <record id="gpu" repeat="*">\s*\|{X,cc:parameter}:{X,cc:value}</record>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='gpu']" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
