Molcas
======

General Info
------------

.. table:: Molcas - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://rodi.urv.es:8080/browse/handle/123456789/6                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `program.header template`_                                                                                           | Molcas 8.0 - service pack 1                                                                                                                                   |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | C 8 H 12 N 8 O 2                                                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | Custom logic  [2]_                                                                                                   | RASSCF RASPT2                                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/MOLCAS_header.png

Atomics and Basis Sets
----------------------

After header section, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms, basis used and contraction.

In geometry optimizations calculations, next to geometry section header there will appear the word **(optimized)**, pointing that this geometry is the last one from all optimization steps and has converged.

If the geometry optimization did not converge, there will appear the phrase **(calculation did not converge)**.

.. image:: /imgs/MOLCAS_geometry.png

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

Symmetry information
~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`symmetry`_'>

.. image:: /imgs/MOLCAS_symmetry.png

Molecular Info
~~~~~~~~~~~~~~

.. table:: Molecular Info - Main fields

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Charge                                                                                                                             | Readed from "charge" scalar on `molcharge`_ line or from `mulliken`_ module                                                        | 0.000                                                                                                                              |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Multiplicity                                                                                                                       | Readed from scalar[m:spinquantumnum] inside `wave.specs`_ module OR from scalar[m:spin] inside `scf-ksdft`_ module                 | 3                                                                                                                                  |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/MOLCAS_molecularinfo.png

Solvation input
~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`pcm`_'>

Data source: <module cmlx:templateRef='`kirkwood`_'>

.. image:: /imgs/MOLCAS_solvation.png

Integrals
~~~~~~~~~

Data source: <module cmlx:templateRef='`seward.generate`_'>

.. image:: /imgs/MOLCAS_sewardgenerate.png

Bond distances
~~~~~~~~~~~~~~

Data source (to read molecule and calculate bonds): <module cmlx:templateRef='`coordinates`_'>

.. image:: /imgs/MOLCAS_bonddistances.png

Restrictions in the Geometry Optimization
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`constraint`_'>

.. image:: /imgs/MOLCAS_restrictions.png

Modules
-------

Wave function specification
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`wave.specs`_'>

.. image:: /imgs/MOLCAS_module_wavefunction.png

Orbital specifications
~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`orbital.specs`_'>

.. image:: /imgs/MOLCAS_module_orbitalspecs.png

CI expansion specifications
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`ci.expansion`_'>

.. image:: /imgs/MOLCAS_module_ciexpansion.png

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`wave.printout`_'>

.. image:: /imgs/MOLCAS_module_energies.png

Wave functions / Weights of the most important CSFs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source <module cmlx:templateRef='`wave.printout`_'>

.. image:: /imgs/MOLCAS_module_wavefunctioncsf.png

Natural Occupation numbers
~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`wave.printout`_'>, module "natural"

.. image:: /imgs/MOLCAS_module_natural.png

Mulliken Spin Population
~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`mulliken`_'>, submodule "mulliken.spin"

.. image:: /imgs/MOLCAS_module_mullikenspin.png

Electrostatic moments
~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`properties`_">

.. image:: /imgs/MOLCAS_module_electrostaticmoments.png

Population analysis / Mulliken atomic charges
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`loprop`_">

Data source: <module cmlx:templateRef="`mulliken`_">

.. image:: /imgs/MOLCAS_module_loprop.png

.. image:: /imgs/MOLCAS_module_mulliken.png

Single-State CASPT2
~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`final.caspt2`_">

.. image:: /imgs/MOLCAS_module_singlestate_caspt2.png

Final energy
~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`scf-ksdft`_"> scalar dictRef='m:scfener'

Data source: <module cmlx:templateRef="`cchc`_"> scalar dictRef='m:e2mp2energy'

Data source: <module cmlx:templateRef="`cchc`_"> scalar dictRef='m:e2ccsdenergy'

Data source: <module cmlx:templateRef="`ccsdt`_"> scalar dictRef='m:ccsdtcorrenergy'

