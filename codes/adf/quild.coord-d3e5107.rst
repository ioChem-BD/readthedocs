.. _quild.coord-d3e5107:

quild.coord
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
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | quild.coord                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Quild module initial coordinates                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Atomic&#92;scoordinates&#92;s\*                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*&#92;d+&#92;s*$&#92;s\*                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | quild/quild.coord.xml                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       Atomic coordinates

    atom       nr    x (Bohrs)   y (Bohrs)   z (Bohrs)       x (angs)    y (angs)    z (angs)
   --------------------------------------------------------------------------------------------
    C           1     -4.35644    -4.32382     2.48365       -2.30533    -2.28807     1.31429
    C           2     -5.56237    -5.32601     0.18408       -2.94348    -2.81840     0.09741
    C           3     -7.06088    -2.91568    -0.71245       -3.73646    -1.54291    -0.37701
    C           4     -7.55061    -1.29962     1.88992       -3.99561    -0.68773     1.00010
    C           5     -5.22954    -2.06590     3.35741       -2.76735    -1.09323     1.77667
    C           6     -1.87045    -5.13748     2.85502       -0.98980    -2.71864     1.51081
    C           7     -1.04042    -6.39232     0.64033       -0.55057    -3.38267     0.33885
    C           8     -3.14831    -6.30129    -1.37538       -1.66601    -3.33450    -0.72782
       
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="quild.coord">
            <module cmlx:lineCount="80" cmlx:templateRef="quild.coord">
               <molecule id="quild.coord">
                <atomArray>
                 <atom id="a1" elementType="C" x3="-2.30533" y3="-2.28807" z3="1.31429">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a2" elementType="C" x3="-2.94348" y3="-2.8184" z3="0.09741">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">2</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a3" elementType="C" x3="-3.73646" y3="-1.54291" z3="-0.37701">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">3</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a4" elementType="C" x3="-3.99561" y3="-0.68773" z3="1.0001">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">4</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a5" elementType="C" x3="-2.76735" y3="-1.09323" z3="1.77667">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">5</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a6" elementType="C" x3="-0.9898" y3="-2.71864" z3="1.51081">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">6</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a7" elementType="C" x3="-0.55057" y3="-3.38267" z3="0.33885">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">7</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                 <atom id="a8" elementType="C" x3="-1.66601" y3="-3.3345" z3="-0.72782">
                  <scalar dataType="xsd:integer" dictRef="cc:serial">8</scalar>
                  <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                 </atom>
                </atomArray>
                <formula formalCharge="0" concise="C 8">
                 <atomArray elementType="C" count="8.0" />
                </formula>
                <bondArray>
                 <bond atomRefs2="a1 a2" id="a1_a2" order="S" />
                 <bond atomRefs2="a1 a5" id="a1_a5" order="S" />
                 <bond atomRefs2="a1 a6" id="a1_a6" order="S" />
                 <bond atomRefs2="a2 a3" id="a2_a3" order="S" />
                 <bond atomRefs2="a2 a8" id="a2_a8" order="S" />           
                </bondArray>
                <property dictRef="cml:molmass">
                 <scalar dataType="xsd:double" units="unit:dalton">1241.0054</scalar>
                </property>
               </molecule>
              </module>
       
       
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <record repeat="4" />
   <record id="atom" repeat="*" makeArray="true">{A,cc:elementType}{I,cc:serial}\s+\S+\s+\S+\s+\S+\s+{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>
   <transform process="createMolecule" id="quild.coord" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:array" />
   <transform process="pullup" xpath=".//cml:molecule" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:molecule[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
