.. _energy3-d3e36445:

energy3
=======

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
   | id                                | energy3                           |
   +-----------------------------------+-----------------------------------+
   | name                              | Energy section 3                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*E-fermi\s:.\*                 |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | energy3.xml                       |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    E-fermi :  -0.1238     XC(G=0):  -6.5267     alpha+bet : -6.4535       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="energy2">
           <module cmlx:templateRef="energy3" id="energy3">
               <scalar dataType="xsd:double" dictRef="v:efermi" units="nonsi:electronvolt">-0.1238</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*E\-fermi\s:{F,v:efermi}.*</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='v:efermi']" value="nonsi:electronvolt" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
