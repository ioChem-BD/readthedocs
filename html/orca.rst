Orca
====

General Info
------------

.. table:: Orca - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/1722                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `header template`_                                                                                                   | Orca 3.0.1                                                                                                                                                    |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | H 2 Fe 1 O 1                                                                                                                                                  |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Geometry optimization Minimum                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method(s)                                                                                                             | Custom logic  [2]_                                                                                                   | DFT ( PBE0 )                                                                                                                                                  |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/ORCA_header.png

Modules
-------

Atomic coordinates
~~~~~~~~~~~~~~~~~~

After header section, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms, basis used and contraction.

.. image:: /imgs/ORCA_geometry.png

Molecular Info
~~~~~~~~~~~~~~

This section captures molecule additional information not captured on previous section.

.. table:: Molecular Info - Main fields

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Multiplicity                                                                                                                       | Readed from Mul parameter on General settings section of `scfsettings`_ module                                                     | 1                                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Charge                                                                                                                             | Readed from Charge parameter on General settings section of `scfsettings`_ module                                                  | 0                                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/ORCA_molecularinfo.png

Bond distances
^^^^^^^^^^^^^^

Data source (to read molecule and calculate bonds): <module cmlx:templateRef='`input`_'>

Data source (to read molecule and calculate bonds): <module cmlx:templateRef='`geometry`_'>

.. image:: /imgs/ORCA_bonddistances.png

Solvation input
^^^^^^^^^^^^^^^

Data source: <module cmlx:templateRef='`cosmo`_'>

.. image:: /imgs/ORCA_solvationinput.png

Restrictions in the Geometry Optimization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Data source: <module cmlx:templateRef='`optsetup`_'>

.. image:: /imgs/ORCA_restrictions.png

Total SCF energy
~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`totalenergy`_'>

Data source: <module cmlx:templateRef='`mp2`_'>

Data source: <module cmlx:templateRef='`ci`_'>

Data source: <module cmlx:templateRef='`d3`_'>

.. image:: /imgs/ORCA_module_scfenergy.png

IR spectrum / Vibrational frequencies
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This module will display JSpecView + JSmol plugins (using javascript libraries) working together to represent molecule IR spectrum.

Data source: <module cmlx:templateRef='`vibrations`_'>

Data source: <module cmlx:templateRef='`irspectrum`_'>

.. image:: /imgs/ORCA_module_irspectrum.png

.. image:: /imgs/ORCA_module_frequencies.png

Population analysis
~~~~~~~~~~~~~~~~~~~

Data source <module cmlx:templateRef='`loewdin`_'>

Data source <module cmlx:templateRef='`mullikenpopulation`_'>

.. image:: /imgs/ORCA_module_popanal1.png

.. image:: /imgs/ORCA_module_popanal2.png

Electrostatic moments
~~~~~~~~~~~~~~~~~~~~~

Data source: Charge parameter on General settings section of `scfsettings`_

Data source: `<module cmlx:templateRef='electricproperties'>`_

.. image:: /imgs/ORCA_module_electrostatic.png

Broken symmetry magnetic coupling analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`brokensym`_">

.. image:: /imgs/ORCA_module_brokensymm.png

Frontier orbitals
~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`orbitalenergies`_'>

.. image:: /imgs/ORCA_module_frontierorb1.png

.. image:: /imgs/ORCA_module_frontierorb2.png

Natural orbitals
~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`natural`_'>

.. image:: /imgs/ORCA_module_natural.png

NMR Shielding tensors
~~~~~~~~~~~~~~~~~~~~~

Data source:

-  <module cmlx:templateRef="`nmr`_">

.. image:: /imgs/ORCA_module_nmr.png

TDHF / TDDFT
~~~~~~~~~~~~

This section displays an interative chart to visualize root energies and an additional table with most relevant dominant contributions to each root

Data source: <module cmlx:templateRef='`tddft`_'>

Data source: <module cmlx:templateRef='`orbitalenergies`_'>

.. image:: /imgs/ORCA_module_tddft1.png

.. image:: /imgs/ORCA_module_tddft2.png

g-matrix and ZFS
~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`eprnmr`_'>

.. image:: /imgs/ORCA_module_eprnmr.png

Final results
~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`totalenergy`_'>

Data source: <module cmlx:templateRef='`spincontamination`_'>

Data source: <module cmlx:templateRef='`innerenergy`_'>

Data source: <module cmlx:templateRef='`mp2`_'>

Data source: <module cmlx:templateRef='`ci`_'>

Data source: <module cmlx:templateRef='`dftd3`_'>

.. image:: /imgs/ORCA_module_finalresults1.png

.. image:: /imgs/ORCA_module_finalresults2.png

.. image:: /imgs/ORCA_module_finalresults3.png

