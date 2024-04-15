.. _cosmo-d3e39418:

cosmo
=====

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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | cosmo                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Cosmo section                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{10,}$&#92;s*COSMO&#92;sINITIALIZATION.\*                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*-{10,}$&#92;s*&#92;w.\*                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/cosmo/cosmo.xml                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   --------------------
   COSMO INITIALIZATION
   --------------------

   Epsilon                                      ...   80.4000
   Refractive Index                             ...    1.3300
   Potential Evaluation                         ...  ANALYTIC
   Technical COSMO parameters:
     rsolv                                      ...    1.3000
     routf                                      ...    0.8500
     disex                                      ...   10.0000
     nppa                                       ... 1082   
     nspa                                       ...   92   
   Radii:
    Radius for O  used is    3.2503 Bohr (=   1.7200 Ang.)
    Radius for C  used is    3.7795 Bohr (=   2.0000 Ang.)
    Radius for H  used is    2.4566 Bohr (=   1.3000 Ang.)
   Initializing COSMO package            ... done
   Setting COSMO radii                   ... done
   Setting atoms and making cavity       ...  USING 1082 GRID
   done
   Cholesky decomposition of A           ... done
   --------------

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="cosmo">
           <module cmlx:templateRef="cosmo" dictRef="cc:userDefinedModule">
              <list cmlx:templateRef="technical">
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">rsolv</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">1.3000</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">routf</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">0.8500</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">disex</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">10.0000</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">nppa</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">1082</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">nspa</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">92</scalar>
                 </list>
              </list>
              <list cmlx:templateRef="radii">
                 <array dataType="xsd:string" dictRef="cc:elementType" size="3">O C H</array>
                 <array dataType="xsd:double" dictRef="o:radius" size="3" units="nonsi:angstrom">1.7200 2.0000 1.3000</array>
              </list>
              <list cmlx:templateRef="parameters" dictRef="parameters">
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Epsilon</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">80.4000</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Refractive Index</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">1.3300</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Potential Evaluation</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">ANALYTIC</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Initializing COSMO package</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">done</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Setting COSMO radii</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">done</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Setting atoms and making cavity</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">USING 1082 GRID</scalar>
                 </list>
                 <list>
                    <scalar dataType="xsd:string" dictRef="cc:parameter">Cholesky decomposition of A</scalar>
                    <scalar dataType="xsd:string" dictRef="cc:value">done</scalar>
                 </list>
              </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*Technical\sCOSMO\sparameters.*" endPattern="\s*Radii.*" endPattern2="\w.*" endPattern3="~" repeat="*">    <record />    <record id="technical" repeat="*">{X,cc:parameter}\.\.\.{X,cc:value}</record>
           </template>  <template pattern="\s*Radii:\s*" endPattern="\s*(?!.*Radius).+" endPattern2="~" repeat="*">    <record />    <record id="radii" repeat="*" makeArray="true">\s*Radius\sfor{A,cc:elementType}used\sis.*\(={F,o:radius}.*</record>
           </template>  <template id="parameter" pattern=".*\.\.\..*" endPattern=".*" endPattern2="~" repeat="*">    <record>{X,cc:parameter}\.\.\.{X,cc:value}</record>
           </template>
       </templateList>
   <transform process="move" xpath=".//cml:module[@cmlx:templateRef='parameter']/cml:list/cml:list" to="." />
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='radii']" />
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='technical']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module" />
   <transform process="addUnits" xpath=".//cml:array[@dictRef='o:radius']" value="nonsi:angstrom" />
   <transform process="addChild" elementName="cml:list" xpath="." dictRef="parameters" />
   <transform process="addAttribute" xpath=".//cml:list[@dictRef='parameters']" name="cmlx:templateRef" value="parameters" />
   <transform process="move" xpath="./cml:list[not(@cmlx:templateRef)]" to="./cml:list[@cmlx:templateRef='parameters']" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
