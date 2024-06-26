GRRM
====

General Info
------------

.. table:: GRRM - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/5672                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `program.header template`_                                                                                           | GRRM 23                                                                                                                                                       |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | `Custom value`_                                                                                                      | SC-AFIR2                                                                                                                                                      |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | Fixed value (`method used`_)                                                                                         | DFT (B3LYP)                                                                                                                                                   |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Symmetry                                                                                                              | <scalar dictRef="`cc:pointgroup`_">                                                                                  | C2v                                                                                                                                                           |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Temperature                                                                                                           | <scalar dictRef="`cc:temp`_">                                                                                        | 298.15K                                                                                                                                                       |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Pressure                                                                                                              | <scalar dictRef="`cc:press`_">                                                                                       | 1.00 atm                                                                                                                                                      |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/GRRM_header.png

.. image:: /imgs/GRRM_header2.png

Atomic coordinates
------------------

The HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms.

.. table:: Atomic coordinates - Possible candidates

   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Section                                                                                                                                                                                               | Note                                                                                                                                                                                                  |
   +=======================================================================================================================================================================================================+=======================================================================================================================================================================================================+
   | <module cmlx:templateRef="`irc`_">                                                                                                                                                                    | Intrinsic Reaction Coordinate module                                                                                                                                                                  |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`structure`_">                                                                                                                                                              | Initial structure                                                                                                                                                                                     |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`final-geometry`_">                                                                                                                                                         | Optimized structure                                                                                                                                                                                   |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`opt`_">                                                                                                                                                                    | Opimization module                                                                                                                                                                                    |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`frequencies`_">                                                                                                                                                            | Frequency module                                                                                                                                                                                      |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/GRRM_geometry.png

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

.. table:: Molecular Info - Main fields

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Multiplicity                                                                                                                       | <scalar dictRef="`cc:multiplicity`_">                                                                                              | 1                                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Charge                                                                                                                             | <scalar dictRef="`cc:charge`_">                                                                                                    | 0                                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/GRRM_molecularinfo.png

Modules
-------

Electronic Energy
~~~~~~~~~~~~~~~~~

Data sources:

-  <module cmlx:templateRef="`final-geometry`_"><scalar dictRef="cc:energy">

-  <module cmlx:templateRef="`opt`_"><scalar dictRef="cc:energy">

-  <module cmlx:templateRef="`structure`_"><scalar dictRef="cc:energy">

.. image:: /imgs/GRRM_module_energy.png

S**2
~~~~

Data sources:

-  <module cmlx:templateRef="`final-geometry`_"><scalar dictRef="cc:s2">

-  <module cmlx:templateRef="`opt`_"><scalar dictRef="cc:s2">

-  <module cmlx:templateRef="`structure`_"><scalar dictRef="cc:s2">

.. image:: /imgs/GRRM_module_s2.png

Frequencies
~~~~~~~~~~~

Data sources: <module cmlx:templateRef="`frequencies`_">

.. image:: /imgs/GRRM_module_frequencies.png

Thermochemistry
~~~~~~~~~~~~~~~

Data sources: <module cmlx:templateRef="`frequencies`_">

.. image:: /imgs/GRRM_module_thermochemistry.png

Intrinsic Reaction Coordinate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data sources: <module cmlx:templateRef="`irc`_">

.. image:: /imgs/GRRM_module_irc.png

.. _program.header template: ../codes/grrm/header-d3e28585.html
.. _Custom value: ../codes/grrm/grrm.input-d3e54453.html
.. _method used: ../codes/grrm/grrm.input-d3e54453.html
.. _`cc:pointgroup`: ../codes/grrm/structure-d3e31297.html
.. _`cc:temp`: ../codes/grrm/frequencies-d3e30997.html
.. _`cc:press`: ../codes/grrm/frequencies-d3e30997.html
.. _irc: ../codes/grrm/irc-d3e28681.html
.. _structure: ../codes/grrm/structure-d3e31297.html
.. _final-geometry: ../codes/grrm/final-geometry-d3e30827.html
.. _opt: ../codes/grrm/opt-d3e30414.html
.. _frequencies: ../codes/grrm/frequencies-d3e30997.html
.. _`cc:multiplicity`: ../codes/grrm/grrm.input-d3e54453.html
.. _`cc:charge`: ../codes/grrm/grrm.input-d3e54453.html
