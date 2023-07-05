.. _grrm.input-d3e54351:

grrm.input
==========

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
   | *source*                                                                                                                   | GRRM input                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | grrm.input                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | GRRM input                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   # SC-AFIR2/B3LYP/Def2SVP

   0 1
   C          0.051911596139         -0.000000000000          0.000000000000
   O          1.251598064141          0.000000000000         -0.000000000000
   H         -0.551754830140          0.944696873126         -0.000000000000
   H         -0.551754830140         -0.944696873126         -0.000000000000
   Options
   Add Interaction
   Gamma=1000.0
   END
   GauMem=400
   GauProc=4

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="grrm.input">
           <module id="grrm.input">
              <module cmlx:templateRef="job">
                 <module cmlx:templateRef="input-desc">
                    <list cmlx:templateRef="method">
                       <scalar dataType="xsd:string" dictRef="cc:jobtype">SC-AFIR2</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:method">B3LYP</scalar>
                       <scalar dataType="xsd:string" dictRef="cc:basis">Def2SVP</scalar>
                    </list>
                    <list cmlx:templateRef="charge-mult">
                       <scalar dataType="xsd:integer" dictRef="cc:charge">0</scalar>
                       <scalar dataType="xsd:integer" dictRef="cc:multiplicity">1</scalar>
                    </list>
                    <module cmlx:templateRef="input-coordinates">
                       <molecule cmlx:templateRef="input" id="molecule">
                          <atomArray>
                             <atom elementType="C" id="a1" x3="0.0519116" y3="-0.0000" z3="0.0000">
                                <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
                             </atom>
                             <atom elementType="O" id="a2" x3="1.25159806" y3="0.0000" z3="-0.0000">
                                <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                             </atom>
                             <atom elementType="H" id="a3" x3="-0.55175483" y3="0.94469687" z3="-0.0000">
                                <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                             </atom>
                             <atom elementType="H" id="a4" x3="-0.55175483" y3="-0.94469687" z3="-0.0000">
                                <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                             </atom>
                          </atomArray>
                          <bondArray>
                             <bond atomRefs2="a1 a2" order="S" />
                             <bond atomRefs2="a1 a3" order="S" />
                             <bond atomRefs2="a1 a4" order="S" />
                          </bondArray>
                          <formula concise="CH2O">
                             <atomArray count="1 2 1" elementType="C H O" />
                          </formula>
                          <property dictRef="cml:molmass">
                             <scalar units="unit:dalton">28.0101</scalar>
                          </property>
                       </molecule>
                    </module>
                 </module>
              </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList id="init">  <template id="job" pattern=".*" endPattern="~">    <templateList>      <template id="input-desc" pattern="#.*/.*/.*" endPattern="\s*Options\s*" endPattern2="~">        <record id="method">#\s*{X,cc:jobtype}/{X,cc:method}/{X,cc:basis}\s*</record>        <record id="null" repeat="1" />        <record id="charge-mult">\s*{I,cc:charge}\s*{I,cc:multiplicity}</record>        <template id="input-coordinates" pattern="[A-Za-z]{1,2}\s*.*" endPattern="~">          <record makeArray="true" repeat="*" id="input">\s*{A,compchem:elementType}\s*{F,compchem:x3}\s*{F,compchem:y3}\s*{F,compchem:z3}\s*</record>          <transform process="createMolecule" xpath="./cml:list[@cmlx:templateRef='input']/cml:array" id="molecule" />          <transform process="pullupSingleton" xpath="./cml:list" />
                       </template>        <transform process="pullupSingleton" xpath="./cml:list" />        <transform process="delete" xpath="(//cml:list[@cmlx:templateRef='null'])" />
                   </template>
               </templateList>
           </template>
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
