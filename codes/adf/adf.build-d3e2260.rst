.. _adf.build-d3e2260:

adf.build
=========

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
   | id                                | adf.build                         |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s+\*\s+B\sU\sI\sL\sD\s          |
   |                                   | \:\s\(Fragments\,\sFunctions\).\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\d*\                          |
   |                                   | s*$\s\*{20,}.*$(\s*|\s*LOGFILE.*) |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 2                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | adf/build/build_fragments.xml     |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

                                         ****************************************
                                         *  B U I L D : (Fragments, Functions)  *
                                         ****************************************
                                        
    =======
    S F O s  ***  (Symmetrized Fragment Orbitals)  ***
    =======
     
    SFOs are linear combinations of (valence) Fragment Orbitals (FOs), such that the SFOs transform as the
    irreducible representations of the (molecular) symmetry group. Each SFO is therefore characterized by
    an irrep of the molecule and by a few (or only one) generating FOs
    
    ....

    ***************************************************************************************************
       
       

**Template definition.**

.. code:: xml

   <xi:include href="build/scanfreq.xml" />
   <xi:include href="build/../frequencyanalysis/thermochemistry.xml" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
