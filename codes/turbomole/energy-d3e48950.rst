.. _energy-d3e48950:

energy
======

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
   | *source*                                                                                                                   | Turbomole log                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | energy                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Final energies section                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*T&#92;s*p&#92;s*ln.\*                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | (&#92;s+&#92;S+&#92;d){5}$&#92;s\*                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 2                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | energy2.xml                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

      T        p       ln(qtrans) ln(qrot) ln(qvib) chem.pot.   energy    entropy
     (K)      (MPa)                                 (kJ/mol)   (kJ/mol) (kJ/mol/K)
    
    298.15   0.1000000      17.02    11.06     0.62    235.15    317.70   0.28517
    
      T        P              Cv            Cp       enthalpy
     (K)     (MPa)        (kJ/mol-K)    (kJ/mol-K)   (kJ/mol)
    298.15   0.1000000     0.0683144     0.0766287    320.18
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="energy">
            <module cmlx:templateRef="energy">
               <list>
                 <scalar dataType="xsd:double" dictRef="cc:temp" units="si:k">298.15</scalar>
                 <scalar dataType="xsd:double" dictRef="cc:press" units="nonsi:bar">1.0</scalar>
                 <scalar dataType="xsd:double" dictRef="t:thermalcorrgfe" units="nonsi:hartree">0.08956388497</scalar>
                 <scalar dataType="xsd:double" dictRef="t:thermalcorrener" units="nonsi:hartree">0.12100551245999999</scalar>
                 <scalar dataType="xsd:double" dictRef="t:entropy" units="nonsi2:kJ.mol-1.K-1">0.28517</scalar>
                 <scalar dataType="xsd:double" dictRef="t:thermalcorrenthalpy" units="nonsi:hartree">0.12195009436399999</scalar>
                 <scalar dataType="xsd:double" dictRef="cc:freeEnergy" id="free" units="nonsi:hartree" />
              </list>
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template name="energy" pattern="\s*T\s*p\s*ln.*" endPattern=".*\d\s*$\s*" endPattern2="~" endOffset="1">    <record repeat="3" />    <record repeat="*" id="line">\s*{F,cc:temp}{F,cc:press}\s+\S+\s+\S+\s+\S+\s+{F,t:thermalcorrgfe}{F,t:thermalcorrener}{F,t:entropy}</record>         
           </template>  <template name="energy" pattern="\s*T\s*P\s*Cv\s*Cp.*" endPattern="\s*" endOffset="0">    <record repeat="2" />    <record repeat="*" id="other">\s*{F,cc:temp}{F,cc:press}\s+\S+\s+\S+\s+{F,t:thermalcorrenthalpy}</record>    <transform process="moveRelative" xpath=".//cml:scalar[@dictRef='t:thermalcorrenthalpy']" to="(ancestor::cml:module[@cmlx:templateRef='energy']//cml:list[@cmlx:templateRef='line']/cml:list[not(descendant::cml:scalar[@dictRef='t:thermalcorrenthalpy'])])[1]" />
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='line']/cml:list" repeat="2" />
   <transform process="delete" xpath="./cml:module" />
   <transform process="addChild" xpath=".//cml:list" elementName="cml:scalar" id="free" />
   <transform process="addAttribute" xpath=".//cml:scalar[@id='free']" name="dataType" value="xsd:double" />
   <transform process="addAttribute" xpath=".//cml:scalar[@id='free']" name="dictRef" value="cc:freeEnergy" />
   <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='t:thermalcorrener' or @dictRef='t:thermalcorrgfe' or @dictRef='t:thermalcorrenthalpy']" args="operator=multiply operand=0.0003808798" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='t:thermalcorrener' or @dictRef='t:thermalcorrgfe' or @dictRef='cc:freeEnergy' or @dictRef='t:thermalcorrenthalpy']" value="nonsi:hartree" />
   <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='cc:press']" args="operator=multiply operand=10.0" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:press']" value="nonsi:bar" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:temp']" value="si:k" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='t:entropy']" value="nonsi2:kJ.mol-1.K-1" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
