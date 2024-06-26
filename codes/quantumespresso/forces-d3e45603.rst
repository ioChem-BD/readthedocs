.. _forces-d3e45603:

forces
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
   | *source*                                                                                                                   | QuantumEspresso log                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | forces                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | forces                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | ^&#92;s+Total&#92;s(Dispersion&#92;s)?[Ff]orce.\*                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | forces.xml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

        Total force =     0.013129     Total SCF correction =     0.000094
       
       

.. container:: formalpara-title

   **Input**

::

        Total Dispersion Force =     0.067387
       
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="force">
           <module cmlx:templateRef="forces">        
               <scalar dataType="xsd:double" dictRef="cc:force" units="nonsi2:ev.angstrom-1">0.3375602847997187</scalar>
               <scalar dataType="xsd:double" dictRef="qex:scfCorrection" units="nonsi2:ev.angstrom-1">0.002416838050969119</scalar>                        
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="force2">
           <module cmlx:templateRef="forces">
               <scalar dataType="xsd:double" dictRef="qex:dispenergy" units="nonsi2:ev.angstrom-1">1.7325900610708087</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <template pattern="\s*Total\sforce.*" endPattern="~">  <record>\s*Total\sforce\s={F,cc:force}Total SCF correction ={F,qex:scfCorrection}</record>  <transform process="pullup" xpath=".//cml:scalar" repeat="1" />  <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=25.71104309541616" />  <transform process="addUnits" xpath=".//cml:scalar" value="nonsi2:ev.angstrom-1" />         
       </template>
   <template pattern="\s*Total\sDispersion\sForce.*" endPattern="~">  <record>\s*Total\sDispersion\sForce\s*={F,qex:dispenergy}</record>  <transform process="operateScalar" xpath=".//cml:scalar" args="operator=multiply operand=25.71104309541616" />  <transform process="addUnits" xpath=".//cml:scalar" value="nonsi2:ev.angstrom-1" />
       </template>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
