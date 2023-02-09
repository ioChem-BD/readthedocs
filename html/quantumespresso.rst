QuantumEspresso
===============

General Info
------------

.. table:: QuantumEspresso - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | supercell2x2x2                                                                                                                                                |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://www.iochem-bd.org/handle/10/123456                                                                                                                    |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `header template`_                                                                                                   | QuantumEspresso 6.1                                                                                                                                           |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | Bi 32 O 128 V 32                                                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | Method used (fixed)                                                                                                  | DFT                                                                                                                                                           |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Functional                                                                                                            | Custom logic  [2]_                                                                                                   | Extracted from the initial section in `parameters template`_                                                                                                  |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: QuantumEspresso- General Info - Additional fields (if they appear in `environ`_ module)

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Temperature                                                                                                                        | <scalar dictRef="`cc:parameter`_">static permittivity</scalar>                                                                     | 298.87222246132 K                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Pressure                                                                                                                           | <scalar dictRef="`cc:parameter`_">external pressure in input</scalar>                                                              | -3454.231433506 atm                                                                                                                |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/QUANTUMESPRESSO_header.png

Settings
--------

Most relevant calculation input parameters. All information fields come from <module cmlx:templateRef="`parameters`_">

-  bravais-lattice index

-  lattice parameter (alat)

-  unit-cell volume

-  number of atoms/cell

-  number of atomic types

-  number of electrons

-  number of Kohn-Sham states

-  kinetic-energy cutoff

-  charge density cutoff

-  convergence threshold

-  mixing beta

-  number of iterations used

-  Exchange-correlation

-  ...

.. image:: /imgs/QUANTUMESPRESSO_settings.png

Atoms and Basis Sets
--------------------

After settings section, our HTML resume will output cell coordinates, lattice vectors and a coordinates table with molecule atoms.

Geometry is read from input file using :<list cmlx:templateRef="`atoms`_">, <list cmlx:templateRef="`species`_">, <module cmlx:templateRef="`lattice`_"> and <module cmlx:templateRef="`axes`_"> for geometry optimizations.

For every atom, we will output it's serial number, atom type, cartesian and fractional coordinates (in angstroms) , and <list cmlx:templateRef="`species`_">.

.. image:: /imgs/QUANTUMESPRESSO_geometry.png

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

LDA+U calculation
~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`ldau`_'>

.. image:: /imgs/QUANTUMESPRESSO_info_ldau.png

Kpoint list
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`kpoints`_'>

.. image:: /imgs/QUANTUMESPRESSO_kpoints.png

Point group
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`point.group`_'>

.. image:: /imgs/QUANTUMESPRESSO_point_group.png

Modules
-------

Forces
~~~~~~

Data source: <module cmlx:templateRef='`forces`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_forces.png

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`energies`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_energies.png

.. image:: /imgs/QUANTUMESPRESSO_module_energies_graph.png

Magnetic moment per site
~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`magnetic`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_magnetic.png

Eigenvalues
~~~~~~~~~~~

Data source <module cmlx:templateRef='`eigenvalues`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_eigen.png

Projects wavefunctions onto orthogonalized atomic wavefunctions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`projwfc`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_projwfc.png

Frequencies
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`frequencies`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_frequencies.png

Absorption spectra
~~~~~~~~~~~~~~~~~~

Data source: <module id='`qespresso.absorptionspec`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_absorption.png

Band structure
~~~~~~~~~~~~~~

Data source: <module id='`qespresso.bands`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_bands.png

Projected DOS
~~~~~~~~~~~~~

Data source: <module id='`qespresso.bands <#QuantumEspresso PDOS:qespresso.pdos>`__'>

.. image:: /imgs/QUANTUMESPRESSO_module_pdos.png

Phonon dispersion
~~~~~~~~~~~~~~~~~

Data source: <module id='`qespresso.phonon.input`_'>

Data source: <module id='`qespresso.phonon`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_phonon.png

Phonon DOS
~~~~~~~~~~

Data source: <module id='`qespresso.phonon`_'>

.. image:: /imgs/QUANTUMESPRESSO_module_phonon_dos.png

