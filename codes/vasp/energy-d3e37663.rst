.. _energy-d3e37663:

energy
======

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
   | id                                | energy                            |
   +-----------------------------------+-----------------------------------+
   | name                              | Energy section                    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*FREE\sENERGIE\sOF\sTHE        |
   |                                   | \sION-ELECTRON\sSYSTEM\s\(eV\).\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*energy\s*without\sentropy.\*  |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | energy.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

     FREE ENERGIE OF THE ION-ELECTRON SYSTEM (eV)
     ---------------------------------------------------
     free  energy   TOTEN  =      -566.22302844 eV

     energy  without entropy=     -566.22206374  energy(sigma->0) =     -566.22254609               
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="energy">
           <module cmlx:templateRef="energies">
               <scalar dataType="xsd:double" dictRef="cc:freeEnergy" units="nonsi:electronvolt">-566.22302844</scalar>
               <scalar dataType="xsd:double" dictRef="v:noEntropyEnergy" units="nonsi:electronvolt">-566.22206374</scalar>
               <scalar dataType="xsd:double" dictRef="cc:e0" units="nonsi:electronvolt">-566.22254609</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="energies" pattern="\s*FREE\sENERGIE\sOF\sTHE\sION-ELECTRON\sSYSTEM\s\(eV\).*" endPattern="\s*energy\s*without\sentropy.*" endOffset="1">    <record repeat="2" />    <record>\s*free\s*energy\s*TOTEN\s*={F,cc:freeEnergy}.*</record>    <record repeat="1" />    <record>\s*energy\s*without\s*entropy={F,v:noEntropyEnergy}energy\(sigma->0\)\s*={F,cc:e0}</record>              
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="pullup" xpath=".//cml:list/cml:scalar" />
   <transform process="delete" xpath=".//cml:list" repeat="2" />
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:electronvolt" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