.. [1]
   string ``orca:getCalcType`` boolean ``isOptimization`` boolean ``isBrokenSymm`` boolean ``hasVibrations`` integer ``negativeFrequenciesCount``

   .. code:: xml

          $isOptimization        Refers to function orca:isOptimization($commands), which searches optimitzation keywords from <module cmlx:templateRef="input" > module  
          $isBrokenSymm          Refers to function orca:isBrokenSymm($commands)  which searches BrokenSymm keyword from <module cmlx:templateRef="input" > module
          $hasVibrations         Exists module <module cmlx:templateRef="vibrations" > ?
          $negativeFrequenciesCount   Count negative frequencies from <module cmlx:templateRef="vibrations" > ?                            
                     
          
          <!-- Calculation type related constants -->
          <xsl:variable name="orca:GeometryOptimization" select="'Geometry optimization'" />
          <xsl:variable name="orca:SinglePoint" select="'Single point'" />
          <xsl:variable name="orca:BrokenSymmetry" select="'Broken symmetry'" />    
          <xsl:variable name="orca:TransitionState" select="'TS'" />
          <xsl:variable name="orca:Minimum" select="'Minimum'"/>

          <!-- Calculation type variables -->
          <xsl:param name="isOptimization" as="xs:boolean"/>
          <xsl:param name="isBrokenSymm" as="xs:boolean"/>
          <xsl:param name="hasVibrations" as="xs:boolean"/>
          <xsl:param name="negativeFrequenciesCount" as="xs:integer"/>
          
          <xsl:variable name="type">
              <xsl:choose>
                  <xsl:when test="$isOptimization">
                      <xsl:value-of select="$orca:GeometryOptimization"/>
                  </xsl:when>
                  <xsl:when test="$isBrokenSymm">
                      <xsl:value-of select="$orca:BrokenSymmetry"/>
                  </xsl:when>
                  <xsl:otherwise>
                      <xsl:value-of select="$orca:SinglePoint"/>
                  </xsl:otherwise>
              </xsl:choose>     
          </xsl:variable>
          
          <xsl:variable name="type2">
              <xsl:if test="$hasVibrations">
                  <xsl:choose>
                      <xsl:when test="$negativeFrequenciesCount > 0">
                          <xsl:value-of select="$orca:TransitionState"/>
                      </xsl:when>
                      <xsl:otherwise>
                          <xsl:value-of select="$orca:Minimum"/>
                      </xsl:otherwise>
                  </xsl:choose>
              </xsl:if>        
          </xsl:variable>
          
          <xsl:value-of select="concat($type, ' ', $type2)"/>                              
                              
                                                  

.. [2]
   string ``orca:getMehods`` nodeset ``section`` boolean ``isTddft``

   .. code:: xml

       
              $section    Input section elements from <module cmlx:templateRef="input"> module  
              $isTddft    Refers to function orca:isTddft($commands) which searches tddft keywords from <module cmlx:templateRef="input" > module                           
                                  
              <xsl:for-each select="$section/cml:array[@dictRef='cc:keywords']">
                  <xsl:variable name="line" select="./text()"/>
                  <xsl:for-each select="tokenize($line,'\s+')">
                      <xsl:variable name="command" select="."/>
                      <xsl:choose>
                          <xsl:when test="matches(upper-case($command), $orca:methodsRegex)">
                              <xsl:if test="$isTddft and matches(upper-case($command), '(DFT|HF)')">TD</xsl:if><xsl:value-of select="$command"/><xsl:text> </xsl:text>    
                          </xsl:when>                   
                          <xsl:when test="matches(upper-case($command),$orca:calculationLevelRegex)">
                              <xsl:if test="$isTddft">TD</xsl:if><xsl:value-of select="$orca:calculationLevels/level[@id=upper-case($command)]/@method"/><xsl:text> </xsl:text>
                          </xsl:when>
                      </xsl:choose>                             
                  </xsl:for-each>
              </xsl:for-each>
              
              <xsl:variable name="blocklines" select="$section//cml:module[@cmlx:templateRef='block']/cml:scalar"/>
              <xsl:for-each select="$blocklines">
                  <xsl:variable name="line" select="./text()"/>                    
                  <xsl:for-each select="tokenize($line,'\s+')">
                      <xsl:variable name="command" select="."/>                
                      <xsl:choose>
                          <xsl:when test="matches(upper-case($command), $orca:methodsRegex)">
                              <xsl:if test="$isTddft and matches(upper-case($command), '(DFT|HF)')">TD</xsl:if><xsl:value-of select="$command"/><xsl:text> </xsl:text>    
                          </xsl:when>
                          <xsl:when test="matches(upper-case($command),$orca:calculationLevelRegex)">
                              <xsl:if test="$isTddft">TD</xsl:if><xsl:value-of select="$orca:calculationLevels/level[@id=upper-case($command)]/@method"/><xsl:text> </xsl:text>
                          </xsl:when>
                      </xsl:choose>             
                  </xsl:for-each>                
              </xsl:for-each>
                                  
                                                  

.. _header template: ../codes/orca/header-d3e38118.html
.. _scfsettings: ../codes/orca/scfsettings-d3e42189.html
.. _input: ../codes/orca/input-d3e38152.html
.. _geometry: ../codes/orca/geometry-d3e39682.html
.. _cosmo: ../codes/orca/cosmo-d3e39316.html
.. _optsetup: ../codes/orca/optsetup-d3e44045.html
.. _totalenergy: ../codes/orca/totalenergy-d3e41867.html
.. _mp2: ../codes/orca/mp2-d3e42829.html
.. _ci: ../codes/orca/ci-d3e42939.html
.. _d3: #d3
.. _vibrations: ../codes/orca/vibrations-d3e39962.html
.. _irspectrum: ../codes/orca/irspectrum-d3e40274.html
.. _loewdin: ../codes/orca/loewdin-d3e41275.html
.. _mullikenpopulation: ../codes/orca/mullikenpopulation-d3e41178.html
.. _`<module cmlx:templateRef='electricproperties'>`: ../codes/orca/electricproperties-d3e41522.html
.. _brokensym: ../codes/orca/brokensym-d3e39864.html
.. _orbitalenergies: ../codes/orca/orbitalenergies-d3e41084.html
.. _natural: ../codes/orca/natural-d3e41648.html
.. _nmr: ../codes/orca/nmr-d3e43141.html
.. _tddft: ../codes/orca/tddft-d3e43259.html
.. _eprnmr: ../codes/orca/eprnmr-d3e43674.html
.. _spincontamination: ../codes/orca/spincontamination-d3e42787.html
.. _innerenergy: ../codes/orca/innerenergy-d3e40137.html
.. _dftd3: ../codes/orca/dftd3-d3e43643.html
