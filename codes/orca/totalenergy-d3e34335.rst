.. _totalenergy-d3e34335:

totalenergy
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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | totalenergy                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Total SCF energy                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-+.*$&#92;s*TOTAL&#92;sSCF&#92;sENERGY&#92;s\*                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s+&#92;*{5,}.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;-+.*$&#92;S+.*$&#92;-+.\*                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/energies/total.xml                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

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
       

.. container:: formalpara-title

   **Input**

::

   ----------------
   TOTAL SCF ENERGY
   ----------------

   Total Energy       :        -3796.80553581 Eh         -103316.33113 eV

   Components:
   Nuclear Repulsion  :         2238.34142232 Eh           60908.36662 eV
   Electronic Energy  :        -6035.14695814 Eh         -164224.69775 eV
   One Electron Energy:        -9672.23819548 Eh         -263194.98187 eV
   Two Electron Energy:         3637.09123734 Eh           98970.28412 eV
   Max COSX asymmetry :            0.00000043 Eh               0.00001 eV

   Virial components:
   Potential Energy   :        -7591.32951133 Eh         -206570.57785 eV
   Kinetic Energy     :         3794.52397551 Eh          103254.24672 eV
   Virial Ratio       :            2.00060128


   DFT components:
   N(Alpha)           :       89.999968770854 electrons
   N(Beta)            :       85.999966063689 electrons
   N(Total)           :      175.999934834543 electrons
   E(X)               :     -179.462545447663 Eh
   E(C)               :       -7.917251270004 Eh
   E(XC)              :     -187.379796717667 Eh
   DFET-embed. en.    :        0.000000000000 Eh

   ---------------
       

.. container:: formalpara-title

   **Output text**

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

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="final2">
           <module cmlx:templateRef="totalenergy" dictRef="cc:userDefinedModule">
               <scalar dataType="xsd:double" dictRef="cc:totalener" units="nonsi:hartree">-3796.80553581</scalar>
               <scalar dataType="xsd:double" dictRef="cc:nucrepener" units="nonsi:hartree">2238.34142232</scalar>
               <scalar dataType="xsd:double" dictRef="cc:electener" units="nonsi:hartree">-6035.14695814</scalar>
               <scalar dataType="xsd:double" dictRef="cc:oneelecener" units="nonsi:hartree">-9672.23819548</scalar>
               <scalar dataType="xsd:double" dictRef="cc:twoeener" units="nonsi:hartree">3637.09123734</scalar>
               <scalar dataType="xsd:double" dictRef="cc:potentialEnergy" units="nonsi:hartree">-7591.32951133</scalar>
               <scalar dataType="xsd:double" dictRef="cc:kineticenergy" units="nonsi:hartree">3794.52397551</scalar>
               <scalar dataType="xsd:double" dictRef="o:vircoeff">2.00060128</scalar>
               <list id="dftcomponents">
                   <scalar dataType="xsd:double" dictRef="cc:alphae">89.999968770854</scalar>
                   <scalar dataType="xsd:double" dictRef="cc:betae">85.999966063689</scalar>
                   <scalar dataType="xsd:double" dictRef="cc:totale">175.999934834543</scalar>
                   <scalar dataType="xsd:double" dictRef="o:exchangeener" units="nonsi:hartree">-179.462545447663</scalar>
                   <scalar dataType="xsd:double" dictRef="o:correlationener" units="nonsi:hartree">-7.917251270004</scalar>
                   <scalar dataType="xsd:double" dictRef="o:xcener" units="nonsi:hartree">-187.379796717667</scalar>
               </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

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
   <record repeat="*">\s*Max\sCOSX\sasymmetry.*</record>
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

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
