.. _forces-d3e32026:

forces
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
   | *source*                          | QuantumEspresso log               |
   +-----------------------------------+-----------------------------------+
   | id                                | forces                            |
   +-----------------------------------+-----------------------------------+
   | name                              | forces                            |
   +-----------------------------------+-----------------------------------+
   | pattern                           | ^\s+                              |
   |                                   | Total\s(Dispersion\s)?[Ff]orce.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | forces.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        Total force =     0.013129     Total SCF correction =     0.000094
       
       

**Input.**

::

        Total Dispersion Force =     0.067387
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="force">
           <module cmlx:templateRef="forces">        
               <scalar dataType="xsd:double" dictRef="cc:force" units="nonsi2:ev.angstrom-1">0.3375602847997187</scalar>
               <scalar dataType="xsd:double" dictRef="qex:scfCorrection" units="nonsi2:ev.angstrom-1">0.002416838050969119</scalar>                        
           </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="force2">
           <module cmlx:templateRef="forces">
               <scalar dataType="xsd:double" dictRef="qex:dispenergy" units="nonsi2:ev.angstrom-1">1.7325900610708087</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <template pattern="\s*Total\sforce.*" endPattern="~">  <record>\s*Total\sforce\s={F,cc:force}Total SCF correction ={F,qex:scfCorrection}</record>  <transform process="pullup" xpath=".//cml:scalar" repeat="1" />  <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=25.71104309541616" />  <transform process="addUnits" xpath=".//cml:scalar" value="nonsi2:ev.angstrom-1" />         
       </template>
   <template pattern="\s*Total\sDispersion\sForce.*" endPattern="~">  <record>\s*Total\sDispersion\sForce\s*={F,qex:dispenergy}</record>  <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=25.71104309541616" />  <transform process="addUnits" xpath=".//cml:scalar" value="nonsi2:ev.angstrom-1" />
       </template>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
