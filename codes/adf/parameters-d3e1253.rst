.. _parameters-d3e1253:

parameters
==========

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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | parameters                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Model parameters                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*                              |
   |                                   | DENSITY\sFUNCTIONAL\sPOTENTIAL.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s\*                         |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*SOLVATION\s\*                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | in                                |
   |                                   | it/modelparameters/parameters.xml |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    DENSITY FUNCTIONAL POTENTIAL (scf)
       LDA:                               VWN                                      
       Gradient Corrections:              Becke88 Perdew86                        == Not Default ==

    SPIN  (restricted / unrestr.)
       Molecule:                          Restricted                               

    OTHER ASPECTS
       Relativistic Corrections:          scalar (ZORA,SAPA)                       *** SPECIAL ***

       Nuclear Charge Density Model:      Point Charge Nuclei                                                                                                                                                                                     
       Core Treatment:                    Frozen Orbital(s)                        

       Electric Field:                    ---                                      

       Hyperfine or Zeeman Interaction:   ---                                          

       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="parameters">       
           <module cmlx:lineCount="17" cmlx:templateRef="parameters">
             <scalar id="method" dictRef="cc:method" dataType="xsd:string">DFT</scalar>
             <list cmlx:lineCount="3" cmlx:templateRef="scf">
               <scalar dataType="xsd:string" dictRef="cc:functional">VWN</scalar>
               <scalar dataType="xsd:string" dictRef="cc:functional">Becke88 Perdew86</scalar>
             </list>
             <list cmlx:lineCount="3" cmlx:templateRef="spin">
               <scalar dataType="xsd:string" dictRef="cc:spinMolecule">Restricted</scalar>
               <scalar dataType="xsd:string" dictRef="cc:spinFragments">Restricted</scalar>
             </list>
             <list cmlx:lineCount="9" cmlx:templateRef="other"> OTHER ASPECTS 
               <scalar dataType="xsd:string" dictRef="a:relcor">scalar (ZORA,SAPA)</scalar>
               <scalar dataType="xsd:string" dictRef="a:densityMode">Point Charge Nuclei</scalar>
               <scalar dataType="xsd:string" dictRef="a:coretreat">Frozen Orbital(s)</scalar>
              </list>           
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="scf" pattern="\s*DENSITY\sFUNCTIONAL\sPOTENTIAL\s\(scf\).*" endPattern="\s*">    <record repeat="1" />    <record id="functional">.*:{X,cc:functional}</record>    <record id="gradient">\s*Gradient\sCorrections:\s+{X,cc:functional}\s*\=\=\s*Not Default\s*\=\=\s*</record>    <transform process="addChild" xpath="." position="1" elementName="cml:scalar" id="method" dictRef="cc:method" value="DFT" />
           </template>  <template id="spin" pattern="\s*SPIN.*" endPattern="\s*" endPattern2="~">    <record repeat="1" />    <record id="molecule">\s*Molecule:\s*{A,cc:spinMolecule}.*</record>    <templateList>      <template pattern="\s*Fragments:.*" endPattern=".*" endPattern2="~">        <record id="fragments">\s*Fragments:\s*{A,cc:spinFragments}.*</record>
                   </template>           
               </templateList>    <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:spinFragments']" />
           </template>  <template id="other" pattern="\s*OTHER\sASPECTS.*" endPattern="~">    <templateList>      <template pattern="\s*Relativistic\sCorrections.*" endPattern=".*" endPattern2="~">        <record>\s*Relativistic\sCorrections:{X,a:relcor}\*\*\*\s*SPECIAL\s*\*\*\*\s*</record>
                    </template>      <template pattern="\s*Nuclear\sCharge\sDensity\sModel.*" endPattern=".*" endPattern2="~">        <record>\s*Nuclear\sCharge\sDensity\sModel:{X,a:densityMode}</record>
                    </template>      <template pattern="\s*Core\sTreatment.*" endPattern=".*" endPattern2="~">        <record>\s*Core\sTreatment:{X,a:coretreat}</record>
                    </template>      <template pattern="\s*Electric\sField.*" endPattern=".*" endPattern2="~">        <record>\s*Electric\sField:{X,a:electricField}</record>
                    </template>      <template pattern="\s*Hyperfine\sor\sZeeman\sInteraction.*" endPattern=".*" endPattern2="~">        <record>\s*Hyperfine\sor\sZeeman\sInteraction:{X,a:zeeman}</record>
                    </template>
               </templateList>
           </template>           
       </templateList>
   <transform process="moveRelative" xpath=".//cml:scalar[@dictRef='cc:method']" to=".//cml:list" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="pullup" xpath=".//cml:module[@cmlx:templateRef='other']/cml:module/cml:scalar" />
   <transform process="delete" xpath=".//cml:scalar[text()='---']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="createList" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
