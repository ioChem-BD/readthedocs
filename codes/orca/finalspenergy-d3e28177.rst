.. _finalspenergy-d3e28177:

finalspenergy
=============

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
   | id                                | finalspenergy                     |
   +-----------------------------------+-----------------------------------+
   | name                              | Final Single Point Energy         |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{20,}.*$\                    |
   |                                   | s*FINAL\sSINGLE\sPOINT\sENERGY.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/energies/final.xml            |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   -------------------------   ----------------
   FINAL SINGLE POINT ENERGY    -3947.384041263
   -------------------------   ----------------

       

**Input.**

::

   -------------------------   --------------------
   FINAL SINGLE POINT ENERGY     -1339.461219357614   (SCF not fully converged!)
   -------------------------   --------------------
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="finalspenergy">
         <module cmlx:templateRef="finalspenergy">
            <scalar dataType="xsd:double" dictRef="cc:energy">-3947.384041263</scalar>
         </module>       
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="finalspenergy2">
         <module cmlx:templateRef="finalspenergy">
            <scalar dataType="xsd:double" dictRef="cc:energy">-1339.461219357614</scalar>
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <record />
   <record>\s*FINAL\sSINGLE\sPOINT\sENERGY{F,cc:energy}.*</record>
   <transform process="move" xpath=".//cml:scalar[@dictRef='cc:energy']" to="." />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