.. image:: /imgs/MOLCAS_module_finalenergy.png

.. image:: /imgs/MOLCAS_module_finalenergy2.png

HZERO
~~~~~

Data source: <module cmlx:templateRef="`extras`_">

.. image:: /imgs/MOLCAS_module_hzero.png

Harmonic frequencies
~~~~~~~~~~~~~~~~~~~~

This module also allows displaying harmonic frequency intensities on a customizable chart.

Data source: <module cmlx:templateRef='`vibrations`_'>

.. image:: /imgs/MOLCAS_module_harmonicfreq.png

.. image:: /imgs/MOLCAS_module_harmonicfreq2.png

IR spectrum / Vibrational frequencies
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`vibrations`_'>

This module will display JSpecView + JSmol plugins (using javascript libraries) working together to represent molecule IR spectrum.

.. image:: /imgs/MOLCAS_module_frequencies.png

Multipole Expansion Analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source:<module cmlx:templateRef="`atom.expansion`_">

.. image:: /imgs/MOLCAS_module_multipoleexpansion.png

LoProp Analysis
~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`dynamic.loprop`_'>

.. image:: /imgs/MOLCAS_module_loprop_analysis.png

.. [1]
   string ``molcas:getCalcType`` boolean ``isRestrictedOpt`` boolean ``isOptimization`` boolean ``isTS`` boolean ``isIncomplete``

   .. code:: xml

                                  
          $isRestrictedOpt  Exists module <module cmlx:templateRef="constraint" > ?
          $isOptimization   Input file from <module cmlx:templateRef="molcas.input" > is setup to perform a geometry optimization? 
          $isTS           TS keyword is defined inside <module cmlx:templateRef="molcas.input" > ?
          $isIncomplete   Convergence table from <module cmlx:templateRef="energy.statistics" > shows 'all converged' OR $isOptimization and $hasLastEnergySection ?                             
                     
          
          <!-- Calculation type related constants -->
          <xsl:param name="isRestrictedOpt"/>
          <xsl:param name="isOptimization"/>
          <xsl:param name="isTS"/>
          <xsl:param name="isIncomplete"/>

          <xsl:choose>
              <xsl:when test="$isRestrictedOpt">
                  <xsl:value-of select="$molcas:RestrictedGeomOpt"/>
              </xsl:when>
              <xsl:when test="$isOptimization">
                  <xsl:value-of select="$molcas:GeometryOpt"/>
              </xsl:when>
              <xsl:otherwise>
                  <xsl:value-of select="$molcas:SinglePoint"/>    
              </xsl:otherwise>            
          </xsl:choose>
          <xsl:if test="$isTS">
              <xsl:text> </xsl:text><xsl:value-of select="$molcas:TS"/>
          </xsl:if>               
          <xsl:if test="$isIncomplete">
              <xsl:text> </xsl:text><xsl:value-of select="$molcas:Incomplete"/>
          </xsl:if>                           
                              
                                                  

