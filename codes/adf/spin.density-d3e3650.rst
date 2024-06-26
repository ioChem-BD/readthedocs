.. _spin.density-d3e3650:

spin.density
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
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | spin.density                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | MDC spin density                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s+MDC&#92;sspin&#92;sdensity&#92;s&#92;(spinA&#92;s&#92;-&#92;sspinB&#92;).\*                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;d+&#92;s+[a-zA-Z]+.*$&#92;s\*                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | multipole/spin.density.xml                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    -------------------------------- 
    MDC spin density (spinA - spinB)
    -------------------------------- 

    With an UNRESTRICTED calculation, there are two sets of atomic multipoles,
    one for the Alpha-electrons, and one for the Beta-electrons. For both sets,
    we get atomic charges. Reported here are the differences, which usually are
    regarded as spin densities.

           Atom    Level:     MDC-m        MDC-d        MDC-q
    ---------------------------------------------------------
        1     W           -0.095556    -0.079659    -0.078800
        2     W           -0.095556    -0.079659    -0.078800
        3     W           -0.118334    -0.096979    -0.097869
        4     W           -0.118334    -0.096979    -0.097869
        5     W           -0.095556    -0.079659    -0.078800
        6     W           -0.095556    -0.079659    -0.078800
        7     W           -0.118334    -0.096979    -0.097869
        8     W           -0.118334    -0.096979    -0.097869
        9     V            0.026743     0.020389     0.023550
       10     W            0.017092     0.011044     0.014337
       11     O            0.001171     0.001927     0.004075
       12     O            0.000886     0.000746     0.006227
       13     O            0.009845     0.003208    -0.000170
       14     O            0.009845     0.003208    -0.000170
       15     O            0.009845     0.003208    -0.000170
       16     O            0.009845     0.003208    -0.000170
       17     O            0.018074     0.010174     0.005147
       18     O            0.018074     0.010174     0.005147
       19     O            0.018074     0.010174     0.005147
       20     O            0.018074     0.010174     0.005147
       21     O           -0.065793    -0.054650    -0.055226
       22     O           -0.065793    -0.054650    -0.055226
       23     O           -0.045436    -0.040162    -0.039869
       24     O           -0.045436    -0.040162    -0.039869
       25     O            0.018945    -0.002407    -0.000652
       26     O            0.018945    -0.002407    -0.000652
       27     O           -0.065793    -0.054650    -0.055226
       28     O           -0.065793    -0.054650    -0.055226
       29     O           -0.045436    -0.040162    -0.039869
       30     O           -0.045436    -0.040162    -0.039869
       31     O            0.018945    -0.002407    -0.000652
       32     O            0.018945    -0.002407    -0.000652
       33     O            0.007884     0.001339     0.001951
       34     O            0.007884     0.001339     0.001951
       35     O            0.008961     0.001586     0.003487
       36     O            0.008961     0.001586     0.003487
       37     O           -0.000938    -0.002912    -0.000585
       38     O            0.000687    -0.000996     0.000401
       39     O            0.007884     0.001339     0.001951
       40     O            0.007884     0.001339     0.001951
       41     O            0.008961     0.001586     0.003487
       42     O            0.008961     0.001586     0.003487

       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="spin.density">        
           <module cmlx:lineCount="53" cmlx:templateRef="spin.density">
               <list cmlx:lineCount="42" cmlx:templateRef="spinDensity">
                   <array dataType="xsd:integer" dictRef="cc:serial" size="42">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42</array>
                   <array dataType="xsd:string" dictRef="cc:elementType" size="42">W W W W W W W W V W O O O O O O O O O O O O O O O O O O O O O O O O O O O O O O O O</array>
                   <array dataType="xsd:double" dictRef="a:mdcm" size="42">-0.095556 -0.095556 -0.118334 -0.118334 -0.095556 -0.095556 -0.118334 -0.118334 0.026743 0.017092 0.001171 8.86E-4 0.009845 0.009845 0.009845 0.009845 0.018074 0.018074 0.018074 0.018074 -0.065793 -0.065793 -0.045436 -0.045436 0.018945 0.018945 -0.065793 -0.065793 -0.045436 -0.045436 0.018945 0.018945 0.007884 0.007884 0.008961 0.008961 -9.38E-4 6.87E-4 0.007884 0.007884 0.008961 0.008961</array>
                   <array dataType="xsd:double" dictRef="a:mdcd" size="42">-0.079659 -0.079659 -0.096979 -0.096979 -0.079659 -0.079659 -0.096979 -0.096979 0.020389 0.011044 0.001927 7.46E-4 0.003208 0.003208 0.003208 0.003208 0.010174 0.010174 0.010174 0.010174 -0.05465 -0.05465 -0.040162 -0.040162 -0.002407 -0.002407 -0.05465 -0.05465 -0.040162 -0.040162 -0.002407 -0.002407 0.001339 0.001339 0.001586 0.001586 -0.002912 -9.96E-4 0.001339 0.001339 0.001586 0.001586</array>
                   <array dataType="xsd:double" dictRef="a:mdcq" size="42">-0.0788 -0.0788 -0.097869 -0.097869 -0.0788 -0.0788 -0.097869 -0.097869 0.02355 0.014337 0.004075 0.006227 -1.7E-4 -1.7E-4 -1.7E-4 -1.7E-4 0.005147 0.005147 0.005147 0.005147 -0.055226 -0.055226 -0.039869 -0.039869 -6.52E-4 -6.52E-4 -0.055226 -0.055226 -0.039869 -0.039869 -6.52E-4 -6.52E-4 0.001951 0.001951 0.003487 0.003487 -5.85E-4 4.01E-4 0.001951 0.001951 0.003487 0.003487</array>
               </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*Atom\s+Level.*" endPattern="~">    <record repeat="2" />    <record id="spinDensity" repeat="*" makeArray="true">{I,cc:serial}{A,cc:elementType}{F,a:mdcm}{F,a:mdcd}{F,a:mdcq}</record>
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='spinDensity']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
