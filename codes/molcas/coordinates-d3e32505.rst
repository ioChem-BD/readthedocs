.. _coordinates-d3e32505:

coordinates
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
   | id                                                                                                                         | coordinates                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Cartesian coordinates                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s+&                                                                                                                   |
   |                                                                                                                            | #92;*{20,}&#92;s*$&#92;s+&#92;*&#92;*&#92;*&#92;*&#92;s+Cartesian&#92;sCoordinates&#92;s&#92;/&#92;sBohr,&#92;sAngstrom.\* |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*Cartesian&#92;scoordinates&#92;sin&#92;sAngstrom:&#92;s\*                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*[0-9]&#92;s*$&#92;s\*                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | .*[0-9]&#92;s*$&#92;s*-{20,}&#92;s\*                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/coordinates.xml                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                       ************************************************ 
                       **** Cartesian Coordinates / Bohr, Angstrom **** 
                       ************************************************ 
    
        Center  Label                x              y              z                     x              y              z
           1      N1              -0.000329       0.000000      -8.480849             -0.000174       0.000000      -4.487872
           2      C2               0.000056       0.000000       1.868456              0.000030       0.000000       0.988744
           3      C3               0.000079       2.304225       0.461974              0.000042       1.219344       0.244466
           4      C4               0.000093       2.296046      -2.173609              0.000049       1.215015      -1.150224
           5      C5               0.000078      -2.304225       0.461974              0.000041      -1.219344       0.244466
           6      C6               0.000095      -2.296046      -2.173609              0.000050      -1.215015      -1.150224
           7      C7               0.000061       0.000000      -3.552689              0.000032       0.000000      -1.880002
           8      C8              -0.000120       0.000000      -6.258363             -0.000064       0.000000      -3.311783
           9      H9               0.000105       4.105435      -3.202743              0.000056       2.172503      -1.694818
          10      H10              0.000042       4.135857       1.440732              0.000022       2.188601       0.762403
          11      H11              0.000115      -4.105435      -3.202743              0.000061      -2.172503      -1.694818
          12      H12              0.000032      -4.135857       1.440732              0.000017      -2.188601       0.762403
          13      N13              0.000007       0.000000       4.892017              0.000004       0.000000       2.588744
          14      C14              1.309504      -2.268145       5.818004              0.692960      -1.200251       3.078755
          15      H15              1.669031      -2.077449       7.798631              0.883213      -1.099338       4.126858
          16      H16              0.150759      -3.893763       5.496772              0.079778      -2.060490       2.908767
          17      H17              3.061892      -2.484185       4.832624              1.620284      -1.314574       2.557314
          18      C18              1.309506       2.268143       5.818004              0.692961       1.200250       3.078755
          19      H19              0.179321       3.901209       5.438146              0.094893       2.064431       2.877743
          20      H20              1.611150       2.105902       7.810791              0.852584       1.114395       4.133292
          21      H21              3.091220       2.448281       4.879091              1.635803       1.295574       2.581904

       

.. container:: formalpara-title

   **Input**

