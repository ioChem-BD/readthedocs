.. _caspt2.root-d3e20387:

caspt2.root
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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | caspt2.root                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s                               |
   |                                   | *(\+\+)?\s*CASPT2\scomputation.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/caspt2/roots.xml          |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ++ CASPT2 computation    5
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="caspt2.root">
            <module cmlx:templateRef="caspt2.root">
               <list cmlx:templateRef="missingID">
                  <scalar dataType="xsd:integer" dictRef="m:rootnumber">5</scalar>
               </list>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*(\+\+)?\s*CASPT2\scomputation{I,m:rootnumber}</record>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
