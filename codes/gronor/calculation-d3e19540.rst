.. _calculation-d3e19540:

calculation
===========

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
   | *source*                          | GronOR cml                        |
   +-----------------------------------+-----------------------------------+
   | id                                | calculation                       |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | calculation.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Hamiltonian Matrix

          |           D0D0                D0D1                D1D0                D1D1                S+T-                T-S+
   -------|------------------------------------------------------------------------------------------------------------------------
     D0D0 |    -2226.8707457990      211.0489728688      211.0489726228      -19.9629863553       -4.9871257809        4.9871257683
     D0D1 |      211.0489728688    -2226.7721867933      -20.0448405818      211.1018460174       40.0814367639       -6.4084081854
     D1D0 |      211.0489726228      -20.0448405818    -2226.7721872776      211.1018463086        6.4084081738      -40.0814367779
     D1D1 |      -19.9629863553      211.1018460174      211.1018463086    -2226.6715030441        2.0587190645       -2.0587190795
     S+T- |       -4.9871257809       40.0814367639        6.4084081738        2.0587190645    -2226.7015912963        0.2325834201
     T-S+ |        4.9871257683       -6.4084081854      -40.0814367779       -2.0587190795        0.2325834201    -2226.7015926766
     


    Overlap Matrix

          |           D0D0                D0D1                D1D0                D1D1                S+T-                T-S+
   -------|------------------------------------------------------------------------------------------------------------------------
     D0D0 |        1.0000000000       -0.0947756689       -0.0947756689        0.0089651567        0.0022392025       -0.0022392025
     D0D1 |       -0.0947756689        1.0000000000        0.0090019108       -0.0948032309       -0.0179976344        0.0028778301
     D1D0 |       -0.0947756689        0.0090019108        1.0000000000       -0.0948032309       -0.0028778301        0.0179976344
     D1D1 |        0.0089651567       -0.0948032309       -0.0948032309        1.0000000000       -0.0009243991        0.0009243991
     S+T- |        0.0022392025       -0.0179976344       -0.0028778301       -0.0009243991        1.0000000000       -0.0001044320
     T-S+ |       -0.0022392025        0.0028778301        0.0179976344        0.0009243991       -0.0001044320        1.0000000000
     


    Electronic Couplings (meV)

          |           D0D0                D0D1                D1D0                D1D1                S+T-                T-S+
   -------|------------------------------------------------------------------------------------------------------------------------
     D0D0 |
     D0D1 |       13.1473567327
     D1D0 |       13.1399717369        9.9090449490
     D1D1 |        9.9522490104       39.0116461388       39.0190115508
     S+T- |      -24.5083990510      148.0854100176        6.4686515963       10.1262509640
     T-S+ |       24.5080124776       -6.4689331970     -148.0853331109      -10.1266443217        1.2099100323
     


    NOCI energies and wave functions

             State:               1                   2                   3                   4                   5                   6
       Energy (Eh):     -2226.8711066453    -2226.7728615919    -2226.7718376522    -2226.7010876001    -2226.7010815801    -2226.6706797744
     Relative (eV):         0.0000000000        2.6733854459        2.7012482789        4.6264562467        4.6266200591        5.4538957532

       MEBF: D0D0          -1.0062136649        0.0000165534        0.0755053546        0.0003401631       -0.0000393956       -0.0065507246
             D0D1          -0.0422217428       -0.7079101215        0.7101668274       -0.0549249107        0.0639748192       -0.0647338595
             D1D0          -0.0422244929        0.7082578900        0.7098194968       -0.0680962015       -0.0497249593       -0.0647364306
             D1D1           0.0009837177        0.0000097006        0.0469737914        0.0310762314       -0.0035998672       -1.0074977322
             S+T-          -0.0035025739        0.0462487756       -0.0492457436       -0.6190941709        0.7821453429       -0.0271046110
             T-S+           0.0035024695        0.0462733969        0.0492238937        0.7815064035        0.6199004383        0.0271044646
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="noci">    
           <module dictRef="cc:calculation" id="NOCI">
               <module dictRef="gr:matrices" id="normalized">
                   <propertyList>
                       <property dictRef="gr:hamiltonian" id="standard">
                             <matrix dataType="xsd:double" units="nonsi:hartree" delimiter="|" columns="6" rows="6">-2226.8707457990|211.0489728688|211.0489726228|-19.9629863553|-4.9871257809|4.9871257683|211.0489728688|-2226.7721867933|-20.0448405818|211.1018460174|40.0814367639|-6.4084081854|211.0489726228|-20.0448405818|-2226.7721872776|211.1018463086|6.4084081738|-40.0814367779|-19.9629863553|211.1018460174|211.1018463086|-2226.6715030441|2.0587190645|-2.0587190795|-4.9871257809|40.0814367639|6.4084081738|2.0587190645|-2226.7015912963|0.2325834201|4.9871257683|-6.4084081854|-40.0814367779|-2.0587190795|0.2325834201|-2226.7015926766</matrix>
                       </property>
                       <property dictRef="gr:overlap">
                             <matrix dataType="xsd:double" dictRef="gr:overlap" delimiter="|" columns="6" rows="6">1.0000000000|-0.0947756689|-0.0947756689|0.0089651567|0.0022392025|-0.0022392025|-0.0947756689|1.0000000000|0.0090019108|-0.0948032309|-0.0179976344|0.0028778301|-0.0947756689|0.0090019108|1.0000000000|-0.0948032309|-0.0028778301|0.0179976344|0.0089651567|-0.0948032309|-0.0948032309|1.0000000000|-0.0009243991|0.0009243991|0.0022392025|-0.0179976344|-0.0028778301|-0.0009243991|1.0000000000|-0.0001044320|-0.0022392025|0.0028778301|0.0179976344|0.0009243991|-0.0001044320|1.0000000000</matrix>
                       </property>
                   </propertyList>
               </module>
               <module dictRef="gr:nociStates">
                   <module dictRef="gr:nociroot">
                       <propertyList>
                           <property dictRef="gr:rootNumber">
                               <scalar dataType="xsd:integer">1</scalar>
                           </property>
                           <property dictRef="gr:nociEnergy" id="standard">
                               <scalar dataType="xsd:double" units="nonsi:hartree">-2226.87110665</scalar>
                           </property>
                           <property dictRef="gr:nociRelEnergy" id="standard">
                               <scalar dataType="xsd:double" dictRef="gr:nociRelEnergy" id="standard" units="nonsi:eV">0.0000</scalar>
                           </property>
                           <property dictRef="gr:mebfCoeff" id="standard">
                               <array dataType="xsd:double" dictRef="gr:mebfCoeff" id="standard" delimiter="|" size="6">-1.0062136649|0.0000165534|0.0755053546|0.0003401631|-0.0000393956|-0.0065507246</array>
                           </property>
                       </propertyList>
                   </module>
                   <module dictRef="gr:nociroot">
                       <propertyList>
                           <property dictRef="gr:rootNumber">
                               <scalar dataType="xsd:integer">2</scalar>
                           </property>
                           <property dictRef="gr:nociEnergy" id="standard">
                               <scalar dataType="xsd:double" units="nonsi:hartree">-2226.77286159</scalar>
                           </property>
                           <property dictRef="gr:nociRelEnergy" id="standard">
                               <scalar dataType="xsd:double" dictRef="gr:nociRelEnergy" id="standard" units="nonsi:eV">2.6734</scalar>
                           </property>
                           <property dictRef="gr:mebfCoeff" id="standard">
                               <array dataType="xsd:double" dictRef="gr:mebfCoeff" id="standard" delimiter="|" size="6">-0.0422217428|-0.7079101215|0.7101668274|-0.0549249107|0.0639748192|-0.0647338595</array>
                           </property>
                       </propertyList>
                   </module>
                   <module dictRef="gr:nociroot">
                       <propertyList>
                           <property dictRef="gr:rootNumber">
                               <scalar dataType="xsd:integer">3</scalar>
                           </property>
                           <property dictRef="gr:nociEnergy" id="standard">
                               <scalar dataType="xsd:double" units="nonsi:hartree">-2226.77183765</scalar>
                           </property>
                           <property dictRef="gr:nociRelEnergy" id="standard">
                               <scalar dataType="xsd:double" dictRef="gr:nociRelEnergy" id="standard" units="nonsi:eV">2.7012</scalar>
                           </property>
                           <property dictRef="gr:mebfCoeff" id="standard">
                               <array dataType="xsd:double" dictRef="gr:mebfCoeff" id="standard" delimiter="|" size="6">-0.0422244929|0.7082578900|0.7098194968|-0.0680962015|-0.0497249593|-0.0647364306</array>
                           </property>
                       </propertyList>
                   </module>
                   <module dictRef="gr:nociroot">
                       <propertyList>
                           <property dictRef="gr:rootNumber">
                               <scalar dataType="xsd:integer">4</scalar>
                           </property>
                           <property dictRef="gr:nociEnergy" id="standard">
                               <scalar dataType="xsd:double" units="nonsi:hartree">-2226.70108760</scalar>
                           </property>
                           <property dictRef="gr:nociRelEnergy" id="standard">
                               <scalar dataType="xsd:double" dictRef="gr:nociRelEnergy" id="standard" units="nonsi:eV">4.6265</scalar>
                           </property>
                           <property dictRef="gr:mebfCoeff" id="standard">
                               <array dataType="xsd:double" dictRef="gr:mebfCoeff" id="standard" delimiter="|" size="6">0.0009837177|0.0000097006|0.0469737914|0.0310762314|-0.0035998672|-1.0074977322</array>
                           </property>
                       </propertyList>
                   </module>
                   <module dictRef="gr:nociroot">
                       <propertyList>
                           <property dictRef="gr:rootNumber">
                               <scalar dataType="xsd:integer">5</scalar>
                           </property>
                           <property dictRef="gr:nociEnergy" id="standard">
                               <scalar dataType="xsd:double" units="nonsi:hartree">-2226.70108158</scalar>
                           </property>
                           <property dictRef="gr:nociRelEnergy" id="standard">
                               <scalar dataType="xsd:double" dictRef="gr:nociRelEnergy" id="standard" units="nonsi:eV">4.6266</scalar>
                           </property>
                           <property dictRef="gr:mebfCoeff" id="standard">
                               <array dataType="xsd:double" dictRef="gr:mebfCoeff" id="standard" delimiter="|" size="6">-0.0035025739|0.0462487756|-0.0492457436|-0.6190941709|0.7821453429|-0.0271046110</array>
                           </property>
                       </propertyList>
                   </module>
                   <module dictRef="gr:nociroot">
                       <propertyList>
                           <property dictRef="gr:rootNumber">
                               <scalar dataType="xsd:integer">6</scalar>
                           </property>
                           <property dictRef="gr:nociEnergy" id="standard">
                               <scalar dataType="xsd:double" units="nonsi:hartree">-2226.67067977</scalar>
                           </property>
                           <property dictRef="gr:nociRelEnergy" id="standard">
                               <scalar dataType="xsd:double" dictRef="gr:nociRelEnergy" id="standard" units="nonsi:eV">5.4539</scalar>
                           </property>
                           <property dictRef="gr:mebfCoeff" id="standard">
                               <array dataType="xsd:double" dictRef="gr:mebfCoeff" id="standard" delimiter="|" size="6">0.0035024695|0.0462733969|0.0492238937|0.7815064035|0.6199004383|0.0271044646</array>
                           </property>
                       </propertyList>
                   </module>
               </module>
               <module dictRef="gr:elCoupling">
                   <propertyList>
                       <property dictRef="gr:mebfCoupling" id="standard">
                             <matrix dataType="xsd:double" units="nonsi:meV" delimiter="|" columns="6" rows="6">0.0000|0.0000|0.0000|0.0000|0.0000|0.0000|13.1474|0.0000|0.0000|0.0000|0.0000|0.0000|13.1400|9.9090|0.0000|0.0000|0.0000|0.0000|9.9522|39.0116|39.0190|0.0000|0.0000|0.0000|-24.5084|148.0854|6.4687|10.1263|0.0000|0.0000|24.5080|-6.4689|-148.0853|-10.1266|1.2099|0.0000</matrix>
                       </property>
                   </propertyList>
               </module>
           </module>         
       </comment>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
