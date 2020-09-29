Gaussian
========

General Info
------------

.. table:: Gaussian - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/1722                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | <scalar dictRef="`cc:program`_">                                                                                     | Gaussian 09                                                                                                                                                   |
   |                                                                                                                       |                                                                                                                      |                                                                                                                                                               |
   |                                                                                                                       | <scalar dictRef="`cc:program <#../codes/gaussian/l1.end-d3e6808.html>`__">                                           |                                                                                                                                                               |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Alvarez Moreno, Moises                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | H 1 O 40 P 1 Ti 1 W 11                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic                                                                                                         | Geometry optimization Minimum                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                                                                                                                | DFT                                                                                                                  | DFT                                                                                                                                                           |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: Gaussian - General Info with additional fields (if `thermochemistry`_ module exists)

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Sample value                                                                                                                       |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Temperature                                                                                                                        | <scalar dictRef="`cc:temp`_">                                                                                                      | 298.15 K                                                                                                                           |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Pressure                                                                                                                           | <scalar dictRef="`cc:press`_">                                                                                                     | 1.0 atm                                                                                                                            |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

|image0|

|image1|

 [1]_

Atoms and Basis Sets
--------------------

After header section, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms, `basis used and core`_, or simply `basis`_.

In geometry optimizations calculations, next to geometry section header there will appear the word **(optimized)**, pointing that this geometry is the last one from all optimization steps and has converged.

If the geometry optimization did not converge, there will appear the phrase **(calculation did not converge)**.

If there are multiple geometries we'll capture it's last appearance.

|image2|

|image3|

|image4|

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

.. table:: Molecular Info - Main fields

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Description                                                                                                                        |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Multiplicity                                                                                                                       | Appears in                                                                                                                         |                                                                                                                                    |
   |                                                                                                                                    |                                                                                                                                    |                                                                                                                                    |
   |                                                                                                                                    | -  qmm module <array dictRef="`g:multiplicity`_">                                                                                  |                                                                                                                                    |
   |                                                                                                                                    |                                                                                                                                    |                                                                                                                                    |
   |                                                                                                                                    | -  `l101.zmat module`_                                                                                                             |                                                                                                                                    |
   |                                                                                                                                    |                                                                                                                                    |                                                                                                                                    |
   |                                                                                                                                    | -  `l101.zmata module`_                                                                                                            |                                                                                                                                    |
   |                                                                                                                                    |                                                                                                                                    |                                                                                                                                    |
   |                                                                                                                                    | -  l9999.archive module <scalar @dictRef='`x:spinMultiplicity`_'>                                                                  |                                                                                                                                    |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Charge                                                                                                                             | It can appear on same places that multiplicity field and also in `l9999.archive module`_                                           |                                                                                                                                    |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | QMMM                                                                                                                               | <module cmlx:templateRef="`l101.qmmm`_">                                                                                           |                                                                                                                                    |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Frozen section                                                                                                                     | <module cmlx:templateRef="`l101.modredundant`_">                                                                                   |                                                                                                                                    |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Point group                                                                                                                        | <module cmlx:templateRef="`l202.stoich`_">                                                                                         |                                                                                                                                    |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Solvation                                                                                                                          | <module cmlx:templateRef="`l301.pcm.standard`_">                                                                                   | Solvation parameters                                                                                                               |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

|image5|

|image6|

Modules
-------

Energies
~~~~~~~~

Data source: <scalar dictRef='`g:rbhflyp`_'>

Data source: <scalar dictRef='`cc:dispenergy`_'>

Data source: <module cmlx:templateRef='`l120`_'>

Data source: <module cmlx:templateRef='`l122`_'>

Data source: <module cmlx:templateRef='`l716.zeropoint`_'>

Data source: <module cmlx:templateRef='`l9999.archive`_'>

|image7|

|image8|

Spin
~~~~

Data source: <module cmlx:templateRef='`l601.mullikenspin`_'>

Data source: <scalar dictRef='`cc:spincontamination`_'>

|image9|

IR spectrum
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`l716.freq.chunkx`_'>

This module will display JSpecView + JSmol plugins (using javascript libraries) working together to represent molecule IR spectrum.

|image10|

Mulliken atomic charges
~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`mulliken`_'>

|image11|

Dipole / Multipole moment
~~~~~~~~~~~~~~~~~~~~~~~~~

Data source: <module cmlx:templateRef="`multipole`_">

|image12|

