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
   | Author                                                                                                                | *Username fullname*                                                                                                  | Alvarez Moreno, Moises                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | C 8 H 12 N 8 O 2                                                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic                                                                                                         | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | Custom logic                                                                                                         | RASSCF RASPT2                                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

|image0|

 [1]_

 [2]_

Atomics and Basis Sets
----------------------

After header section, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms, basis used and contraction.

In geometry optimizations calculations, next to geometry section header there will appear the word **(optimized)**, pointing that this geometry is the last one from all optimization steps and has converged.

If the geometry optimization did not converge, there will appear the phrase **(calculation did not converge)**.

|image1|

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

Symmetry information
~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`symmetry`_'>

|image2|

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

|image3|

Solvation input
~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`pcm`_'>

Data source: <module cmlx:templateRef='`kirkwood`_'>

|image4|

Integrals
~~~~~~~~~

Data source: <module cmlx:templateRef='`seward.generate`_'>

|image5|

Bond distances
~~~~~~~~~~~~~~

Data source (to read molecule and calculate bonds): <module cmlx:templateRef='`coordinates`_'>

|image6|

Restrictions in the Geometry Optimization
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`constraint`_'>

|image7|

Modules
-------

Wave function specification
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`wave.specs`_'>

|image8|

Orbital specifications
~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`orbital.specs`_'>

|image9|

CI expansion specifications
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`ci.expansion`_'>

|image10|

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`wave.printout`_'>

|image11|

Wave functions / Weights of the most important CSFs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source <module cmlx:templateRef='`wave.printout`_'>

|image12|

Natural Occupation numbers
~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`wave.printout`_'>, module "natural"

|image13|

Mulliken Spin Population
~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`mulliken`_'>, submodule "mulliken.spin"

|image14|

Electrostatic moments
~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`properties`_">

|image15|

Population analysis / Mulliken atomic charges
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`loprop`_">

Data source: <module cmlx:templateRef="`mulliken`_">

|image16|

|image17|

Single-State CASPT2
~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`final.caspt2`_">

|image18|

Final energy
~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`scf-ksdft`_"> scalar dictRef='m:scfener'

Data source: <module cmlx:templateRef="`cchc`_"> scalar dictRef='m:e2mp2energy'

Data source: <module cmlx:templateRef="`cchc`_"> scalar dictRef='m:e2ccsdenergy'

Data source: <module cmlx:templateRef="`ccsdt`_"> scalar dictRef='m:ccsdtcorrenergy'

|image19|

|image20|

HZERO
~~~~~

Data source: <module cmlx:templateRef="`extras`_">

|image21|

Harmonic frequencies
~~~~~~~~~~~~~~~~~~~~

This module also allows displaying harmonic frequency intensities on a customizable chart.

Data source: <module cmlx:templateRef='`vibrations`_'>

|image22|

|image23|

IR spectrum / Vibrational frequencies
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`vibrations`_'>

This module will display JSpecView + JSmol plugins (using javascript libraries) working together to represent molecule IR spectrum.

|image24|

Multipole Expansion Analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Data source:<module cmlx:templateRef="`atom.expansion`_">

|image25|

LoProp Analysis
~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`dynamic.loprop`_'>

|image26|

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
                              
                              

.. _program.header template: ../codes/molcas/module.header-d3e19941.html
.. _symmetry: ../codes/molcas/symmetry-d3e22684.html
.. _molcharge: #molcharge
.. _mulliken: ../codes/molcas/mulliken-d3e22352.html
.. _wave.specs: ../codes/molcas/wave.specs-d3e20496.html
.. _scf-ksdft: ../codes/molcas/scf-ksdft-d3e21769.html
.. _pcm: ../codes/molcas/pcm-d3e20590.html
.. _kirkwood: ../codes/molcas/kirkwood-d3e20640.html
.. _seward.generate: ../codes/molcas/seward.generate-d3e20687.html
.. _coordinates: ../codes/molcas/coordinates-d3e20270.html
.. _constraint: ../codes/molcas/constraint-d3e24225.html
.. _orbital.specs: ../codes/molcas/orbital.specs-d3e21845.html
.. _ci.expansion: ../codes/molcas/ci.expansion-d3e22110.html
.. _wave.printout: ../codes/molcas/wave.printout-d3e20751.html
.. _properties: ../codes/molcas/properties-d3e22797.html
.. _loprop: ../codes/molcas/loprop-d3e22973.html
.. _final.caspt2: ../codes/molcas/final.caspt2-d3e23493.html
.. _cchc: ../codes/molcas/cchc-d3e24448.html
.. _ccsdt: #ccsdt
.. _extras: ../codes/molcas/extras-d3e23037.html
.. _vibrations: ../codes/molcas/vibrations-d3e24013.html
.. _atom.expansion: ../codes/molcas/atom.expansion-d3e24517.html
.. _dynamic.loprop: ../codes/molcas/dynamic.loprop-d3e24633.html

.. |image0| image:: /imgs/MOLCAS_header.png
.. |image1| image:: /imgs/MOLCAS_geometry.png
.. |image2| image:: /imgs/MOLCAS_symmetry.png
.. |image3| image:: /imgs/MOLCAS_molecularinfo.png
.. |image4| image:: /imgs/MOLCAS_solvation.png
.. |image5| image:: /imgs/MOLCAS_sewardgenerate.png
.. |image6| image:: /imgs/MOLCAS_bonddistances.png
.. |image7| image:: /imgs/MOLCAS_restrictions.png
.. |image8| image:: /imgs/MOLCAS_module_wavefunction.png
.. |image9| image:: /imgs/MOLCAS_module_orbitalspecs.png
.. |image10| image:: /imgs/MOLCAS_module_ciexpansion.png
.. |image11| image:: /imgs/MOLCAS_module_energies.png
.. |image12| image:: /imgs/MOLCAS_module_wavefunctioncsf.png
.. |image13| image:: /imgs/MOLCAS_module_natural.png
.. |image14| image:: /imgs/MOLCAS_module_mullikenspin.png
.. |image15| image:: /imgs/MOLCAS_module_electrostaticmoments.png
.. |image16| image:: /imgs/MOLCAS_module_loprop.png
.. |image17| image:: /imgs/MOLCAS_module_mulliken.png
.. |image18| image:: /imgs/MOLCAS_module_singlestate_caspt2.png
.. |image19| image:: /imgs/MOLCAS_module_finalenergy.png
.. |image20| image:: /imgs/MOLCAS_module_finalenergy2.png
.. |image21| image:: /imgs/MOLCAS_module_hzero.png
.. |image22| image:: /imgs/MOLCAS_module_harmonicfreq.png
.. |image23| image:: /imgs/MOLCAS_module_harmonicfreq2.png
.. |image24| image:: /imgs/MOLCAS_module_frequencies.png
.. |image25| image:: /imgs/MOLCAS_module_multipoleexpansion.png
.. |image26| image:: /imgs/MOLCAS_module_loprop_analysis.png
