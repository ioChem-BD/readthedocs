.. _orbital.specs.fermi-d3e20757:

orbital.specs.fermi
===================

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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | orbital.specs.fermi               |
   +-----------------------------------+-----------------------------------+
   | name                              | Fermi aufbau orbitals             |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Fermi\                        |
   |                                   | saufbau\sprocedure\scompleted!.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/orbital.specs.fermi.xml   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

          Fermi aufbau procedure completed!
         nOcc=   28   24   
       

**Input.**

::

     Fermi aufbau procedure completed!
    nOcc(alpha)=                    29                    24
    nOcc(beta) =                    27                    24   
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="orbital.specs.fermi">
            <module cmlx:templateRef="orbital.specs.fermi">
               <list>
                   <array dataType="xsd:integer" dictRef="m:occup" size="2">28 24</array>  
               </list>           
            </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="orbital.specs.fermi2">
           <module cmlx:templateRef="orbital.specs.fermi">
               <list>
                  <scalar dataType="xsd:string" dictRef="m:spintype">alpha</scalar>
                  <array dataType="xsd:integer" dictRef="m:occup" size="2">29 24</array>
               </list>
               <list>
                  <scalar dataType="xsd:string" dictRef="m:spintype">beta</scalar>
                  <array dataType="xsd:integer" dictRef="m:occup" size="2">27 24</array>
               </list>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <record />
   <record repeat="*">\s*nOcc\(?({X,m:spintype})\)?\s*={1_30I,m:occup}</record>
   <transform process="pullup" xpath=".//cml:list[child::cml:array]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='m:spintype' and not(text())]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
