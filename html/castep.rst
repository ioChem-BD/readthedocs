CASTEP
======

For this specific format, the minimum required files are:

-  A user defined **input file** *(.param)*.

-  A **cell file** *(.cell)*, with the atomic cooordinates, cell dimensions and kpoints used in the calculation.

-  The generated resume **output file** *(.castep)*.

.. note::

   CASTEP allows to change the default units used inside the calculation and printed in its output file. The current ioChem-BD release supports the default units only.

   The geometry optimization method used must be BFGS, the default one. Damped molecular dynamics optimizations are not supported.

   Geometry optimization calculations generate a *.geom* file that **must be also appended when uploading it to ioChem-BD**, otherwise the optimized geometry won't be available in the final resume.

   All generated CASTEP graph files *.xcd* can be attached to the upload process and its content will be rendered in the final resume.

General Info
------------

.. table:: CASTEP - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/5672                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | `program.header template`_                                                                                           | CASTEP 2021 HF1                                                                                                                                               |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/CASTEP_header.png

Settings
--------

This section captures initialization settings like units used, geometry optimization parameters, exchange correlation parameters, etc.

Data source: <module cmlx:templateRef='`parameters`_'>

.. image:: /imgs/CASTEP_settings.png

Atomic coordinates
------------------

After settings, our HTML resume will output cell dimensions and an xyz coordinates table with current molecule atoms.

For every atom, we will output it's serial number, atom type, coordinates in angstroms in cartesian and fractional types.

Information is read from `geometry steps file`_ or from `atoms`_ section.

On geometry optimization calculations it will indicate if it converged along with the initial and final geometries.

.. image:: /imgs/CASTEP_geometry.png

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

.. table:: Molecular Info - Main fields

   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                              | Source                                                                                                                             | Description                                                                                                                        |
   +====================================================================================================================================+====================================================================================================================================+====================================================================================================================================+
   | Point group                                                                                                                        | <scalar dictRef="`cc:pointgroup`_">                                                                                                | Variable found inside Symmetry and Constraints section                                                                             |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | Space group                                                                                                                        | <scalar dictRef="`ca:spacegroup`_">                                                                                                | Variable found inside Symmetry and Constraints section                                                                             |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+
   | k-point                                                                                                                            | Read from `castep.cell`_                                                                                                           | K-point list and its weight, defined inside .cell file                                                                             |
   +------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/CASTEP_molecularinfo.png

Modules
-------

Energies
~~~~~~~~

Data source:

-  <module cmlx:templateRef='`step`_'>

-  <module cmlx:templateRef='`enthalpy`_'>

.. image:: /imgs/CASTEP_module_energies.png

Mulliken Atomic Charges
~~~~~~~~~~~~~~~~~~~~~~~

Data source:

-  <module cmlx:templateRef='`mulliken`_'>

.. image:: /imgs/CASTEP_module_mulliken.png

Graphs
~~~~~~

Data source:

-  .xcd files attached to the calculation during its upload.

It can contain geometry optimization step parameters, density of states or band gap graphs.

.. image:: /imgs/CASTEP_module_graph.png

.. image:: /imgs/CASTEP_module_graph2.png

.. image:: /imgs/CASTEP_module_graph3.png

Timing
~~~~~~

Data sources:

-  <module cmlx:templateRef='`timing`_'>

.. image:: /imgs/CASTEP_module_timing.png

.. [1]
   string ``ca:getCalcType`` string ``setup``

   .. code:: xml

                                 
          $setup          Refers to all read elements from <module cmlx:templateRef="parameters">                 
                     
          <xsl:variable name="ca:minimize">Geometry optimization</xsl:variable>
          <xsl:variable name="ca:spectroscopy">Electronic spectroscopy</xsl:variable>

          <xsl:function name="ca:getCalcType">
              <xsl:param name="setup"  /> 

              <xsl:variable name="type" select="ca:getParameter($setup, 'type of calculation')" />
              <xsl:choose>
                  <xsl:when test="matches($type, 'geometry optimization')">
                      <xsl:value-of select="$ca:minimize"/>
                  </xsl:when>
                  <xsl:when test="matches($type, 'Electronic Spectroscopy')">
                      <xsl:value-of select="$ca:spectroscopy"/>
                  </xsl:when>
                  <xsl:otherwise><xsl:text>N/A</xsl:text></xsl:otherwise>
              </xsl:choose>
          </xsl:function>

          <xsl:function name="ca:getParameter">
              <xsl:param name="setup" />
              <xsl:param name="name" />                      
              <xsl:copy-of select="$setup/cml:parameter/cml:scalar[@dictRef='x:label'][text()=$name]/following-sibling::cml:scalar[@dictRef='x:value']"/>                
          </xsl:function>

                              
                              

.. _program.header template: ../codes/castep/header-d3e10515.html
.. _parameters: ../codes/castep/parameters-d3e11096.html
.. _geometry steps file: ../codes/castep/castep.geom-d3e51486.html
.. _atoms: ../codes/castep/atoms-d3e10815.html
.. _`cc:pointgroup`: ../codes/castep/symmetry-d3e11041.html
.. _`ca:spacegroup`: ../codes/castep/symmetry-d3e11041.html
.. _castep.cell: ../codes/castep/castep.cell-d3e51189.html
.. _step: ../codes/castep/step-d3e11936.html
.. _enthalpy: ../codes/castep/enthalpy-d3e12239.html
.. _mulliken: ../codes/castep/mulliken-d3e12135.html
.. _timing: ../codes/castep/timing-d3e12273.html
