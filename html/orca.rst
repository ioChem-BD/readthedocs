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
   | Author                                                                                                                | *Username fullname*                                                                                                  | Alvarez Moreno, Moises                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | H 2 Fe 1 O 1                                                                                                                                                  |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic                                                                                                         | Geometry optimization Minimum                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method(s)                                                                                                             | Custom logic                                                                                                         | DFT ( PBE0 )                                                                                                                                                  |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

|image0|

 [1]_

 [2]_

Modules
-------

Atomic coordinates
~~~~~~~~~~~~~~~~~~

After header section, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms, basis used and contraction.

|image1|

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

|image2|

Bond distances
^^^^^^^^^^^^^^

Data source (to read molecule and calculate bonds): <module cmlx:templateRef='`input`_'>

Data source (to read molecule and calculate bonds): <module cmlx:templateRef='`geometry`_'>

|image3|

Solvation input
^^^^^^^^^^^^^^^

Data source: <module cmlx:templateRef='`cosmo`_'>

|image4|

Restrictions in the Geometry Optimization
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Data source: <module cmlx:templateRef='`optsetup`_'>

|image5|

Total SCF energy
~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`totalenergy`_'>

Data source: <module cmlx:templateRef='`mp2`_'>

Data source: <module cmlx:templateRef='`ci`_'>

Data source: <module cmlx:templateRef='`d3`_'>

|image6|

IR spectrum / Vibrational frequencies
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This module will display JSpecView + JSmol plugins (using javascript libraries) working together to represent molecule IR spectrum.

Data source: <module cmlx:templateRef='`vibrations`_'>

Data source: <module cmlx:templateRef='`irspectrum`_'>

|image7|

|image8|

Population analysis
~~~~~~~~~~~~~~~~~~~

Data source <module cmlx:templateRef='`loewdin`_'>

Data source <module cmlx:templateRef='`mullikenpopulation`_'>

|image9|

|image10|

Electrostatic moments
~~~~~~~~~~~~~~~~~~~~~

Data source: Charge parameter on General settings section of `scfsettings`_

Data source: `<module cmlx:templateRef='electricproperties'>`_

|image11|

Broken symmetry magnetic coupling analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`brokensym`_">

|image12|

Frontier orbitals
~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`orbitalenergies`_'>

|image13|

|image14|

Natural orbitals
~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`natural`_'>

|image15|

NMR Shielding tensors
~~~~~~~~~~~~~~~~~~~~~

Data source:

-  <module cmlx:templateRef="`nmr`_">

|image16|

TDHF / TDDFT
~~~~~~~~~~~~

This section displays an interative chart to visualize root energies and an additional table with most relevant dominant contributions to each root

Data source: <module cmlx:templateRef='`tddft`_'>

Data source: <module cmlx:templateRef='`orbitalenergies`_'>

|image17|

|image18|

g-matrix and ZFS
~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`eprnmr`_'>

|image19|

Final results
~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`totalenergy`_'>

Data source: <module cmlx:templateRef='`spincontamination`_'>

Data source: <module cmlx:templateRef='`innerenergy`_'>

Data source: <module cmlx:templateRef='`mp2`_'>

Data source: <module cmlx:templateRef='`ci`_'>

Data source: <module cmlx:templateRef='`dftd3`_'>

|image20|

|image21|

|image22|

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
                                  
                              

.. _header template: ../codes/orca/header-d3e25902.html
.. _scfsettings: ../codes/orca/scfsettings-d3e29719.html
.. _input: ../codes/orca/input-d3e25936.html
.. _geometry: ../codes/orca/geometry-d3e27466.html
.. _cosmo: ../codes/orca/cosmo-d3e27100.html
.. _optsetup: ../codes/orca/optsetup-d3e31550.html
.. _totalenergy: ../codes/orca/totalenergy-d3e29583.html
.. _mp2: ../codes/orca/mp2-d3e30358.html
.. _ci: ../codes/orca/ci-d3e30469.html
.. _d3: #d3
.. _vibrations: ../codes/orca/vibrations-d3e27746.html
.. _irspectrum: ../codes/orca/irspectrum-d3e28037.html
.. _loewdin: ../codes/orca/loewdin-d3e28991.html
.. _mullikenpopulation: ../codes/orca/mullikenpopulation-d3e28894.html
.. _`<module cmlx:templateRef='electricproperties'>`: ../codes/orca/electricproperties-d3e29238.html
.. _brokensym: ../codes/orca/brokensym-d3e27648.html
.. _orbitalenergies: ../codes/orca/orbitalenergies-d3e28800.html
.. _natural: ../codes/orca/natural-d3e29364.html
.. _nmr: ../codes/orca/nmr-d3e30646.html
.. _tddft: ../codes/orca/tddft-d3e30764.html
.. _eprnmr: ../codes/orca/eprnmr-d3e31179.html
.. _spincontamination: ../codes/orca/spincontamination-d3e30317.html
.. _innerenergy: ../codes/orca/innerenergy-d3e27900.html
.. _dftd3: ../codes/orca/dftd3-d3e31147.html

.. |image0| image:: /imgs/ORCA_header.png
.. |image1| image:: /imgs/ORCA_geometry.png
.. |image2| image:: /imgs/ORCA_molecularinfo.png
.. |image3| image:: /imgs/ORCA_bonddistances.png
.. |image4| image:: /imgs/ORCA_solvationinput.png
.. |image5| image:: /imgs/ORCA_restrictions.png
.. |image6| image:: /imgs/ORCA_module_scfenergy.png
.. |image7| image:: /imgs/ORCA_module_irspectrum.png
.. |image8| image:: /imgs/ORCA_module_frequencies.png
.. |image9| image:: /imgs/ORCA_module_popanal1.png
.. |image10| image:: /imgs/ORCA_module_popanal2.png
.. |image11| image:: /imgs/ORCA_module_electrostatic.png
.. |image12| image:: /imgs/ORCA_module_brokensymm.png
.. |image13| image:: /imgs/ORCA_module_frontierorb1.png
.. |image14| image:: /imgs/ORCA_module_frontierorb2.png
.. |image15| image:: /imgs/
.. |image16| image:: /imgs/ORCA_module_nmr.png
.. |image17| image:: /imgs/ORCA_module_tddft1.png
.. |image18| image:: /imgs/ORCA_module_tddft2.png
.. |image19| image:: /imgs/ORCA_module_eprnmr.png
.. |image20| image:: /imgs/ORCA_module_finalresults1.png
.. |image21| image:: /imgs/ORCA_module_finalresults2.png
.. |image22| image:: /imgs/ORCA_module_finalresults3.png
