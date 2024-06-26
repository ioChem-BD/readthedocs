.. _symmetry-d3e2154:

symmetry
========

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image2|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | symmetry                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | ADF Init symmetry parameters                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*={10,}.*$&#92;s*S&                                                                                                  |
   |                                                                                                                            | #92;sY&#92;sM&#92;sM&#92;sE&#92;sT&#92;sR&#92;sY&#92;s,&#92;s*E&#92;sL&#92;sE&#92;sC&#92;sT&#92;sR&#92;sO&#92;sN&#92;sS.\* |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*={10,}.\*                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s*&#92;*{10,}.\*                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | runtype/symmetry.xml                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

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
       

.. container:: formalpara-title

   **Input**

::

       
    =====================================
    S Y M M E T R Y ,   E L E C T R O N S
    =====================================
     
    Symmetry: NOSYM

    Irreducible Representations, including subspecies
    -------------------------------------------------
    A


    Configuration of Valence Electrons
    ==================================
    ( determined in the SCF procedure )

    Total:   70 (Spin-A)  + 69 (Spin-B)

    Net Charge: -3 (Nuclei minus Electrons)
    Spin polar: 1 (Spin_A minus Spin_B electrons)

    Aufbau principle for MO occupations will be applied through SCF cycle no.     150
    Thereafter, the program will assign electrons to MOs that are spatially
    similar to the occupied MOs in a "reference" cycle ("KeepOrbitals").
    The reference cycle is always the PREVIOUS cycle: it will evolve with
    the SCF procedure.
   1
    ***************************************************************************************************

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="symmetry">
           <module cmlx:templateRef="symmetry">
               <scalar dataType="xsd:string" dictRef="a:symmetry">T(D)</scalar>
               <scalar dataType="xsd:string" dictRef="a:charge">-4</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="symmetry2">
           <module cmlx:templateRef="symmetry">
               <scalar dataType="xsd:string" dictRef="a:symmetry">NOSYM</scalar>
               <scalar dataType="xsd:integer" dictRef="a:charge">-3</scalar>
               <scalar dataType="xsd:string" dictRef="a:spinPolarization">1</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template pattern="\s*Symmetry:.*" endPattern=".*" endOffset="0">    <record>\s*Symmetry:{X,a:symmetry}</record>
           </template>  <template pattern="\s*Net\sCharge.*" endPattern=".*" endOffset="0">    <record>\s*Net\sCharge:{I,a:charge}\(Nuclei\sminus\sElectrons\).*</record>
           </template>  <template pattern="\s*Spin\spolar:.*" endPattern=".*" endOffset="0">    <record>.*Spin\spolar:{A,a:spinPolarization}\(Spin_A\sminus\sSpin_B\selectrons\).*</record>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
