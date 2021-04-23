.. _kirkwood-d3e19858:

kirkwood
========

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
   | id                                | kirkwood                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Kirkwood model                    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Reaction\sField\scalc         |
   |                                   | ulation:\sthe\sKirkwood\smodel.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/kirkwood.xml              |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        Reaction Field calculation: the Kirkwood model
         Dielectric Constant : 0.800E+02
         Eps_opt             : 0.100E+01
         Radius of Cavity(au): 0.475E+01
         l_Max               : 4
         Calculation type    : equilibrium 
    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="kirkwood">
           <module cmlx:templateRef="kirkwood">
               <scalar dataType="xsd:double" dictRef="m:dielectricvalue">0.800E+02</scalar>
               <scalar dataType="xsd:double" dictRef="m:epsopt">0.100E+01</scalar>
               <scalar dataType="xsd:double" dictRef="m:cavityradius" units="nonsi:angstrom">0.475E+01</scalar>
               <scalar dataType="xsd:double" dictRef="m:lmax">4</scalar>
               <scalar dataType="xsd:string" dictRef="m:calctype">equilibrium</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <record />
   <record>\s*Dielectric\sConstant\s:{E,m:dielectricvalue}</record>
   <record>\s*Eps_opt\s*:{E,m:epsopt}</record>
   <record>\s*Radius\sof\sCavity\(au\):{E,m:cavityradius}</record>
   <record>\s*l_Max\s+:{F,m:lmax}</record>
   <record>\s*Calculation\stype\s+:{X,m:calctype}</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='m:cavityradius']" value="nonsi:angstrom" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