.. [2]
   string ``molcas:getMethods`` node\* ``modules`` node ``ksdft`` node ``wavespecs``

   .. code:: xml

                                  
          $modules    Array with all executed module names 
          $ksdft      Module from <module cmlx:templateRef="scf-ksdft" > 
          $wavespecs  Entire <module cmlx:templateRef="wave.specs" > module                             
                     
          
              <xsl:param name="modules"/>
              <xsl:param name="ksdft" />
              <xsl:param name="wavespecs" />

              <xsl:variable name="isCASSCF" select="
                  if(exists($wavespecs) and contains($modules,$molcas:RASSCFmodule) and ($wavespecs/cml:scalar[@dictRef='m:ras1holes'] = '0') and ($wavespecs/cml:scalar[@dictRef='m:ras3holes'] = 0)) then
                      true()                
                  else
                      false()"/>
              <xsl:variable name="isRASSCF" select="
                  if(contains($modules,$molcas:RASSCFmodule)) then
                      true()
                  else
                      false()"/>      
              
              <xsl:variable name="moduleArray">
                  <xsl:for-each select="$modules">                
                      <xsl:value-of select="concat(upper-case(string(.)),'|')"/>
                  </xsl:for-each>
              </xsl:variable>
              
              <xsl:for-each select="distinct-values(tokenize($moduleArray/text(),'[|]+'))">
                  <xsl:if test="matches(.,$molcas:methodsRegex)">
                      <xsl:choose>
                          <xsl:when test="exists($ksdft) and matches(.,$molcas:SCFmodule)">
                              <xsl:choose>
                                  <xsl:when test="matches($ksdft,$molcas:SCFmodule)">
                                      <xsl:text>HF </xsl:text>
                                  </xsl:when>
                                  <xsl:otherwise>
                                      <xsl:text>DFT </xsl:text>
                                  </xsl:otherwise>
                              </xsl:choose>
                          </xsl:when>
                          <xsl:when test="matches(.,$molcas:RASSCFmodule)">                        
                              <xsl:choose>
                                  <xsl:when test="$isCASSCF">
                                      <xsl:value-of select="$molcas:CASSCFmodule"/><xsl:text> </xsl:text>
                                  </xsl:when>
                                  <xsl:otherwise>
                                      <xsl:value-of select="."/><xsl:text> </xsl:text>
                                  </xsl:otherwise>
                              </xsl:choose>
                          </xsl:when>
                          <xsl:when test="matches(.,$molcas:CASPT2module)">
                              <xsl:choose>
                                  <xsl:when test="not($isCASSCF) and $isRASSCF">
                                      <xsl:value-of select="$molcas:RASPT2module"/><xsl:text> </xsl:text>
                                  </xsl:when>
                                  <xsl:otherwise>
                                      <xsl:value-of select="."/><xsl:text> </xsl:text>
                                  </xsl:otherwise>
                              </xsl:choose>
                          </xsl:when>
                          <xsl:otherwise>
                              <xsl:value-of select="."/><xsl:text> </xsl:text>
                          </xsl:otherwise>
                      </xsl:choose>
                  </xsl:if>           
              </xsl:for-each>              
                              
                                                  

.. _program.header template: ../codes/molcas/module.header-d3e24615.html
.. _symmetry: ../codes/molcas/symmetry-d3e27358.html
.. _molcharge: #molcharge
.. _mulliken: ../codes/molcas/mulliken-d3e27026.html
.. _wave.specs: ../codes/molcas/wave.specs-d3e25170.html
.. _scf-ksdft: ../codes/molcas/scf-ksdft-d3e26443.html
.. _pcm: ../codes/molcas/pcm-d3e25264.html
.. _kirkwood: ../codes/molcas/kirkwood-d3e25314.html
.. _seward.generate: ../codes/molcas/seward.generate-d3e25361.html
.. _coordinates: ../codes/molcas/coordinates-d3e24944.html
.. _constraint: ../codes/molcas/constraint-d3e28899.html
.. _orbital.specs: ../codes/molcas/orbital.specs-d3e26519.html
.. _ci.expansion: ../codes/molcas/ci.expansion-d3e26784.html
.. _wave.printout: ../codes/molcas/wave.printout-d3e25425.html
.. _properties: ../codes/molcas/properties-d3e27471.html
.. _loprop: ../codes/molcas/loprop-d3e27647.html
.. _final.caspt2: ../codes/molcas/final.caspt2-d3e28167.html
.. _cchc: ../codes/molcas/cchc-d3e29122.html
.. _ccsdt: #ccsdt
.. _extras: ../codes/molcas/extras-d3e27711.html
.. _vibrations: ../codes/molcas/vibrations-d3e28687.html
.. _atom.expansion: ../codes/molcas/atom.expansion-d3e29191.html
.. _dynamic.loprop: ../codes/molcas/dynamic.loprop-d3e29307.html
