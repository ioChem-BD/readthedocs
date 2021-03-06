.. _symmetry-d3e2154:

symmetry
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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | symmetry                          |
   +-----------------------------------+-----------------------------------+
   | name                              | ADF Init symmetry parameters      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*={                            |
   |                                   | 10,}.*$\s*S\sY\sM\sM\sE\sT\sR\sY\ |
   |                                   | s,\s*E\sL\sE\sC\sT\sR\sO\sN\sS.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s*={10,}.\*                 |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*\*{10,}.\*                    |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | runtype/symmetry.xml              |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    =====================================
    S Y M M E T R Y ,   E L E C T R O N S
    =====================================

    Symmetry: D(4H)

    Irreducible Representations, including subspecies
    -------------------------------------------------
    A1.g
    A2.g
    B1.g
    B2.g
    E1.g:1  E1.g:2
    A1.u
    A2.u
    B1.u
    B2.u
    E1.u:1  E1.u:2


    Configuration of Valence Electrons
    ==================================
    ( determined in the SCF procedure )

    Total:   476

    Net Charge: -4 (Nuclei minus Electrons)

    Aufbau principle for MO occupations will be applied through SCF cycle no.      30
    Thereafter, the program will assign electrons to MOs that are spatially
    similar to the occupied MOs in a "reference" cycle ("KeepOrbitals").
    The reference cycle is always the PREVIOUS cycle: it will evolve with
    the SCF procedure.
   1
    ***************************************************************************************************
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="symmetry">
           <module cmlx:templateRef="symmetry">
               <scalar dataType="xsd:string" dictRef="a:symmetry">T(D)</scalar>
               <scalar dataType="xsd:string" dictRef="a:charge">-4</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Symmetry:.*" endPattern=".*">    <record>\s*Symmetry:{X,a:symmetry}</record>
           </template>  <template pattern="\s*Net\sCharge.*" endPattern=".*">    <record>\s*Net\sCharge:{I,a:charge}\(Nuclei\sminus\sElectrons\).*</record>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
