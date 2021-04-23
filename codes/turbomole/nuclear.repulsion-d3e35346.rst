.. _nuclear.repulsion-d3e35346:

nuclear.repulsion
=================

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
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | nuclear.repulsion                 |
   +-----------------------------------+-----------------------------------+
   | name                              | Nuclear repulsion energies        |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*nuclear\sre                   |
   |                                   | pulsion\senergy.*$\s*empirical.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*nuclear\srepulsi              |
   |                                   | on\s\+\sdispersion\scorrection.\* |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | nuclear.repulsion.xml             |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    nuclear repulsion energy                  =    4406.824720361
    empirical dispersive energy correction    =      -0.055658060
    nuclear repulsion + dispersion correction =    4406.769062301 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="nuclear.repulsion">   
           <module cmlx:templateRef="nuclear.repulsion">
               <scalar dataType="xsd:double" dictRef="cc:nucrepener" units="nonsi:hartree">4406.82472036</scalar>
               <scalar dataType="xsd:double" dictRef="t:empdispcorrection" units="nonsi:hartree">-0.055658060</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*nuclear\srepulsion\senergy\s*={F,cc:nucrepener}</record>
   <record>\s*empirical\sdispersive\senergy\scorrection\s*={F,t:empdispcorrection}</record>
   <record repeat="1" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath="./cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