.. [1]
   string ``gaussian:getCalcType`` boolean ``isOptimization`` boolean ``hasStationaryPoint`` boolean ``hasMinimum``

   .. code:: xml

                                      
          $isOptimization       Exists module <module cmlx:templateRef="l103" > ?
          $hasStationaryPoiny   'Stationary point found' appears in <module cmlx:templateRef="l103.optimizedparam" > ?
          $hasMinimum           'Search for a local minimum' appears in <module cmlx:templateRef="l103.localminsaddle" > ?                               
                     
          
          <!-- Calculation type related constants -->
          <xsl:variable name="calcType" select="if($isOptimization) then 'Geometry optimization' else 'Single point'"/>       
              <xsl:choose>
                  <xsl:when test="$hasStationaryPoint">
                      <xsl:variable name="hasMinimum" select="if($hasMinimum) then ' Minimum' else ' TS'"/>
                      <xsl:sequence select="concat($calcType, ' ' , $hasMinimum)"/>
                  </xsl:when>
                  <xsl:otherwise>
                      <xsl:sequence select="concat($calcType, ' Structure')"/>
                  </xsl:otherwise>
              </xsl:choose>                          
           
                              

.. _`cc:program`: ../codes/gaussian/jobcpu-d3e18437.html
.. _thermochemistry: ../codes/gaussian/l716.thermochemistry-d3e15561.html
.. _`cc:temp`: ../codes/gaussian/l716.thermochemistry.temperature-d3e15571.html
.. _`cc:press`: ../codes/gaussian/l716.thermochemistry.temperature-d3e15571.html
.. _basis used and core: ../codes/gaussian/l301.basis2-d3e12816.html
.. _basis: ../codes/gaussian/l301.basis-d3e12527.html
.. _`g:multiplicity`: ../codes/gaussian/l101.qmmm-d3e7175.html
.. _l101.zmat module: ../codes/gaussian/l101.zmat-d3e7651.html
.. _l101.zmata module: ../codes/gaussian/l101.zmata-d3e7734.html
.. _`x:spinMultiplicity`: ../codes/gaussian/l9999.archive-d3e17754.html
.. _l9999.archive module: ../codes/gaussian/l9999.archive-d3e17754.html
.. _l101.qmmm: ../codes/gaussian/l101.qmmm-d3e7175.html
.. _l101.modredundant: ../codes/gaussian/l101.modredundant-d3e8119.html
.. _l202.stoich: ../codes/gaussian/l202.stoich-d3e12429.html
.. _l301.pcm.standard: ../codes/gaussian/l301.pcm.standard-d3e13579.html
.. _`g:rbhflyp`: ../codes/gaussian/l502.footer-d3e14359.html
.. _`cc:dispenergy`: ../codes/gaussian/l502.pcm-d3e14499.html
.. _l120: ../codes/gaussian/l120-d3e12162.html
.. _l122: ../codes/gaussian/l122-d3e17537.html
.. _l716.zeropoint: ../codes/gaussian/l716.zeropoint-d3e15245.html
.. _l9999.archive: ../codes/gaussian/l9999.archive-d3e17754.html
.. _l601.mullikenspin: ../codes/gaussian/l601.mullikenspin-d3e10134.html
.. _`cc:spincontamination`: ../codes/gaussian/l502.footer2-d3e14540.html
.. _l716.freq.chunkx: ../codes/gaussian/l716.freq.chunkx-d3e14884.html
.. _mulliken: ../codes/gaussian/mulliken-d3e10094.html
.. _multipole: ../codes/gaussian/multipole-d3e10263.html

.. |image0| image:: /imgs/GAUSSIAN_header.png
.. |image1| image:: /imgs/GAUSSIAN_header2.png
.. |image2| image:: /imgs/GAUSSIAN_geometry.png
.. |image3| image:: /imgs/GAUSSIAN_geometry2.png
.. |image4| image:: /imgs/GAUSSIAN_geometry3.png
.. |image5| image:: /imgs/GAUSSIAN_molecularinfo.png
.. |image6| image:: /imgs/GAUSSIAN_molecularinfo2.png
.. |image7| image:: /imgs/GAUSSIAN_module_energies.png
.. |image8| image:: /imgs/GAUSSIAN_module_energies1.png
.. |image9| image:: /imgs/GAUSSIAN_module_l601_mullikenspin.png
.. |image10| image:: /imgs/GAUSSIAN_module_frequencies.png
.. |image11| image:: /imgs/GAUSSIAN_module_mulliken.png
.. |image12| image:: /imgs/GAUSSIAN_module_dipole_moment.png
