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
   | Author                                                                                                                | *Username fullname*                                                                                                  | Alvarez Moreno, Moises                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | Bi 32 O 128 V 32                                                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic                                                                                                         | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | Method used (fixed)                                                                                                  | DFT                                                                                                                                                           |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Functional                                                                                                            | Custom logic                                                                                                         | Extracted from the initial section in `parameters template`_                                                                                                  |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: QuantumEspresso- General Info - Additional fields (if they appear in `environ`_ module)

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Temperature                                                                                                                        | <scalar dictRef="`cc:parameter`_">static permittivity</scalar>                                                                     | 298.87222246132 K                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Pressure                                                                                                                           | <scalar dictRef="`cc:parameter`_">external pressure in input</scalar>                                                              | -3454.231433506 atm                                                                                                                |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

|image0|

 [1]_

 [2]_

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

|image1|

Atoms and Basis Sets
--------------------

After settings section, our HTML resume will output cell coordinates, lattice vectors and a coordinates table with molecule atoms.

Geometry is readed from input file using :<list cmlx:templateRef="`atoms`_">, <list cmlx:templateRef="`species`_">, <module cmlx:templateRef="`lattice`_"> and <module cmlx:templateRef="`axes`_"> for geometry optimizations.

For every atom, we will output it's serial number, atom type, cartesian and fractional coordinates (in angstroms) , and <list cmlx:templateRef="`species`_">.

|image2|

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

LDA+U calculation
~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`ldau`_'>

|image3|

Kpoint list
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`kpoints`_'>

|image4|

Point group
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`point.group`_'>

|image5|

Modules
-------

Forces
~~~~~~

Data source: <module cmlx:templateRef='`forces`_'>

|image6|

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`energies`_'>

|image7|

Magnetic moment per site
~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`magnetic`_'>

|image8|

Eigenvalues
~~~~~~~~~~~

Data source <module cmlx:templateRef='`eigenvalues`_'>

|image9|

Projects wavefunctions onto orthogonalized atomic wavefunctions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`projwfc`_'>

|image10|

Frequencies
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`frequencies`_'>

|image11|

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

                                  
          $functionals  <module cmlx:templateRef="header" >
          $calculation   Calculation type defined on <module cmlx:templateRef="qespresso.input" > , CONTROL section. 
                         

                              
                              

.. _header template: ../codes/quantumespresso/header-d3e30287.html
.. _parameters template: ../codes/quantumespresso/parameters-d3e30350.html
.. _environ: ../codes/quantumespresso/environ-d3e31128.html
.. _`cc:parameter`: ../codes/quantumespresso/environ-d3e31128.html
.. _parameters: ../codes/quantumespresso/parameters-d3e30350.html
.. _atoms: ../codes/quantumespresso/qespresso.input-d3e41121.html
.. _species: ../codes/quantumespresso/qespresso.input-d3e41121.html
.. _lattice: ../codes/quantumespresso/lattice-d3e30531.html
.. _axes: ../codes/quantumespresso/axes-d3e30640.html
.. _ldau: ../codes/quantumespresso/ldau-d3e31418.html
.. _kpoints: ../codes/quantumespresso/kpoints-d3e31463.html
.. _point.group: ../codes/quantumespresso/point.group-d3e31105.html
.. _forces: ../codes/quantumespresso/forces-d3e31516.html
.. _energies: ../codes/quantumespresso/energies-d3e31308.html
.. _magnetic: ../codes/quantumespresso/magnetic-d3e31572.html
.. _eigenvalues: ../codes/quantumespresso/eigenvalues-d3e31607.html
.. _projwfc: ../codes/quantumespresso/projwfc-d3e31720.html
.. _frequencies: ../codes/quantumespresso/frequencies-d3e31939.html

.. |image0| image:: /imgs/QUANTUMESPRESSO_header.png
.. |image1| image:: /imgs/QUANTUMESPRESSO_settings.png
.. |image2| image:: /imgs/QUANTUMESPRESSO_geometry.png
.. |image3| image:: /imgs/QUANTUMESPRESSO_info_ldau.png
.. |image4| image:: /imgs/QUANTUMESPRESSO_kpoints.png
.. |image5| image:: /imgs/QUANTUMESPRESSO_point_group.png
.. |image6| image:: /imgs/QUANTUMESPRESSO_module_forces.png
.. |image7| image:: /imgs/QUANTUMESPRESSO_module_energies.png
.. |image8| image:: /imgs/QUANTUMESPRESSO_module_magnetic.png
.. |image9| image:: /imgs/QUANTUMESPRESSO_module_eigen.png
.. |image10| image:: /imgs/QUANTUMESPRESSO_module_projwfc.png
.. |image11| image:: /imgs/QUANTUMESPRESSO_module_frequencies.png