::

         Cartesian coordinates in Angstrom:
         -----------------------------------------------------
         No.  Label        X            Y            Z        
         -----------------------------------------------------
          1   N1        -0.00017425   0.00000000  -4.48787180
          2   C2         0.00002955   0.00000000   0.98874410
          3   C3         0.00004205   1.21934360   0.24446610
          4   C4         0.00004915   1.21501530  -1.15022430
          5   C5         0.00004115  -1.21934360   0.24446610
          6   C6         0.00005015  -1.21501530  -1.15022430
          7   C7         0.00003235   0.00000000  -1.88000200
          8   C8        -0.00006365   0.00000000  -3.31178300
          9   H9         0.00005565   2.17250290  -1.69481840
         10   H10        0.00002205   2.18860110   0.76240260
         11   H11        0.00006095  -2.17250290  -1.69481840
         12   H12        0.00001705  -2.18860110   0.76240260
         13   N13        0.00000365   0.00000000   2.58874410
         14   C14        0.69295969  -1.20025054   3.07875488
         15   H15        0.88321339  -1.09933846   4.12685806
         16   H16        0.07977834  -2.06049040   2.90876657
         17   H17        1.62028373  -1.31457415   2.55731434
         18   C18        0.69296088   1.20024985   3.07875488
         19   H19        0.09489284   2.06443086   2.87774294
         20   H20        0.85258368   1.11439520   4.13329248
         21   H21        1.63580339   1.29557437   2.58190356
         ----------------------------------------------------- 
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="coordinates">
           <module cmlx:templateRef="coordinates">
               <list id="coordinates">
                   <scalar dataType="xsd:string" dictRef="x:label">N1</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C2</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C3</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C4</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C5</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C6</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C7</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C8</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H9</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H10</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H11</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H12</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">N13</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C14</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H15</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H16</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H17</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C18</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H19</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H20</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H21</scalar>
                   <array dataType="xsd:double" dictRef="cc:x3" size="21">-0.000174 0.000030 0.000042 0.000049 0.000041 0.000050 0.000032 -0.000064 0.000056 0.000022 0.000061 0.000017 0.000004 0.692960 0.883213 0.079778 1.620284 0.692961 0.094893 0.852584 1.635803</array>
                   <array dataType="xsd:double" dictRef="cc:y3" size="21">0.000000 0.000000 1.219344 1.215015 -1.219344 -1.215015 0.000000 0.000000 2.172503 2.188601 -2.172503 -2.188601 0.000000 -1.200251 -1.099338 -2.060490 -1.314574 1.200250 2.064431 1.114395 1.295574</array>
                   <array dataType="xsd:double" dictRef="cc:z3" size="21">-4.487872 0.988744 0.244466 -1.150224 0.244466 -1.150224 -1.880002 -3.311783 -1.694818 0.762403 -1.694818 0.762403 2.588744 3.078755 4.126858 2.908767 2.557314 3.078755 2.877743 4.133292 2.581904</array>
               </list>
            </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="coordinates2">
            <module cmlx:templateRef="coordinates">
               <list id="coordinates">
                   <scalar dataType="xsd:string" dictRef="x:label">N1</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C2</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C3</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C4</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C5</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C6</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C7</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C8</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H9</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H10</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H11</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H12</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">N13</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C14</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H15</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H16</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H17</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">C18</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H19</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H20</scalar>
                   <scalar dataType="xsd:string" dictRef="x:label">H21</scalar>
                   <array dataType="xsd:double" dictRef="cc:x3" size="21">-0.00017425 0.00002955 0.00004205 0.00004915 0.00004115 0.00005015 0.00003235 -0.00006365 0.00005565 0.00002205 0.00006095 0.00001705 0.00000365 0.69295969 0.88321339 0.07977834 1.62028373 0.69296088 0.09489284 0.85258368 1.63580339</array>
                   <array dataType="xsd:double" dictRef="cc:y3" size="21">0.00000000 0.00000000 1.21934360 1.21501530 -1.21934360 -1.21501530 0.00000000 0.00000000 2.17250290 2.18860110 -2.17250290 -2.18860110 0.00000000 -1.20025054 -1.09933846 -2.06049040 -1.31457415 1.20024985 2.06443086 1.11439520 1.29557437</array>
                   <array dataType="xsd:double" dictRef="cc:z3" size="21">-4.48787180 0.98874410 0.24446610 -1.15022430 0.24446610 -1.15022430 -1.88000200 -3.31178300 -1.69481840 0.76240260 -1.69481840 0.76240260 2.58874410 3.07875488 4.12685806 2.90876657 2.55731434 3.07875488 2.87774294 4.13329248 2.58190356</array>
               </list>               
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s+\*{20,}\s*$\s+\*\*\*\*\s+Cartesian\sCoordinates\s\/\sBohr,\sAngstrom.*" endPattern="~">    <record repeat="5" />    <record repeat="*">{A,cc:serial}{A,x:label}\s+\S+\s+\S+\s+\S+\s+{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>                        
           </template>  <template pattern="\s*Cartesian\scoordinates\sin\sAngstrom:\s*" endPattern="~">    <record repeat="4" />    <record repeat="*">{I,cc:serial}{A,x:label}{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>                              
           </template>               
       </templateList>
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:x3']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:y3']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:z3']" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='cc:serial']" />
   <transform process="addChild" xpath="." elementName="cml:list" id="coordinates" />
   <transform process="move" xpath=".//cml:scalar" to=".//cml:list[@id='coordinates']" />
   <transform process="move" xpath=".//cml:array" to=".//cml:list[@id='coordinates']" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
