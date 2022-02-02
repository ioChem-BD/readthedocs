ADF
===

General Info
------------

.. table:: ADF - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/1722                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `program.header template`_                                                                                           | ADF 2007                                                                                                                                                      |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | H 1 O 40 P 1 Ti 1 W 11                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Geometry optimization Minimum                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | DFT                                                                                                                  | DFT                                                                                                                                                           |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: ADF - General Info - Additional fields (if `thermochemistry`_ module exists)

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Temperature                                                                                                                        | <scalar dictRef="`cc:temp`_">                                                                                                      | 300 K                                                                                                                              |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Pressure                                                                                                                           | <scalar dictRef="`cc:press`_">                                                                                                     | 1.0 atm                                                                                                                            |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/ADF_header.png

Atoms and Basis Sets
--------------------

After header section, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms, basis used and contraction.

In geometry optimizations calculations, next to geometry section header there will appear the word **(optimized)**, pointing that this geometry is the last one from all optimization steps and has converged.

If the geometry optimization did not converge, there will appear the phrase **(calculation did not converge)**.

If there are multiple geometries we'll capture them acording with the following table order :

.. table:: Atomic coordinates - Possible candidates (most important first)

   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Section                                                                                                                                                                                               | Note                                                                                                                                                                                                  |
   +=======================================================================================================================================================================================================+=======================================================================================================================================================================================================+
   | <module cmlx:templateRef="`geometry.cycle`_">                                                                                                                                                         | Latest geometry cycle(Coordinates on Input orientation)                                                                                                                                               |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`geometry.cycle`_">                                                                                                                                                         | Lastest geom.opt. (Coordinates)                                                                                                                                                                       |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`quild.coord`_">                                                                                                                                                            | Latest quild iteration                                                                                                                                                                                |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`nuclear.coordinates`_">                                                                                                                                                    | NMR geometry                                                                                                                                                                                          |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | <module cmlx:templateRef="`geometry`_">                                                                                                                                                               | Single point initial geometry                                                                                                                                                                         |
   +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/ADF_geometry.png

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

.. table:: Molecular Info - Main fields

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Description                                                                                                                        |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Spin polarization                                                                                                                  | <scalar dictRef="`a:spinPolarization`_">                                                                                           | Variable found inside logfile module (last instance is captured)                                                                   |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Multiplicity                                                                                                                       | Depends on `spin polarization`_                                                                                                    | If spin polarization exists, multiplicity = spinpolarization + 1, otherwise multiplicity = 1                                       |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Charge                                                                                                                             | <scalar dictRef="`a:charge`_">                                                                                                     | Variable found inside logfile module (last instance is captured)                                                                   |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Solvation                                                                                                                          | <module cmlx:templateRef="`solvation`_">                                                                                           | Solvation parameters                                                                                                               |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/ADF_molecularinfo.png

Modules
-------

Bonding energy
~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`bonding.energy`_'>

.. image:: /imgs/ADF_module_bondingenergies.png

Fit test
~~~~~~~~

Data source: <module cmlx:templateRef='`fit.test`_'>

.. image:: /imgs/ADF_module_fittest.png

MOs / SFO gross populations
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`molecular-orbitals`_'>

.. image:: /imgs/ADF_module_molecularorbitals.png

MOs Energies
~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`orbital.energies`_'>

Data source: <module cmlx:templateRef='`orbital.energies.spin`_'>

.. image:: /imgs/ADF_module_orbitalenergies.png

Data source: <module cmlx:templateRef='`orbital.energies.spin`_'>

.. image:: /imgs/ADF_module_orbitalenergiesspin.png

Mulliken Atomic Charges
~~~~~~~~~~~~~~~~~~~~~~~

Data source <module cmlx:templateRef='`mulliken`_'>

.. image:: /imgs/ADF_module_mullikenatomiccharges.png

Multipole Derived Atomic Charges
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`atomic.charges`_'>

Data source: <module cmlx:templateRef='`atomic.charges.spin`_'>

Data source: <module cmlx:templateRef='`spin.density`_'>

.. image:: /imgs/ADF_module_multipolederivedatomiccharges.png

.. image:: /imgs/ADF_module_multipolederivedatomiccharges2.png

.. image:: /imgs/ADF_module_multipolederivedatomiccharges3.png

Quadrupole Moment
~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`quadrupole.moment`_'>

.. image:: /imgs/ADF_module_quadrupolemoment.png

S**2
~~~~

Data source: <module cmlx:templateRef="`s2`_">

.. image:: /imgs/ADF_module_s2.png

Vibrational Frequencies and Intensities
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`intensities`_'>

.. image:: /imgs/ADF_module_intensities.png

IR spectrum
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`vibrations`_'>

This module will display JSpecView + JSmol plugins (using javascript libraries) working together to represent molecule IR spectrum.

.. image:: /imgs/ADF_module_frequencies.png

Zero Point Energy
~~~~~~~~~~~~~~~~~

Data source:

-  <module cmlx:templateRef="zeropoint"><scalar dictRef="`cc:zeropoint`_">

.. image:: /imgs/ADF_module_zeropointenergy.png

Thermochemistry
~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`thermochemistry`_'>

.. image:: /imgs/ADF_module_thermochemistry.png

Final Excitation Energies
~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`excitation.energy`_'>

.. image:: /imgs/ADF_module_finalexcitationenergies.png

