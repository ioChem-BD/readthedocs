GROMACS
=======

For this specific format, the most relevant information is the trajectory file in its binary form (.xtc), mandatory on all uploads. ioChem-BD won't render such files but keep them inside the platform for its later download.

General Info
------------

.. table:: GROMACS - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/5672                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `program.header template`_                                                                                           | GROMACS 5.0.2                                                                                                                                                 |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Fixed value (method used)  [1]_                                                                                      | Molecular Dynamics (NPT)                                                                                                                                      |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/GROMACS_header.png

Settings
--------

This section captures initialization settings like starting time, timestep used, coupling groups, etc.

Data source: <module cmlx:templateRef='`input.parameters`_'>

.. image:: /imgs/GROMACS_settings.png

Atomic coordinates
------------------

After settings, our HTML resume will output a xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms.

Information its read from `molecular structure file.`_

.. image:: /imgs/GROMACS_geometry.png

Modules
-------

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`averages`_'>

.. image:: /imgs/GROMACS_module_energies.png

Timing
~~~~~~

Data sources:

-  <module cmlx:templateRef='`hardware`_'>

-  <module cmlx:templateRef='`summary`_'>

-  <module cmlx:templateRef='`accounting`_'>

.. image:: /imgs/GROMACS_module_timing.png

.. [1]
   string ``gromacs:getCalcType`` string ``tcoupl`` string ``pcoupl``

   .. code:: xml
      :number-lines:

                                 
          $tcoupl  Variable tcoupl from module <module cmlx:templateRef="input" > 
          $pcoupl  Variable pcoupl from module <module cmlx:templateRef="input" >  
                     
          <!-- Calculation type related constants -->                
          <xsl:variable name="gm:npt">NPT</xsl:variable>
          <xsl:variable name="gm:nvt">NVT</xsl:variable>
          <xsl:variable name="gm:nve">NVE</xsl:variable>
          
          <xsl:param name="tcoupl"  />
          <xsl:param name="pcoupl" />        
          
          <xsl:choose>
              <xsl:when test="not(exists($pcoupl)) or lower-case(gm:trim($pcoupl/text())) = 'no'">
                  <xsl:choose>
                      <xsl:when test="not(exists($tcoupl)) or lower-case(gm:trim($tcoupl/text())) = 'no'">
                          <xsl:value-of select="$gm:nve"/>
                      </xsl:when>
                      <xsl:otherwise>
                          <xsl:value-of select="$gm:nvt"/>                        
                      </xsl:otherwise>
                  </xsl:choose>
              </xsl:when>
              <xsl:otherwise>
                  <xsl:value-of select="$gm:npt"/>
              </xsl:otherwise>
          </xsl:choose>                 
                              
                              

.. _program.header template: ../codes/gromacs/header-d3e26582.html
.. _input.parameters: ../codes/gromacs/input.parameters-d3e26725.html
.. _molecular structure file.: ../codes/gromacs/gromacs.geometry-d3e52489.html
.. _averages: ../codes/gromacs/averages-d3e27311.html
.. _hardware: ../codes/gromacs/hardware-d3e27169.html
.. _summary: ../codes/gromacs/summary-d3e27724.html
.. _accounting: ../codes/gromacs/accounting-d3e27649.html
