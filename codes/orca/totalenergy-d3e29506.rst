.. _totalenergy-d3e29506:

totalenergy
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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | totalenergy                       |
   +-----------------------------------+-----------------------------------+
   | name                              | Total SCF energy                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \                                 |
   |                                   | \s*-+.*$\s*TOTAL\sSCF\sENERGY\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s+\*{5,}.\*                     |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\-+.*$\S+.*$\-+.\*               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/energies/total.xml            |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ----------------
   TOTAL SCF ENERGY
   ----------------

   Total Energy       :         -228.92495871 Eh           -6229.36482 eV

   Components:
   Nuclear Repulsion  :          120.17448994 Eh            3270.11412 eV
   Electronic Energy  :         -349.09944865 Eh           -9499.47894 eV

   One Electron Energy:         -550.00631780 Eh          -14966.43279 eV
   Two Electron Energy:          200.90686915 Eh            5466.95384 eV

   Virial components:
   Potential Energy   :         -455.74150374 Eh          -12401.35679 eV
   Kinetic Energy     :          226.81654504 Eh            6171.99197 eV
   Virial Ratio       :            2.00929568


   DFT components:
   N(Alpha)           :       16.000004642086 electrons
   N(Beta)            :       16.000004642086 electrons
   N(Total)           :       32.000009284172 electrons
   E(X)               :      -28.295324961944 Eh       
   E(C)               :       -1.174635717062 Eh       
   E(XC)              :      -29.469960679007 Eh       

   --------------- 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="final">
           <module cmlx:templateRef="totalenergy" dictRef="cc:userDefinedModule">                     
              <scalar dataType="xsd:double" dictRef="cc:totalener" units="nonsi:hartree">-228.92495871</scalar>
              <scalar dataType="xsd:double" dictRef="cc:nucrepener" units="nonsi:hartree">120.17448994</scalar>
              <scalar dataType="xsd:double" dictRef="cc:electener" units="nonsi:hartree">-349.09944865</scalar>
              <scalar dataType="xsd:double" dictRef="cc:oneelecener" units="nonsi:hartree">-550.00631780</scalar>
              <scalar dataType="xsd:double" dictRef="cc:twoeener" units="nonsi:hartree">200.90686915</scalar>
              <scalar dataType="xsd:double" dictRef="cc:potentialEnergy" units="nonsi:hartree">-455.74150374</scalar>
              <scalar dataType="xsd:double" dictRef="cc:kineticenergy" units="nonsi:hartree">226.81654504</scalar>
              <scalar dataType="xsd:double" dictRef="o:vircoeff">2.00929568</scalar>
              <list id="dftcomponents">
                 <scalar dataType="xsd:double" dictRef="cc:alphae">16.000004642086</scalar>
                 <scalar dataType="xsd:double" dictRef="cc:betae">16.000004642086</scalar>
                 <scalar dataType="xsd:double" dictRef="cc:totale">32.000009284172</scalar>
                 <scalar dataType="xsd:double" dictRef="o:exchangeener" units="nonsi:hartree">-28.295324961944</scalar>
                 <scalar dataType="xsd:double" dictRef="o:correlationener" units="nonsi:hartree">-1.174635717062</scalar>
                 <scalar dataType="xsd:double" dictRef="o:xcener" units="nonsi:hartree">-29.469960679007</scalar>
              </list>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="4" />
   <record>\s*Total\sEnergy\s*:{F,cc:totalener}Eh.*</record>
   <record repeat="2" />
   <record>\s*Nuclear\sRepulsion\s*:{F,cc:nucrepener}Eh.*</record>
   <record>\s*Electronic\sEnergy\s*:{F,cc:electener}Eh.*</record>
   <record repeat="*">\s*COSMO\(ediel\)\s*:{F,cc:cosmoener}Eh.*</record>
   <record repeat="*">\s*</record>
   <record>\s*One\sElectron\sEnergy\s*:{F,cc:oneelecener}Eh.*</record>
   <record>\s*Two\sElectron\sEnergy\s*:{F,cc:twoeener}Eh.*</record>
   <record repeat="*">\s*CPCM\sDielectric\s*:{F,o:cpcmener}Eh.*</record>
   <record repeat="2" />
   <record>\s*Potential\sEnergy\s*:{F,cc:potentialEnergy}Eh.*</record>
   <record>\s*Kinetic\sEnergy\s*:{F,cc:kineticenergy}Eh.*</record>
   <record>\s*Virial\sRatio\s*:{F,o:vircoeff}</record>
   <transform process="addUnits" xpath=".//cml:scalar[not(@dictRef = 'o:vircoeff')]" value="nonsi:hartree" />
   <templateList>  <template id="dftcomponents" pattern="\s*DFT\scomponents\:\s*" endPattern="\s*" endPattern2="~">    <record repeat="1" />    <record>\s*N\(Alpha\)\s*:{F,cc:alphae}electrons\s*</record>    <record>\s*N\(Beta\)\s*:{F,cc:betae}electrons\s*</record>    <record>\s*N\(Total\)\s*:{F,cc:totale}electrons\s*</record>    <record>\s*E\(X\)\s*:{F,o:exchangeener}Eh\s*</record>    <record>\s*E\(C\)\s*:{F,o:correlationener}Eh\s*</record>    <record>\s*E\(XC\)\s*:{F,o:xcener}Eh\s*</record>    <transform process="addChild" xpath="." elementName="cml:list" id="dftcomponents" />    <transform process="move" xpath=".//cml:list/cml:scalar" to="./cml:list[@id='dftcomponents']" />         
           </template>
       </templateList>
   <transform process="move" xpath="./cml:list/cml:scalar" to="." />
   <transform process="move" xpath=".//cml:list[@id='dftcomponents']" to="." />
   <transform process="delete" xpath="./cml:list[@cmlx:templateRef='missingID']" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:exchangeener']" value="nonsi:hartree" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:correlationener']" value="nonsi:hartree" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:xcener']" value="nonsi:hartree" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