NMR Shielding Tensors
~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`nmr`_'>

.. image:: /imgs/ADF_module_nmr.png

Timing
~~~~~~

Data source: <module cmlx:templateRef='`timing`_'>

.. image:: /imgs/ADF_module_timing.png

Input file
~~~~~~~~~~

Data source: <module cmlx:templateRef='`input.file`_'>

.. image:: /imgs/ADF_module_inputfile.png

.. [1]
   string ``adf:getCalcType`` string ``runtype`` boolean ``hasVibrations`` boolean ``isMininum`` boolean ``isQuild`` boolean ``isNMR``

   .. code:: xml

                                  
          $runtype        Refers to <scalar dataType="xsd:string" dictRef="cc:runtype">
          $hasVibrations  Exists module <module cmlx:templateRef="vibrations" > ?
          $isMinimum      All frequencies from <module cmlx:templateRef="vibrations" > are positive?
          $isQuild        Exists module <module cmlx:templateRef="quild.iteration" > ?
          $isNMR          Exists module <module cmlx:templateRef="nucleus" > ?                            
                     
          
          <!-- Calculation type related constants -->
          <xsl:variable name="adf:GeometryOptimization" select="'Geometry optimization'" />
          <xsl:variable name="adf:SinglePoint" select="'Single point'" />
          <xsl:variable name="adf:TransitionState" select="'TS'" />
          <xsl:variable name="adf:Frequencies" select="'Frequencies'" />
          <xsl:variable name="adf:Minimum" select="'Minimum'"/>
          <xsl:variable name="adf:Quild" select="'Quild'" />    
          <xsl:variable name="adf:NMR" select="'NMR'" />
          
          <!-- Calculation type variables -->
          <xsl:variable name="calcType" select="
              if(compare($runType,'GEOMETRY OPTIMIZATION') = 0) 
                  then $adf:GeometryOptimization 
              else
                  if(compare($runType,'SINGLE POINT') = 0)
                      then $adf:SinglePoint
                  else
                      if(compare($runType,'TRANSITION STATE') = 0)
                          then $adf:TransitionState
                      else
                          if(compare($runType,'FREQUENCIES') = 0)
                              then $adf:Frequencies
                          else
                              $adf:SinglePoint" />              
          
          <xsl:variable name="vibrations" select="
              if($hasVibrations)
                  then if($isMinimum)
                          then concat(' ', $adf:Minimum)
                       else
                           if(compare($calcType,$adf:TransitionState) != 0) 
                               then concat(' ',$adf:TransitionState)
                           else 
                               ''
              else ''" />
              
          <xsl:variable name="quild" select="
              if($isQuild)
                  then concat(' ',$adf:Quild)
              else
                  ''" />
              
          <xsl:variable name="nmr" select="
              if($isNMR)
                  then concat(' ',$adf:NMR)
              else
                  ''"
          />
          <xsl:sequence select="concat($calcType, $vibrations, $quild, $nmr)"/>                              
                              
                              

.. _program.header template: ../codes/adf/program.header-d3e28.html
.. _thermochemistry: ../codes/adf/thermochemistry-d3e4680.html
.. _`cc:temp`: ../codes/adf/thermochemistry-d3e4680.html
.. _`cc:press`: ../codes/adf/thermochemistry-d3e4680.html
.. _geometry.cycle: ../codes/adf/geometry.cycle-d3e2540.html
.. _quild.coord: ../codes/adf/quild.coord-d3e5050.html
.. _nuclear.coordinates: ../codes/adf/nuclear.coordinates-d3e237.html
.. _geometry: ../codes/adf/geometry-d3e1819.html
.. _`a:spinPolarization`: ../codes/adf/logfile-d3e5184.html
.. _spin polarization: ../codes/adf/logfile-d3e5184.html
.. _`a:charge`: ../codes/adf/logfile-d3e5184.html
.. _solvation: ../codes/adf/solvation-d3e1673.html
.. _bonding.energy: ../codes/adf/bonding.energy-d3e3739.html
.. _fit.test: ../codes/adf/fit.test-d3e3276.html
.. _molecular-orbitals: ../codes/adf/molecular.orbitals-d3e3850.html
.. _orbital.energies: ../codes/adf/orbital.energies-d3e3188.html
.. _orbital.energies.spin: ../codes/adf/orbital.energies.spin-d3e3231.html
.. _mulliken: ../codes/adf/mulliken-d3e3327.html
.. _atomic.charges: ../codes/adf/atomic.charges-d3e3524.html
.. _atomic.charges.spin: ../codes/adf/atomic.charges.spin-d3e3575.html
.. _spin.density: ../codes/adf/spin.density-d3e3626.html
.. _quadrupole.moment: ../codes/adf/quadrupole.moment-d3e3680.html
.. _s2: ../codes/adf/s2-d3e3710.html
.. _intensities: ../codes/adf/intensities-d3e4640.html
.. _vibrations: ../codes/adf/vibrations-d3e4560.html
.. _`cc:zeropoint`: ../codes/adf/zeropoint-d3e4528.html
.. _excitation.energy: ../codes/adf/excitation.energy-d3e4266.html
.. _nmr: ../codes/adf/nmr-d3e21.html
.. _timing: ../codes/adf/timing-d3e5279.html
.. _input.file: ../codes/adf/input.file-d3e6642.html
