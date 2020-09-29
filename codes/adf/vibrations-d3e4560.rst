.. _vibrations-d3e4560:

vibrations
==========

.. table:: Implementation level

   +-----------------------------------+-----------------------------------+
   | Type                              | Status                            |
   +===================================+===================================+
   | CML extraction template           | |image0|                          |
   +-----------------------------------+-----------------------------------+
   | HTML5 representation              | |image1|                          |
   +-----------------------------------+-----------------------------------+

.. table:: Template attributes

   +-----------------------------------+-----------------------------------+
   | Attribute                         | Value                             |
   +===================================+===================================+
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | vibrations                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Frequencies and normal modes      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*                              |
   |                                   | Vibrations\sand\sNormal\sModes.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s+List\sof\sAll\sFrequencies.\* |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | frequencyanalysis/vibrations.xml  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    ===========================
    Vibrations and Normal Modes  ***  (cartesian coordinates, NOT mass-weighted)  ***
    ===========================
     
    The headers on the normal mode eigenvectors below give the Frequency in cm-1
    (a negative value means an imaginary frequency, no output for (almost-)zero frequencies)


                          -28.256                        45.406                        54.750
                 ------------------------      ------------------------      ------------------------
       1.C         -0.012   0.007  -0.020         0.041  -0.105  -0.038        -0.005  -0.030   0.101
       2.C         -0.004   0.034  -0.019         0.035  -0.097  -0.044         0.022  -0.037   0.100
       3.C         -0.019   0.001  -0.004         0.012  -0.113  -0.038        -0.023  -0.039   0.094
       4.C          0.010   0.043   0.000         0.012  -0.104  -0.038         0.022  -0.031   0.099
       5.C          0.009   0.029   0.012        -0.054  -0.129  -0.034        -0.011  -0.035   0.098
       6.C          0.013  -0.016  -0.022         0.029  -0.099  -0.038        -0.025  -0.028   0.091
       7.C         -0.014   0.051  -0.027         0.008  -0.086  -0.036         0.024  -0.034   0.095
       8.C         -0.026  -0.035  -0.003         0.039  -0.084  -0.047        -0.048  -0.056   0.074
       9.C          0.006   0.066   0.001         0.021  -0.076  -0.020         0.043  -0.007   0.095


                          100.940                       118.700                       121.007
                 ------------------------      ------------------------      ------------------------
       1.C          0.088   0.006   0.008        -0.002  -0.040   0.029         0.022   0.033   0.035
       2.C          0.095   0.007   0.000        -0.018  -0.040   0.029         0.005   0.032   0.034
       3.C          0.060  -0.008   0.007        -0.014  -0.042   0.030         0.042   0.033   0.038
       4.C          0.075  -0.005   0.000        -0.041  -0.042   0.033         0.012   0.033   0.036
       5.C          0.004  -0.020   0.005        -0.040  -0.041   0.031         0.037   0.033   0.037
       6.C          0.071   0.023   0.010         0.016  -0.050   0.035         0.018   0.039   0.039
       7.C          0.078   0.025  -0.001        -0.014  -0.047   0.033        -0.015   0.041   0.040
       8.C          0.058  -0.009  -0.002        -0.002  -0.046   0.035         0.055   0.032   0.049
       9.C          0.074  -0.005   0.007        -0.053  -0.042   0.044        -0.006   0.034   0.045

**Output text.**

.. code:: xml

   <comment class="example.output" id="vibrations">
           <module cmlx:lineCount="36" cmlx:templateRef="vibrations">
               <array dataType="xsd:double" size="6" dictRef="cc:frequency">-28.256 45.406 54.75 100.94 118.7 121.007</array>
               <array dataType="xsd:string" dictRef="cc:elementType" size="9">C C C C C C C C C</array>
               <array dataType="xsd:double" size="162" dictRef="cc:displacement">-0.012 0.007 -0.02 -0.004 0.034 -0.019 -0.019 0.001 -0.004 0.01 0.043 0.0 0.009 0.029 0.012 0.013 -0.016 -0.022 -0.014 0.051 -0.027 -0.026 -0.035 -0.003 0.006 0.066 0.001 0.041 -0.105 -0.038 0.035 -0.097 -0.044 0.012 -0.113 -0.038 0.012 -0.104 -0.038 -0.054 -0.129 -0.034 0.029 -0.099 -0.038 0.008 -0.086 -0.036 0.039 -0.084 -0.047 0.021 -0.076 -0.02 -0.005 -0.03 0.101 0.022 -0.037 0.1 -0.023 -0.039 0.094 0.022 -0.031 0.099 -0.011 -0.035 0.098 -0.025 -0.028 0.091 0.024 -0.034 0.095 -0.048 -0.056 0.074 0.043 -0.007 0.095 0.088 0.006 0.008 0.095 0.007 0.0 0.06 -0.008 0.007 0.075 -0.005 0.0 0.004 -0.02 0.005 0.071 0.023 0.01 0.078 0.025 -0.001 0.058 -0.009 -0.002 0.074 -0.005 0.007 -0.002 -0.04 0.029 -0.018 -0.04 0.029 -0.014 -0.042 0.03 -0.041 -0.042 0.033 -0.04 -0.041 0.031 0.016 -0.05 0.035 -0.014 -0.047 0.033 -0.002 -0.046 0.035 -0.053 -0.042 0.044 0.022 0.033 0.035 0.005 0.032 0.034 0.042 0.033 0.038 0.012 0.033 0.036 0.037 0.033 0.037 0.018 0.039 0.039 -0.015 0.041 0.04 0.055 0.032 0.049 -0.006 0.034 0.045</array>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="8" />
   <templateList>  <template pattern="(\s*[-0-9\.]+\s*){1,3}+" endPattern="\s*" endOffset="0" repeat="*">    <templateList>      <template pattern="(\s*[-0-9\.]+\s*){1,3}+" endPattern=".*" endOffset="1">        <record id="freq">{1_3F,cc:frequency}</record>          
                   </template>      <template pattern="\s*\S+\.[a-zA-Z]+(\s+\S+){9}\s*" endPattern="~">        <record id="displacement3" makeArray="true" repeat="*">\s*\S+\.{A,cc:elementType}{3F,cc:displacement}{3F,cc:displacement2}{3F,cc:displacement3}</record>
                   </template>      <template pattern="\s*\S+\.[a-zA-Z]+(\s+\S+){6}\s*" endPattern="~">        <record id="displacement2" makeArray="true" repeat="*">\s*\S+\.{A,cc:elementType}{3F,cc:displacement}{3F,cc:displacement2}</record>
                   </template>      <template pattern="\s*\S+\.[a-zA-Z]+(\s+\S+){3}\s*" endPattern="~">        <record id="displacement1" makeArray="true" repeat="*">\s*\S+\.{A,cc:elementType}{3F,cc:displacement}</record>
                   </template>
               </templateList>               
           </template>
       </templateList>
   <transform process="joinArrays" xpath=".//cml:array[@dictRef='cc:frequency']" />
   <transform process="joinArrays" xpath=".//cml:array[starts-with(@dictRef,'cc:displacement')]" />
   <transform process="pullup" xpath=".//cml:array" repeat="3" />
   <transform process="delete" xpath="(.//cml:array[@dictRef='cc:elementType'])[position() >=2]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath="./cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
