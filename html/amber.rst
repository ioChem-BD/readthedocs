Amber
=====

For this specific format, the most relevant information is the trajectory file in its NetCDF binary form (.nc), mandatory on all uploads. ioChem-BD won't render such files but keep them inside the platform for its later download.

General Info
------------

.. table:: Amber - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/5672                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `header`_ template                                                                                                   | Amber 18                                                                                                                                                      |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Molecular Dynamics (NPT)                                                                                                                                      |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/AMBER_header.png

Settings
--------

This section captures initialization settings like starting time, timestep used, pressure and temperature regulation, etc.

Data source: <module cmlx:templateRef='`control`_'>

.. image:: /imgs/AMBER_settings.png

Atomic coordinates
------------------

After settings, our HTML resume will output a coordinates table with current molecule atoms and its cell dimensions.

For every atom, we will output it's serial number, atom type, coordinates in cartesian and fractional modes, in angstroms.

Information its read from `parameter/topology`_ file specification and `trajectory restart`_ file. Solvent atoms will be discarded.

.. image:: /imgs/AMBER_geometry.png

Modules
-------

Averages
~~~~~~~~

Data sources:

-  <module cmlx:templateRef='`averages`_'>

-  <module cmlx:templateRef='`results`_'>

.. image:: /imgs/AMBER_module_averages.png

Timing
~~~~~~

Data source: <module cmlx:templateRef='`timing`_'>

.. image:: /imgs/AMBER_module_timing.png

.. [1]
   string ``amber:getMethod`` string ``imin`` string ``ntt`` string ``ntp``

   .. code:: xml
      :number-lines:

          $imin  Variable imin from module <module cmlx:templateRef="control" >
          $ntt  Variable ntt from module <module cmlx:templateRef="control" > 
          $ntp  Variable ntp from module <module cmlx:templateRef="control" >  
                     
          <!-- Calculation type related constants -->                
          <xsl:variable name="am:GeometryOptimization">Geometry optimization</xsl:variable>
          <xsl:variable name="am:npt">NPT</xsl:variable>
          <xsl:variable name="am:nvt">NVT</xsl:variable>
          <xsl:variable name="am:nve">NVE</xsl:variable> 
          
          <xsl:param name="imin" />
          <xsl:param name="ntp" />
          <xsl:param name="ntt" />
          
          <xsl:choose>
              <xsl:when test="exists($imin) and number($imin) = 1">                
                  <xsl:value-of select="$am:GeometryOptimization" />
              </xsl:when>
              <xsl:when test="exists($ntp) and number($ntp) &gt; 0">
                  <xsl:value-of select="$am:npt"/>
              </xsl:when>            
              <xsl:otherwise>
                  <xsl:choose>
                      <xsl:when test="exists($ntt) and number($ntt) = 0">
                          <xsl:value-of select="$am:nve"/>
                      </xsl:when>
                      <xsl:otherwise>
                          <xsl:value-of select="$am:nvt"/>
                      </xsl:otherwise>
                  </xsl:choose>
              </xsl:otherwise>
          </xsl:choose>                
                              
                                                  

.. _header: ../codes/amber/header-d3e9530.html
.. _control: ../codes/amber/control-d3e9761.html
.. _parameter/topology: ../codes/amber/amber.parm-d3e51136.html
.. _trajectory restart: ../codes/amber/amber.nctraj-d3e51282.html
.. _averages: ../codes/amber/averages-d3e10062.html
.. _results: ../codes/amber/results-d3e10221.html
.. _timing: ../codes/amber/timing-d3e10357.html
