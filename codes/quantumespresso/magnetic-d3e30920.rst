.. _magnetic-d3e30920:

magnetic
========

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
   | *source*                          | QuantumEspresso log               |
   +-----------------------------------+-----------------------------------+
   | id                                | magnetic                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Magnetic moment per site          |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\                                |
   |                                   | s+Magnetic\smoment\sper\ssite:.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | magnetic.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        Magnetic moment per site:
        atom:    1    charge:   12.3499    magn:    2.4587    constr:    0.0000
        atom:    2    charge:   12.3538    magn:   -2.4176    constr:    0.0000
        atom:    3    charge:   12.3424    magn:    3.5943    constr:    0.0000
        atom:    4    charge:   12.2145    magn:   -3.4843    constr:    0.0000
        atom:    5    charge:   12.2910    magn:    3.5614    constr:    0.0000
        atom:    6    charge:   12.3479    magn:   -3.5867    constr:    0.0000
        atom:    7    charge:   12.3243    magn:    3.5820    constr:    0.0000
        atom:    8    charge:   12.3418    magn:   -3.5882    constr:    0.0000
        atom:    9    charge:   12.3492    magn:    3.5872    constr:    0.0000
        atom:   10    charge:   12.2927    magn:   -3.5630    constr:    0.0000
        atom:   11    charge:   12.2160    magn:    3.4846    constr:    0.0000
        atom:   12    charge:   12.3399    magn:   -3.5876    constr:    0.0000
        atom:   13    charge:    1.9907    magn:    0.0354    constr:    0.0000
        atom:   14    charge:    2.0245    magn:    0.0565    constr:    0.0000
        atom:   15    charge:    1.9741    magn:   -0.0098    constr:    0.0000
        atom:   16    charge:    1.9740    magn:    0.0098    constr:    0.0000
        atom:   17    charge:    2.0016    magn:   -0.0488    constr:    0.0000
        atom:   18    charge:    2.0002    magn:    0.0602    constr:    0.0000
        atom:   19    charge:    1.9991    magn:   -0.0601    constr:    0.0000
        atom:   20    charge:    2.0027    magn:    0.0490    constr:    0.0000
        atom:   21    charge:    2.0286    magn:    0.0550    constr:    0.0000
        atom:   22    charge:    2.0558    magn:   -0.0007    constr:    0.0000
        atom:   23    charge:    2.0558    magn:    0.0007    constr:    0.0000
        atom:   24    charge:    2.0532    magn:    0.0047    constr:    0.0000
        atom:   25    charge:    2.0530    magn:    0.0031    constr:    0.0000
        atom:   26    charge:    2.0525    magn:    0.0015    constr:    0.0000
        atom:   27    charge:    2.0563    magn:    0.0000    constr:    0.0000
        atom:   28    charge:    2.0089    magn:   -0.0488    constr:    0.0000
        atom:   29    charge:    2.0182    magn:   -0.0590    constr:    0.0000
        atom:   30    charge:    2.0446    magn:   -0.0053    constr:    0.0000
        atom:   31    charge:    2.0537    magn:   -0.0040    constr:    0.0000
        atom:   32    charge:    2.0536    magn:   -0.0032    constr:    0.0000
        atom:   33    charge:    2.0108    magn:   -0.0470    constr:    0.0000
        atom:   34    charge:   12.1612    magn:    2.4351    constr:    0.0000
        atom:   35    charge:   12.3511    magn:   -2.4588    constr:    0.0000
        atom:   36    charge:   12.3460    magn:    3.5960    constr:    0.0000
        atom:   37    charge:   12.2555    magn:   -3.2375    constr:    0.0000
        atom:   38    charge:   12.2913    magn:    3.5626    constr:    0.0000
        atom:   39    charge:   12.3455    magn:   -3.5862    constr:    0.0000
        atom:   40    charge:   12.3406    magn:    3.5879    constr:    0.0000
        atom:   41    charge:   12.3324    magn:   -3.5848    constr:    0.0000
        atom:   42    charge:   12.3491    magn:    3.5880    constr:    0.0000
        atom:   43    charge:   12.2861    magn:   -3.5557    constr:    0.0000
        atom:   44    charge:   12.2677    magn:    3.3899    constr:    0.0000
        atom:   45    charge:   12.3430    magn:   -3.5945    constr:    0.0000
        atom:   46    charge:    2.0192    magn:    0.0590    constr:    0.0000
        atom:   47    charge:    2.0099    magn:    0.0488    constr:    0.0000
        atom:   48    charge:    1.9834    magn:    0.0166    constr:    0.0000
        atom:   49    charge:    1.9825    magn:   -0.0043    constr:    0.0000
        atom:   50    charge:    1.9603    magn:    0.0202    constr:    0.0000
        atom:   51    charge:    1.9819    magn:    0.0505    constr:    0.0000
        atom:   52    charge:    1.9813    magn:    0.0116    constr:    0.0000
        atom:   53    charge:    1.9936    magn:    0.0512    constr:    0.0000
        atom:   54    charge:    2.0168    magn:    0.0579    constr:    0.0000
        atom:   55    charge:    2.0555    magn:    0.0005    constr:    0.0000
        atom:   56    charge:    2.0564    magn:    0.0010    constr:    0.0000
        atom:   57    charge:    2.0495    magn:    0.0049    constr:    0.0000
        atom:   58    charge:    2.0484    magn:    0.0044    constr:    0.0000
        atom:   59    charge:    2.0497    magn:    0.0063    constr:    0.0000
        atom:   60    charge:    2.0556    magn:    0.0002    constr:    0.0000
        atom:   61    charge:    2.0151    magn:   -0.0603    constr:    0.0000
        atom:   62    charge:    2.0221    magn:   -0.0591    constr:    0.0000
        atom:   63    charge:    2.0538    magn:   -0.0047    constr:    0.0000
        atom:   64    charge:    2.0503    magn:   -0.0063    constr:    0.0000
        atom:   65    charge:    2.0430    magn:   -0.0055    constr:    0.0000
        atom:   66    charge:    2.0276    magn:   -0.0549    constr:    0.0000
        atom:   67    charge:   12.3526    magn:    2.4175    constr:    0.0000
        atom:   68    charge:   12.3477    magn:   -2.4301    constr:    0.0000
        atom:   69    charge:   12.3392    magn:    3.5874    constr:    0.0000
        atom:   70    charge:   12.2664    magn:   -3.3897    constr:    0.0000
        atom:   71    charge:   12.2917    magn:    3.5610    constr:    0.0000
        atom:   72    charge:   12.3477    magn:   -3.5876    constr:    0.0000
        atom:   73    charge:   12.3334    magn:    3.5849    constr:    0.0000
        atom:   74    charge:   12.3256    magn:   -3.5823    constr:    0.0000
        atom:   75    charge:   12.3469    magn:    3.5867    constr:    0.0000
        atom:   76    charge:   12.2924    magn:   -3.5618    constr:    0.0000
        atom:   77    charge:   12.2569    magn:    3.2378    constr:    0.0000
        atom:   78    charge:   12.3416    magn:   -3.5945    constr:    0.0000
        atom:   79    charge:    2.0322    magn:    0.0557    constr:    0.0000
        atom:   80    charge:    1.9947    magn:    0.0468    constr:    0.0000
        atom:   81    charge:    1.9813    magn:    0.0044    constr:    0.0000
        atom:   82    charge:    1.9846    magn:   -0.0165    constr:    0.0000
        atom:   83    charge:    1.9926    magn:   -0.0510    constr:    0.0000
        atom:   84    charge:    1.9825    magn:   -0.0115    constr:    0.0000
        atom:   85    charge:    1.9806    magn:   -0.0503    constr:    0.0000
        atom:   86    charge:    1.9616    magn:   -0.0201    constr:    0.0000
        atom:   87    charge:    2.0117    magn:    0.0470    constr:    0.0000
        atom:   88    charge:    2.0564    magn:   -0.0009    constr:    0.0000
        atom:   89    charge:    2.0555    magn:   -0.0005    constr:    0.0000
        atom:   90    charge:    2.0441    magn:    0.0052    constr:    0.0000
        atom:   91    charge:    2.0424    magn:    0.0055    constr:    0.0000
        atom:   92    charge:    2.0428    magn:    0.0051    constr:    0.0000
        atom:   93    charge:    2.0556    magn:   -0.0002    constr:    0.0000
        atom:   94    charge:    2.0235    magn:   -0.0565    constr:    0.0000
        atom:   95    charge:    1.9897    magn:   -0.0354    constr:    0.0000
        atom:   96    charge:    2.0508    magn:   -0.0037    constr:    0.0000
        atom:   97    charge:    2.0433    magn:   -0.0052    constr:    0.0000
        atom:   98    charge:    2.0490    magn:   -0.0044    constr:    0.0000
        atom:   99    charge:    2.0095    magn:   -0.0551    constr:    0.0000
        atom:  100    charge:   12.3465    magn:    2.4299    constr:    0.0000
        atom:  101    charge:   12.1623    magn:   -2.4356    constr:    0.0000
        atom:  102    charge:   12.3409    magn:    3.5943    constr:    0.0000
        atom:  103    charge:   12.2395    magn:   -3.3551    constr:    0.0000
        atom:  104    charge:   12.2848    magn:    3.5553    constr:    0.0000
        atom:  105    charge:   12.3467    magn:   -3.5876    constr:    0.0000
        atom:  106    charge:   12.3312    magn:    3.5845    constr:    0.0000
        atom:  107    charge:   12.3346    magn:   -3.5853    constr:    0.0000
        atom:  108    charge:   12.3481    magn:    3.5880    constr:    0.0000
        atom:  109    charge:   12.2931    magn:   -3.5614    constr:    0.0000
        atom:  110    charge:   12.2409    magn:    3.3555    constr:    0.0000
        atom:  111    charge:   12.3466    magn:   -3.5962    constr:    0.0000
        atom:  112    charge:    2.0231    magn:    0.0591    constr:    0.0000
        atom:  113    charge:    2.0162    magn:    0.0603    constr:    0.0000
        atom:  114    charge:    1.9828    magn:   -0.0040    constr:    0.0000
        atom:  115    charge:    1.9840    magn:    0.0041    constr:    0.0000
        atom:  116    charge:    1.9473    magn:   -0.0109    constr:    0.0000
        atom:  117    charge:    1.8704    magn:    0.0782    constr:    0.0000
        atom:  118    charge:    1.8692    magn:   -0.0779    constr:    0.0000
        atom:  119    charge:    1.9487    magn:    0.0110    constr:    0.0000
        atom:  120    charge:    2.0105    magn:    0.0552    constr:    0.0000
        atom:  121    charge:    2.0559    magn:   -0.0001    constr:    0.0000
        atom:  122    charge:    2.0559    magn:    0.0001    constr:    0.0000
        atom:  123    charge:    2.0502    magn:    0.0037    constr:    0.0000
        atom:  124    charge:    2.0489    magn:    0.0039    constr:    0.0000
        atom:  125    charge:    2.0532    magn:    0.0040    constr:    0.0000
        atom:  126    charge:    2.0552    magn:    0.0000    constr:    0.0000
        atom:  127    charge:    1.9937    magn:   -0.0468    constr:    0.0000
        atom:  128    charge:    2.0312    magn:   -0.0556    constr:    0.0000
        atom:  129    charge:    2.0500    magn:   -0.0049    constr:    0.0000
        atom:  130    charge:    2.0530    magn:   -0.0015    constr:    0.0000
        atom:  131    charge:    2.0494    magn:   -0.0040    constr:    0.0000
        atom:  132    charge:    2.0158    magn:   -0.0579    constr:    0.0000
        atom:  133    charge:    0.3597    magn:    0.0045    constr:    0.0000
        atom:  134    charge:    0.3605    magn:   -0.0045    constr:    0.0000
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="magnetic">
           <module cmlx:templateRef="magnetic">
               <array dataType="xsd:integer" dictRef="cc:serial" size="134">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79 80 81 82 83 84 85 86 87 88 89 90 91 92 93 94 95 96 97 98 99 100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117 118 119 120 121 122 123 124 125 126 127 128 129 130 131 132 133 134</array>
               <array dataType="xsd:double" dictRef="qex:charge" size="134">12.3499 12.3538 12.3424 12.2145 12.2910 12.3479 12.3243 12.3418 12.3492 12.2927 12.2160 12.3399 1.9907 2.0245 1.9741 1.9740 2.0016 2.0002 1.9991 2.0027 2.0286 2.0558 2.0558 2.0532 2.0530 2.0525 2.0563 2.0089 2.0182 2.0446 2.0537 2.0536 2.0108 12.1612 12.3511 12.3460 12.2555 12.2913 12.3455 12.3406 12.3324 12.3491 12.2861 12.2677 12.3430 2.0192 2.0099 1.9834 1.9825 1.9603 1.9819 1.9813 1.9936 2.0168 2.0555 2.0564 2.0495 2.0484 2.0497 2.0556 2.0151 2.0221 2.0538 2.0503 2.0430 2.0276 12.3526 12.3477 12.3392 12.2664 12.2917 12.3477 12.3334 12.3256 12.3469 12.2924 12.2569 12.3416 2.0322 1.9947 1.9813 1.9846 1.9926 1.9825 1.9806 1.9616 2.0117 2.0564 2.0555 2.0441 2.0424 2.0428 2.0556 2.0235 1.9897 2.0508 2.0433 2.0490 2.0095 12.3465 12.1623 12.3409 12.2395 12.2848 12.3467 12.3312 12.3346 12.3481 12.2931 12.2409 12.3466 2.0231 2.0162 1.9828 1.9840 1.9473 1.8704 1.8692 1.9487 2.0105 2.0559 2.0559 2.0502 2.0489 2.0532 2.0552 1.9937 2.0312 2.0500 2.0530 2.0494 2.0158 0.3597 0.3605</array>
               <array dataType="xsd:double" dictRef="qex:magn" size="134">2.4587 -2.4176 3.5943 -3.4843 3.5614 -3.5867 3.5820 -3.5882 3.5872 -3.5630 3.4846 -3.5876 0.0354 0.0565 -0.0098 0.0098 -0.0488 0.0602 -0.0601 0.0490 0.0550 -0.0007 0.0007 0.0047 0.0031 0.0015 0.0000 -0.0488 -0.0590 -0.0053 -0.0040 -0.0032 -0.0470 2.4351 -2.4588 3.5960 -3.2375 3.5626 -3.5862 3.5879 -3.5848 3.5880 -3.5557 3.3899 -3.5945 0.0590 0.0488 0.0166 -0.0043 0.0202 0.0505 0.0116 0.0512 0.0579 0.0005 0.0010 0.0049 0.0044 0.0063 0.0002 -0.0603 -0.0591 -0.0047 -0.0063 -0.0055 -0.0549 2.4175 -2.4301 3.5874 -3.3897 3.5610 -3.5876 3.5849 -3.5823 3.5867 -3.5618 3.2378 -3.5945 0.0557 0.0468 0.0044 -0.0165 -0.0510 -0.0115 -0.0503 -0.0201 0.0470 -0.0009 -0.0005 0.0052 0.0055 0.0051 -0.0002 -0.0565 -0.0354 -0.0037 -0.0052 -0.0044 -0.0551 2.4299 -2.4356 3.5943 -3.3551 3.5553 -3.5876 3.5845 -3.5853 3.5880 -3.5614 3.3555 -3.5962 0.0591 0.0603 -0.0040 0.0041 -0.0109 0.0782 -0.0779 0.0110 0.0552 -0.0001 0.0001 0.0037 0.0039 0.0040 0.0000 -0.0468 -0.0556 -0.0049 -0.0015 -0.0040 -0.0579 0.0045 -0.0045</array>
               <array dataType="xsd:double" dictRef="qex:constr" size="134">0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000 0.0000</array>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="1" />
   <record repeat="*" makeArray="true">\s+atom:{I,cc:serial}charge:{F,qex:charge}magn:{F,qex:magn}constr:{F,qex:constr}</record>
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="delete" xpath="./cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
