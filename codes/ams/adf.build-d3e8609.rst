.. _adf.build-d3e8609:

adf.build
=========

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
   | *source*                                                                                                                   | AMS ADF log                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | adf.build                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s+&#92;*&#92;s+B&#92;sU&#92;sI&#92;sL&#92;sD&#92;s&#92;:&#92;s&#92;(Fragments&#92;,&#92;sFunctions&#92;).\*           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;d*&#92;s*$&#92;s&#92;*{20,}.*$(&#92;s*|&#92;s*LOGFILE.*)                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 2                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | adf/build_fragments.xml                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                                         ****************************************
                                         *  B U I L D : (Fragments, Functions)  *
                                         ****************************************
                                        
    =======
    S F O s  ***  (Symmetrized Fragment Orbitals)  ***
    =======
     
    SFOs are linear combinations of (valence) Fragment Orbitals (FOs), such that the SFOs transform as the
    irreducible representations of the (molecular) symmetry group. Each SFO is therefore characterized by
    an irrep of the molecule and by a few (or only one) generating FOs
    
    ....
    
    
     Summary of a frequency scan in the requested range: 
    (One component per degenerate irreducible representations, degeneracy is not counted in the intens.)
    ---------------------------------------------------------------------------------------------------
    Frequency, cm**(-1)      Dipol moment derivatives (a.u.)      IR Intensity   Force const   Red.mass
       Old      New                X         Y         Z            km/mole          a.u.        a.u.
    ---------------------------------------------------------------------------------------------------
    Vibration symmetry: A
      -51.657    52.760         -0.101     0.054     0.002           12.836      0.00251441   23.868787
      -27.178    37.410         -0.023    -0.032     0.032            2.528      0.00120976   22.841882
       16.489      not re-calculated (not in the required range)
       34.998      not re-calculated (not in the required range)
       37.572      not re-calculated (not in the required range)
       46.567      not re-calculated (not in the required range)
       58.375      not re-calculated (not in the required range)
       58.904      not re-calculated (not in the required range)
       72.413      not re-calculated (not in the required range)
       76.848      not re-calculated (not in the required range)
       79.477      not re-calculated (not in the required range)
       88.491      not re-calculated (not in the required range)
       93.808      not re-calculated (not in the required range)
      107.983      not re-calculated (not in the required range)
      115.865      not re-calculated (not in the required range)
      125.710      not re-calculated (not in the required range)
      130.932      not re-calculated (not in the required range)
      137.110      not re-calculated (not in the required range)
      145.822      not re-calculated (not in the required range)
      159.225      not re-calculated (not in the required range)
      180.310      not re-calculated (not in the required range)
      182.831      not re-calculated (not in the required range)
      191.535      not re-calculated (not in the required range)
      200.688      not re-calculated (not in the required range)
      202.939      not re-calculated (not in the required range)
      215.655      not re-calculated (not in the required range)
      219.853      not re-calculated (not in the required range)
      235.919      not re-calculated (not in the required range)
      252.113      not re-calculated (not in the required range)
      256.325      not re-calculated (not in the required range)
      262.495      not re-calculated (not in the required range)
      268.801      not re-calculated (not in the required range)
      278.108      not re-calculated (not in the required range)
      284.339      not re-calculated (not in the required range)
      295.820      not re-calculated (not in the required range)
      301.502      not re-calculated (not in the required range)
      305.006      not re-calculated (not in the required range)
      313.884      not re-calculated (not in the required range)
      322.161      not re-calculated (not in the required range)
      347.060      not re-calculated (not in the required range)
      352.966      not re-calculated (not in the required range)
      365.039      not re-calculated (not in the required range)
      367.435      not re-calculated (not in the required range)
      387.534      not re-calculated (not in the required range)
      411.988      not re-calculated (not in the required range)
      414.426      not re-calculated (not in the required range)
      419.283      not re-calculated (not in the required range)
      446.483      not re-calculated (not in the required range)
      477.122      not re-calculated (not in the required range)
      484.528      not re-calculated (not in the required range)
      492.307      not re-calculated (not in the required range)
      528.129      not re-calculated (not in the required range)
      537.292      not re-calculated (not in the required range)
      558.294      not re-calculated (not in the required range)
      579.671      not re-calculated (not in the required range)
      599.544      not re-calculated (not in the required range)
      604.648      not re-calculated (not in the required range)
      617.953      not re-calculated (not in the required range)
      622.328      not re-calculated (not in the required range)
      634.384      not re-calculated (not in the required range)
      644.496      not re-calculated (not in the required range)
      681.808      not re-calculated (not in the required range)
      696.942      not re-calculated (not in the required range)
      731.533      not re-calculated (not in the required range)
      739.170      not re-calculated (not in the required range)
      759.981      not re-calculated (not in the required range)
      770.690      not re-calculated (not in the required range)
      786.097      not re-calculated (not in the required range)
      790.427      not re-calculated (not in the required range)
      817.302      not re-calculated (not in the required range)
      821.664      not re-calculated (not in the required range)
      825.339      not re-calculated (not in the required range)
      829.275      not re-calculated (not in the required range)
      843.819      not re-calculated (not in the required range)
      846.803      not re-calculated (not in the required range)
      876.784      not re-calculated (not in the required range)
      897.441      not re-calculated (not in the required range)
      903.464      not re-calculated (not in the required range)
      907.962      not re-calculated (not in the required range)
      925.490      not re-calculated (not in the required range)
      936.783      not re-calculated (not in the required range)
      938.951      not re-calculated (not in the required range)
      954.648      not re-calculated (not in the required range)
      967.503      not re-calculated (not in the required range)
      975.074      not re-calculated (not in the required range)
     1087.951      not re-calculated (not in the required range)
     1089.758      not re-calculated (not in the required range)
     1098.617      not re-calculated (not in the required range)
     1126.333      not re-calculated (not in the required range)
     1142.157      not re-calculated (not in the required range)
     1244.525      not re-calculated (not in the required range)
     1250.542      not re-calculated (not in the required range)
     1291.887      not re-calculated (not in the required range)
     1338.245      not re-calculated (not in the required range)
     1345.848      not re-calculated (not in the required range)
     1365.448      not re-calculated (not in the required range)
     1462.133      not re-calculated (not in the required range)
     1474.467      not re-calculated (not in the required range)
     1505.224      not re-calculated (not in the required range)
     1576.430      not re-calculated (not in the required range)
     1586.143      not re-calculated (not in the required range)
     1650.210      not re-calculated (not in the required range)
     1667.972      not re-calculated (not in the required range)
     2685.132      not re-calculated (not in the required range)
     2776.478      not re-calculated (not in the required range)
     2968.122      not re-calculated (not in the required range)
     3039.335      not re-calculated (not in the required range)
     3093.392      not re-calculated (not in the required range)
     3108.811      not re-calculated (not in the required range)
     3123.347      not re-calculated (not in the required range)
     3139.558      not re-calculated (not in the required range)
     3277.441      not re-calculated (not in the required range)
     3409.905      not re-calculated (not in the required range)
     3555.962      not re-calculated (not in the required range)
     3623.176      not re-calculated (not in the required range)
     3632.115      not re-calculated (not in the required range)
     3675.220      not re-calculated (not in the required range)
    ===================================================================================================
    
    ...

    ***************************************************************************************************
       
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="adf.build">
           <module cmlx:templateRef="adf.build">
               <module cmlx:templateRef="scanfreq">
                  <list cmlx:templateRef="scanfreq">
                     <array dataType="xsd:double" dictRef="a:oldfreq" size="2" units="nonsi:cm-1">-51.657 -27.178</array>
                     <array dataType="xsd:double" dictRef="a:newfreq" size="2" units="nonsi:cm-1">52.760 37.410</array>
                     <array dataType="xsd:double" dictRef="a:dipolederivX" size="2" units="nonsi:hartree">-0.101 -0.023</array>
                     <array dataType="xsd:double" dictRef="a:dipolederivY" size="2" units="nonsi:hartree">0.054 -0.032</array>
                     <array dataType="xsd:double" dictRef="a:dipolederivZ" size="2" units="nonsi:hartree">0.002 0.032</array>
                     <array dataType="xsd:double" dictRef="cc:irintensity" size="2" units="nonsi2:km.mol-1">12.836 2.528</array>
                     <array dataType="xsd:double" dictRef="cc:forceconst" size="2" units="nonsi:hartree">0.00251441 0.00120976</array>
                     <array dataType="xsd:double" dictRef="cc:redmass" size="2" units="nonsi:hartree">23.868787 22.841882</array>
                  </list>
               </module>         
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="scanfreq" pattern="\s*Summary\sof\sa\sfrequency\sscan\sin\sthe\srequested\srange.*" endPattern="\s*={20,}.*" endPattern2="~" endOffset="0" repeat="*">    <templateList>      <template pattern="\s*Frequency.*" endPattern="\s*\-?[0-9]+.*" endOffset="0">        <record repeat="*" />
                   </template>      <template pattern="\s*\-?[0-9]+.*" endPattern=".*not\sre-calculated\s\(not\sin\sthe\srequired\srange.*" endOffset="0">        <record repeat="*" makeArray="true" id="scanfreq">{F,a:oldfreq}{F,a:newfreq}{F,a:dipolederivX}{F,a:dipolederivY}{F,a:dipolederivZ}{F,cc:irintensity}{F,cc:forceconst}{F,cc:redmass}</record>
                   </template>      <transform process="addUnits" xpath=".//cml:array[@dictRef='a:oldfreq']" value="nonsi:cm-1" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='a:newfreq']" value="nonsi:cm-1" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='a:dipolederivX']" value="nonsi:hartree" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='a:dipolederivY']" value="nonsi:hartree" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='a:dipolederivZ']" value="nonsi:hartree" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:irintensity']" value="nonsi2:km.mol-1" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:forceconst']" value="nonsi:hartree" />      <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:redmass']" value="nonsi:hartree" />      <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='scanfreq']" />e
                         <transform process="delete" xpath=".//cml:list[count(*) = 0]" />      <transform process="delete" xpath=".//cml:list[count(*) = 0]" />      <transform process="delete" xpath=".//cml:module[count(*) = 0]" />                  
               </templateList>
           </template>
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
