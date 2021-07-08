.. _dispersion-d3e38514:

dispersion
==========

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
   | *source*                          | Turbomole control file            |
   +-----------------------------------+-----------------------------------+
   | id                                | dispersion                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Empirical dispersion correction   |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\u002                         |
   |                                   | 4\s*(?i:(disp3|olddisp|disp))\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | dispersion.xml                    |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   $disp3      
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="dispersion">
           <module cmlx:templateRef="dispersion">
               <scalar dataType="xsd:string" dictRef="t:correction">disp3</scalar>
           </module>     
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*\u0024{X,t:correction}</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
