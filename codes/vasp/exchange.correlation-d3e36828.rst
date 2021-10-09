.. _exchange.correlation-d3e36828:

exchange.correlation
====================

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
   | id                                | exchange.correlation              |
   +-----------------------------------+-----------------------------------+
   | name                              | Exchange correlation treatment    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Exch                          |
   |                                   | ange\scorrelation\streatment:\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | incar/exchange.correlation.xml    |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Exchange correlation treatment:
      GGA     =    PE    GGA type
      LEXCH   =     8    internal setting for exchange type
      VOSKOWN=      0    Vosko Wilk Nusair interpolation
      LHFCALC =     F    Hartree Fock is set to
      LHFONE  =     F    Hartree Fock one center treatment
      AEXX    =    0.0000 exact exchange contribution
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="exchange.correlation">
           <module cmlx:templateRef="exchange.correlation">  
               <module>
                  <list cmlx:templateRef="missingID">
                     <scalar dataType="xsd:string" dictRef="v:gga">PE</scalar>
                  </list>
               </module>
               <module cmlx:templateRef="parameter">
                  <list cmlx:templateRef="missingID">
                     <list>
                        <scalar dataType="xsd:string" dictRef="v:lexch">8</scalar>
                     </list>
                  </list>
               </module>
               <module cmlx:templateRef="parameter">
                  <list cmlx:templateRef="missingID">
                     <list>
                        <scalar dataType="xsd:string" dictRef="v:voskown">0</scalar>
                     </list>
                  </list>
               </module>
               <module cmlx:templateRef="LHFCALC">
                  <list cmlx:templateRef="missingID">
                     <scalar dataType="xsd:boolean" dictRef="v:lhfcalc">false</scalar>
                  </list>
               </module>
               <module cmlx:templateRef="parameter">
                  <list cmlx:templateRef="missingID">
                     <list>
                        <scalar dataType="xsd:string" dictRef="v:lhfone">F</scalar>
                     </list>
                  </list>
               </module>
               <module cmlx:templateRef="AEXX">
                  <list cmlx:templateRef="missingID">
                     <scalar dataType="xsd:double" dictRef="v:aexx">0.0000</scalar>
                  </list>
               </module>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s+GGA\s+.*" endPattern=".*" endPattern2="~">    <record>\s+GGA\s+.*={A,v:gga}.*</record> 
           </template>  <template id="LHFCALC" pattern="\s+LHFCALC\s+.*" endPattern=".*" endPattern2="~">    <record>\s+LHFCALC\s+.*={B,v:lhfcalc}.*</record> 
           </template>  <template id="HFSCREEN" pattern="\s+HFSCREEN\s*.*" endPattern=".*" endPattern2="~">    <record>\s+HFSCREEN\s*.*={E,v:hfscreen}.*</record> 
           </template>  <template id="AEXX" pattern="\s+AEXX\s*.*" endPattern=".*" endPattern2="~">    <record>\s+AEXX\s*.*={E,v:aexx}.*</record> 
           </template>  <template id="AGGAX" pattern="\s+AGGAX\s*.*" endPattern=".*" endPattern2="~">    <record>\s+AGGAX\s*.*={E,v:aggax}.*</record> 
           </template>  <template id="ALDAC" pattern="\s+ALDAC\s*.*" endPattern=".*" endPattern2="~">    <record>\s+AGGAX\s*.*={E,v:aldac}.*</record> 
           </template>  <template id="parameter" pattern=".*=.*" endPattern=".*" endPattern2="~" repeat="*">    <record>\s+{A,x:parameter}={A,x:value}{X,x:description}</record>    <transform process="addAttribute" xpath=".//cml:scalar[@dictRef='x:value']" name="dictRef" value="$string(concat('v:' , lower-case(preceding-sibling::cml:scalar[@dictRef='x:parameter']/text())))" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:description']" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='x:parameter']" />
           </template>
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