.. [1]
   string ``qex:getCalcType`` string ``modName`` string ``calculation``

   .. code:: xml

                                  
          $modName  Name of the module <module cmlx:templateRef="header" >
          $calculation   Calculation type defined on <module cmlx:templateRef="qespresso.input" > , CONTROL section. 
                         
         <!-- Calculation type related constants -->
         <xsl:param name="moduleName"/>
         <xsl:param name="calculation"/>
              
              <xsl:variable name="nCalculation" select="replace(helper:trim(upper-case($calculation)),'[^A-Z-]','')"/>          
              
              <xsl:choose>
                  <xsl:when test="helper:trim(upper-case($moduleName)) = 'PWSCF'">
                      <xsl:choose>
                          <xsl:when test="$nCalculation = 'VC-RELAX'">
                              <xsl:value-of select="$qex:GeometryOptimization"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'RELAX'">
                              <xsl:value-of select="$qex:GeometryOptimization"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'SCF'">
                              <xsl:value-of select="$qex:SinglePoint"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'BANDS'">
                              <xsl:value-of select="$qex:Bands"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'NSCF'">
                              <xsl:value-of select="$qex:NonSCF"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'MD'">
                              <xsl:value-of select="$qex:MolecularDynamics"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'CP'">
                              <xsl:value-of select="$qex:CarParrinello"/>
                          </xsl:when>
                          <xsl:when test="$nCalculation = 'CP-WF'">
                              <xsl:value-of select="$qex:CarParrinelloWF"/>
                          </xsl:when>            
                          <xsl:otherwise>
                              <xsl:value-of select="$qex:SinglePoint"/>
                          </xsl:otherwise>
                      </xsl:choose>                        
                  </xsl:when>
                  <xsl:when test="helper:trim(upper-case($moduleName)) = 'PWNEB'">
                      <xsl:value-of select="$qex:NudgedElasticBand"/>
                  </xsl:when>
                  <xsl:otherwise>
                      <xsl:value-of select="$qex:SinglePoint"/>
                  </xsl:otherwise>            
              </xsl:choose>
                              
                                                  

.. [2]
   .. code:: xml

                                  
          $functionals  Exchange-correlation parameter from <module cmlx:templateRef="parameter" >
          $functionalsFromFilenames  Functionals read from qex:pseudofile scalar on <module cmlx:templateRef="pseudopotential" >
                                                      
                     
          <xsl:param name="functionals"/>
          <xsl:param name="functionalsFromFilenames"/>

          <xsl:value-of select="if(exists($functionals)) then $functionals else $functionalsFromFilenames"/>
                              
                                                  

.. _header template: ../codes/quantumespresso/header-d3e41065.html
.. _parameters template: ../codes/quantumespresso/parameters-d3e41128.html
.. _environ: ../codes/quantumespresso/environ-d3e41964.html
.. _`cc:parameter`: ../codes/quantumespresso/environ-d3e41964.html
.. _parameters: ../codes/quantumespresso/parameters-d3e41128.html
.. _atoms: ../codes/quantumespresso/qespresso.input-d3e56129.html
.. _species: ../codes/quantumespresso/qespresso.input-d3e56129.html
.. _lattice: ../codes/quantumespresso/lattice-d3e41309.html
.. _axes: ../codes/quantumespresso/axes-d3e41418.html
.. _ldau: ../codes/quantumespresso/ldau-d3e42291.html
.. _kpoints: ../codes/quantumespresso/kpoints-d3e42336.html
.. _point.group: ../codes/quantumespresso/point.group-d3e41941.html
.. _forces: ../codes/quantumespresso/forces-d3e42416.html
.. _energies: ../codes/quantumespresso/energies-d3e42144.html
.. _magnetic: ../codes/quantumespresso/magnetic-d3e42472.html
.. _eigenvalues: ../codes/quantumespresso/eigenvalues-d3e42507.html
.. _projwfc: ../codes/quantumespresso/projwfc-d3e42620.html
.. _frequencies: ../codes/quantumespresso/frequencies-d3e42839.html
.. _qespresso.absorptionspec: ../codes/quantumespresso/qespresso.absorptionspec-d3e57173.html
.. _qespresso.bands: #QuantumEspresso bands:qespresso.bands
.. _qespresso.phonon.input: #QuantumEspresso phonon input:qespresso.phonon.input
.. _qespresso.phonon: #QuantumEspresso phonon output:qespresso.phonon
