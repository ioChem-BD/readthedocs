.. _startparameters-d3e35330:

startparameters
===============

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
   | id                                | startparameters                   |
   +-----------------------------------+-----------------------------------+
   | name                              | Startparameter for this run       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*St                            |
   |                                   | artparameter\sfor\sthis\srun:\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | incar/startparameters.xml         |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Startparameter for this run:
      NWRITE =      2    write-flag & timer
      PREC   = normal    normal or accurate (medium, high low for compatibility)
      ISTART =      1    job   : 0-new  1-cont  2-samecut
      ICHARG =      0    charge: 1-file 2-atom 10-const
      ISPIN  =      2    spin polarized calculation?
      LNONCOLLINEAR =      F non collinear calculations
      LSORBIT =      F    spin-orbit coupling
      INIWAV =      1    electr: 0-lowe 1-rand  2-diag
      LASPH  =      T    aspherical Exc in radial PAW
      METAGGA=      F    non-selfconsistent MetaGGA calc.
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="startparameters"> 
           <module cmlx:templateRef="startparameters">
               <module>
                   <list cmlx:templateRef="missingID">
                       <scalar dataType="xsd:integer" dictRef="v:ispin">2</scalar>
                   </list>
               </module>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*ISPIN.*" endPattern=".*" endPattern2="~">    <record>\s*ISPIN\s*={I,v:ispin}.*</record> 
           </template>   
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
