.. _eprnmr-d3e29811:

eprnmr
======

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
   | id                                | eprnmr                            |
   +-----------------------------------+-----------------------------------+
   | name                              | EPR/NMR calculation section       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s                               |
   |                                   | *ORCA\sEPR\/NMR\s*CALCULATION\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*DOMO-.VMO.\*                  |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*\*{20,}.\*                    |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/eprnmr/eprnmr.xml             |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

   ------------------------------------------------------------------------------
                                   ORCA EPR/NMR CALCULATION
   ------------------------------------------------------------------------------
   ...

   DOMO->SOMO (beta ->beta )  :     0.917      1.080
   SOMO->SOMO (alpha->beta )  :    -0.029     -0.343
   DOMO->VMO  (beta ->alpha)  :    -0.122      0.022
       

**Template definition.**

.. code:: xml

   <xi:include href="eprnmr/gmatrix.xml" />
   <xi:include href="eprnmr/zerofield.xml" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
