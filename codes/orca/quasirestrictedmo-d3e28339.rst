.. _quasirestrictedmo-d3e28339:

quasirestrictedmo
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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | quasirestrictedmo                 |
   +-----------------------------------+-----------------------------------+
   | name                              | QR-MO Generation                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*QR-MO\sGENERATION.\*          |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/quasirestrictedmo.xml         |
   +-----------------------------------+-----------------------------------+

**Input.**

::

       QR-MO GENERATION
         Dim     = 570
         Mult    =   3
         NEl     = 158
         N(DOMO) =  78
         N(SOMO) =   2
         N(VMO)  = 490

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="quasirestrictedmo">
           <module cmlx:templateRef="quasirestrictedmo">
                <list cmlx:templateRef="missingID">
                   <scalar dataType="xsd:string" dictRef="cc:dummy">QR-MO GENERATION</scalar>
                   <scalar dataType="xsd:string" dictRef="cc:dummy">Dim     = 570</scalar>
                   <scalar dataType="xsd:string" dictRef="cc:dummy">Mult    =   3</scalar>
                   <scalar dataType="xsd:string" dictRef="cc:dummy">NEl     = 158</scalar>
                   <scalar dataType="xsd:string" dictRef="cc:dummy">N(DOMO) =  78</scalar>
                   <scalar dataType="xsd:string" dictRef="cc:dummy">N(SOMO) =   2</scalar>
                   <scalar dataType="xsd:string" dictRef="cc:dummy">N(VMO)  = 490</scalar>
                </list>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="*">{X,cc:dummy}</record>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
