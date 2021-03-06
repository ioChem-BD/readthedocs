.. _thermochemistry-d3e22816:

thermochemistry
===============

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
   | id                                | thermochemistry                   |
   +-----------------------------------+-----------------------------------+
   | name                              | Thermochemistry section           |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\*\s*THERMOCHEMISTRY.\*       |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s\*                         |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | offset                            | -2                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/th                        |
   |                                   | ermochemistry/thermochemistry.xml |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

    *********************
    *                   *
    *  THERMOCHEMISTRY  *
    *                   *
    *********************

    Mass-centered Coordinates (Angstrom):
    ***********************************************************
    Label   N         X           Y           Z          Mass  
    -----------------------------------------------------------
    C1      6     0.000000   -0.398668    0.633261     12.00000
    C2      6     0.000000    0.398705   -0.633364     12.00000
    O3      8     0.000000    0.138237    1.710248     15.99492
    H4      1     0.000001   -1.485792    0.502175      1.00782
    O5      8     0.000000   -0.138274   -1.710170     15.99492
    H6      1     0.000001    1.485936   -0.502183      1.00782
    -----------------------------------------------------------
    Molecular mass:   58.005480
    Rotational Constants (cm-1):    0.1497    0.1626    1.8991
    Rotational Constants (GHz) :    4.4893    4.8735   56.9350
    Rotational temperatures (K):    0.2155    0.2339    2.7324
    Rotational Symmetry factor:  1
    Vibrational temperature (K): 
       195.01   499.45   823.12  1210.63  1559.82
      1583.17  1978.92  2029.89  2563.24  2574.91
      4366.71  4374.91
    Number of trans. and rot. degrees of freedom:  6
    ZPVE                23.608 kcal/mol      0.037621 au.

   ...
    -----------------------------------------------------

       
       

**Template definition.**

.. code:: xml

   <xi:include href="modules/thermochemistry/zpve.xml" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
