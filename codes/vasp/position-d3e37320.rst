.. _position-d3e37320:

position
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
   | *source*                          | VASP outcar                       |
   +-----------------------------------+-----------------------------------+
   | id                                | position                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Positions in fractional           |
   |                                   | coordinates                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*posit                         |
   |                                   | ion\sof\sions\sin\sfractional\sco |
   |                                   | ordinates\s\(direct\slattice\).\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | position/positions.xml            |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    position of ions in fractional coordinates (direct lattice) 
      0.16666500  0.33333501  0.03459000
      0.16666500  0.83333501  0.03459000
      0.66666500  0.33333501  0.03459000
      0.66666500  0.83333501  0.03459000
      0.33344208  0.16678690  0.17241022
      0.33370785  0.66723260  0.17236879
      0.83356269  0.16703726  0.17234065
      0.83363629  0.66717655  0.17245114
      0.00055589  0.00179727  0.31021653
      0.00128051  0.50131695  0.30977472
      0.50122386  0.00133435  0.31014414
      0.50020908  0.50086165  0.30991796
      0.00000000  0.00000000  0.00000000
      0.00000000  0.50000000  0.00000000
      0.50000000  0.00000000  0.00000000
      0.50000000  0.50000000  0.00000000
      0.33333501  0.16666500  0.06918000
      0.33333501  0.66666500  0.06918000
      0.83333501  0.16666500  0.06918000
      0.83333501  0.66666500  0.06918000
      0.16666500  0.33333501  0.13837001
      0.16666500  0.83333501  0.13837001
      0.66666500  0.33333501  0.13837001
      0.66666500  0.83333501  0.13837001
      0.00078633  0.00081280  0.20583181
      0.00070507  0.50087513  0.20577521
      0.50008487  0.00078081  0.20576536
      0.49993408  0.49978326  0.20584340
      0.33351324  0.16671123  0.27905870
      0.33503831  0.66883301  0.27846615
      0.83360028  0.16754563  0.27824211
      0.83392651  0.66832458  0.27853659
      0.16420118  0.33792779  0.36587087
      0.16720140  0.83425831  0.36977061
      0.67367077  0.33715788  0.36672624
      0.66731975  0.83561243  0.36833882
      0.34790048  0.20014118  0.47522548
      0.40274117  0.38177333  0.48995583
      0.54131862  0.58946666  0.50116705
      0.16783755  0.09136909  0.47266040
      0.18523424  0.33429035  0.40778406
      0.10603102  0.24227062  0.48043436
      0.66232245  0.34363224  0.40869442
      0.15082389  0.80250040  0.41108887
      0.68703805  0.85873047  0.41002896
      0.43618283  0.13522132  0.46102313
      0.69211950  0.63331329  0.48545774
      0.49407341  0.68433687  0.47869690
      0.55148637  0.62329277  0.54801584
    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="position">
           <module cmlx:templateRef="position">
               <atom id="atom" xFract="0.16666500" yFract="0.33333501" zFract="0.03459000" />
               <atom id="atom" xFract="0.16666500" yFract="0.83333501" zFract="0.03459000" />
               <atom id="atom" xFract="0.66666500" yFract="0.33333501" zFract="0.03459000" />
               <atom id="atom" xFract="0.66666500" yFract="0.83333501" zFract="0.03459000" />
               <atom id="atom" xFract="0.33344208" yFract="0.16678690" zFract="0.17241022" />
               <atom id="atom" xFract="0.33370785" yFract="0.66723260" zFract="0.17236879" />
               <atom id="atom" xFract="0.83356269" yFract="0.16703726" zFract="0.17234065" />
               <atom id="atom" xFract="0.83363629" yFract="0.66717655" zFract="0.17245114" />
               <atom id="atom" xFract="0.00055589" yFract="0.00179727" zFract="0.31021653" />
               <atom id="atom" xFract="0.00128051" yFract="0.50131695" zFract="0.30977472" />
               <atom id="atom" xFract="0.50122386" yFract="0.00133435" zFract="0.31014414" />
               <atom id="atom" xFract="0.50020908" yFract="0.50086165" zFract="0.30991796" />
               <atom id="atom" xFract="0.00000000" yFract="0.00000000" zFract="0.00000000" />
               <atom id="atom" xFract="0.00000000" yFract="0.50000000" zFract="0.00000000" />
               <atom id="atom" xFract="0.50000000" yFract="0.00000000" zFract="0.00000000" />
               <atom id="atom" xFract="0.50000000" yFract="0.50000000" zFract="0.00000000" />
               <atom id="atom" xFract="0.33333501" yFract="0.16666500" zFract="0.06918000" />
               <atom id="atom" xFract="0.33333501" yFract="0.66666500" zFract="0.06918000" />
               <atom id="atom" xFract="0.83333501" yFract="0.16666500" zFract="0.06918000" />
               <atom id="atom" xFract="0.83333501" yFract="0.66666500" zFract="0.06918000" />
               <atom id="atom" xFract="0.16666500" yFract="0.33333501" zFract="0.13837001" />
               <atom id="atom" xFract="0.16666500" yFract="0.83333501" zFract="0.13837001" />
               <atom id="atom" xFract="0.66666500" yFract="0.33333501" zFract="0.13837001" />
               <atom id="atom" xFract="0.66666500" yFract="0.83333501" zFract="0.13837001" />
               <atom id="atom" xFract="0.00078633" yFract="0.00081280" zFract="0.20583181" />
               <atom id="atom" xFract="0.00070507" yFract="0.50087513" zFract="0.20577521" />
               <atom id="atom" xFract="0.50008487" yFract="0.00078081" zFract="0.20576536" />
               <atom id="atom" xFract="0.49993408" yFract="0.49978326" zFract="0.20584340" />
               <atom id="atom" xFract="0.33351324" yFract="0.16671123" zFract="0.27905870" />
               <atom id="atom" xFract="0.33503831" yFract="0.66883301" zFract="0.27846615" />
               <atom id="atom" xFract="0.83360028" yFract="0.16754563" zFract="0.27824211" />
               <atom id="atom" xFract="0.83392651" yFract="0.66832458" zFract="0.27853659" />
               <atom id="atom" xFract="0.16420118" yFract="0.33792779" zFract="0.36587087" />
               <atom id="atom" xFract="0.16720140" yFract="0.83425831" zFract="0.36977061" />
               <atom id="atom" xFract="0.67367077" yFract="0.33715788" zFract="0.36672624" />
               <atom id="atom" xFract="0.66731975" yFract="0.83561243" zFract="0.36833882" />
               <atom id="atom" xFract="0.34790048" yFract="0.20014118" zFract="0.47522548" />
               <atom id="atom" xFract="0.40274117" yFract="0.38177333" zFract="0.48995583" />
               <atom id="atom" xFract="0.54131862" yFract="0.58946666" zFract="0.50116705" />
               <atom id="atom" xFract="0.16783755" yFract="0.09136909" zFract="0.47266040" />
               <atom id="atom" xFract="0.18523424" yFract="0.33429035" zFract="0.40778406" />
               <atom id="atom" xFract="0.10603102" yFract="0.24227062" zFract="0.48043436" />
               <atom id="atom" xFract="0.66232245" yFract="0.34363224" zFract="0.40869442" />
               <atom id="atom" xFract="0.15082389" yFract="0.80250040" zFract="0.41108887" />
               <atom id="atom" xFract="0.68703805" yFract="0.85873047" zFract="0.41002896" />
               <atom id="atom" xFract="0.43618283" yFract="0.13522132" zFract="0.46102313" />
               <atom id="atom" xFract="0.69211950" yFract="0.63331329" zFract="0.48545774" />
               <atom id="atom" xFract="0.49407341" yFract="0.68433687" zFract="0.47869690" />
               <atom id="atom" xFract="0.55148637" yFract="0.62329277" zFract="0.54801584" />
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="1" />
   <record id="atom" repeat="*">{F,cc:xFract}{F,cc:yFract}{F,cc:zFract}</record>
   <transform process="addChild" elementName="atom" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:list" id="atom" />
   <transform process="addAttribute" xpath=".//cml:atom" name="xFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:xFract'])" />
   <transform process="addAttribute" xpath=".//cml:atom" name="yFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:yFract'])" />
   <transform process="addAttribute" xpath=".//cml:atom" name="zFract" value="$string(preceding-sibling::cml:scalar[@dictRef='cc:zFract'])" />
   <transform process="move" xpath=".//cml:atom" to="." />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
