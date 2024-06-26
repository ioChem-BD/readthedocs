.. _qespresso.bands-d3e60797:

qespresso.bands
===============

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
   | *source*                                                                                                                   | QuantumEspresso bands                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | qespresso.bands                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | QuantumEspresso bands                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    &plot nbnd=  34, nks=   202 /
               0.000000  0.000000  0.000000
     -91.768  -91.768  -91.731  -91.731  -91.731  -20.772   -4.487   -3.537   -2.948   -2.948
      -2.948    8.069    8.069    8.069   11.211   11.211   11.211   14.016   14.016   14.016
      14.245   14.640   14.640   14.640   17.785   17.785   18.624   23.759   23.759   23.759
      27.589   27.589   27.589   34.835
               0.025000 -0.014434  0.020412
     -91.768  -91.768  -91.731  -91.731  -91.731  -20.771   -4.525   -3.542   -2.952   -2.952
      -2.907    8.078    8.078    8.086   11.186   11.216   11.216   14.014   14.016   14.016
      14.246   14.626   14.637   14.637   17.795   17.800   18.652   23.742   23.745   23.745
      27.580   27.597   27.597   34.892
               0.050000 -0.028868  0.040825
     -91.768  -91.768  -91.731  -91.731  -91.731  -20.767   -4.630   -3.557   -2.963   -2.963
      -2.792    8.107    8.107    8.137   11.112   11.231   11.231   14.007   14.018   14.018
      14.249   14.589   14.628   14.628   17.825   17.841   18.734   23.691   23.704   23.704
      27.555   27.622   27.622   35.056
               0.075000 -0.043301  0.061237
     -91.768  -91.768  -91.731  -91.731  -91.731  -20.759   -4.778   -3.581   -2.980   -2.980
      -2.628    8.155    8.155    8.221   10.993   11.254   11.254   13.997   14.020   14.020
      14.255   14.534   14.613   14.613   17.875   17.903   18.865   23.607   23.637   23.637
      27.525   27.661   27.661   35.311
               0.100000 -0.057735  0.081650
     -91.768  -91.768  -91.731  -91.731  -91.731  -20.750   -4.950   -3.613   -3.004   -3.004
      -2.433    8.222    8.222    8.336   10.833   11.285   11.285   13.984   14.022   14.022
      14.263   14.470   14.592   14.592   17.943   17.973   19.040   23.489   23.548   23.548
      27.505   27.712   27.712   35.623
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="qespresso.bands">
           <module id="qespresso.bands">
              <scalar dataType="xsd:integer" dictRef="qex:nbnd">34</scalar>
              <scalar dataType="xsd:integer" dictRef="qex:nks">202</scalar>
              <matrix cols="3" dataType="xsd:double" dictRef="cc:coord" rows="5">0.000000 0.000000 0.000000 0.025000 -0.014434 0.020412 0.050000 -0.028868 0.040825 0.075000 -0.043301 0.061237 0.100000 -0.057735 0.081650</matrix>
              <matrix cols="34" dataType="xsd:double" dictRef="cc:eigen" rows="5">-91.768 -91.768 -91.731 -91.731 -91.731 -20.772 -4.487 -3.537 -2.948 -2.948 -2.948 8.069 8.069 8.069 11.211 11.211 11.211 14.016 14.016 14.016 14.245 14.640 14.640 14.640 17.785 17.785 18.624 23.759 23.759 23.759 27.589 27.589 27.589 34.835 -91.768 -91.768 -91.731 -91.731 -91.731 -20.771 -4.525 -3.542 -2.952 -2.952 -2.907 8.078 8.078 8.086 11.186 11.216 11.216 14.014 14.016 14.016 14.246 14.626 14.637 14.637 17.795 17.800 18.652 23.742 23.745 23.745 27.580 27.597 27.597 34.892 -91.768 -91.768 -91.731 -91.731 -91.731 -20.767 -4.630 -3.557 -2.963 -2.963 -2.792 8.107 8.107 8.137 11.112 11.231 11.231 14.007 14.018 14.018 14.249 14.589 14.628 14.628 17.825 17.841 18.734 23.691 23.704 23.704 27.555 27.622 27.622 35.056 -91.768 -91.768 -91.731 -91.731 -91.731 -20.759 -4.778 -3.581 -2.980 -2.980 -2.628 8.155 8.155 8.221 10.993 11.254 11.254 13.997 14.020 14.020 14.255 14.534 14.613 14.613 17.875 17.903 18.865 23.607 23.637 23.637 27.525 27.661 27.661 35.311 -91.768 -91.768 -91.731 -91.731 -91.731 -20.750 -4.950 -3.613 -3.004 -3.004 -2.433 8.222 8.222 8.336 10.833 11.285 11.285 13.984 14.022 14.022 14.263 14.470 14.592 14.592 17.943 17.973 19.040 23.489 23.548 23.548 27.505 27.712 27.712 35.623</matrix>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*.plot\snbnd.*" endPattern=".*" endOffset="0">    <record>.*nbnd\s*={I, qex:nbnd},\s*nks\s*={I, qex:nks}.*</record>
           </template>  <template pattern="\s{9,}\S+.*" endPattern="\s{9,}\S+.*" endPattern2="~" repeat="*">    <record id="kpoint">{3F,cc:coord}</record>    <record repeat="*" makeArray="true" id="energy">{1_10F,cc:eigen}</record>    <transform process="move" xpath=".//cml:array[@dictRef='qex:benergy']" to=".//cml:list[@cmlx:templateRef='kpoint']" />
           </template>  <transform process="createMatrix" xpath="." from=".//cml:array[@dictRef='cc:coord']" dictRef="cc:coord" />  <transform process="createMatrix" xpath="." from=".//cml:array[@dictRef='cc:eigen']" dictRef="cc:eigen" />  <transform process="pullup" xpath=".//cml:scalar" repeat="3" />  <transform process="pullup" xpath=".//cml:matrix" repeat="3" />  <transform process="delete" xpath=".//cml:module" />         
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
