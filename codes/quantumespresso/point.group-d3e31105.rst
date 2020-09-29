.. _point.group-d3e31105:

point.group
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
   | *source*                          | QuantumEspresso log               |
   +-----------------------------------+-----------------------------------+
   | id                                | point.group                       |
   +-----------------------------------+-----------------------------------+
   | name                              | Point group                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | ^\s*point\sgroup.\*               |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | initialization/point.group.xml    |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        point group C_1 (1)    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="point.group">
           <module cmlx:templateRef="point.group">
               <scalar dataType="xsd:string" dictRef="cc:pointgroup">C_1 (1)</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*point\sgroup{X,cc:pointgroup}</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
