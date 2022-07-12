Vasp
====

Header
------

.. table:: VASP - General Info - Main fields

   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Field                                                                                                                 | Source                                                                                                               | Sample value                                                                                                                                                  |
   +=======================================================================================================================+======================================================================================================================+===============================================================================================================================================================+
   | Title                                                                                                                 | *Set on Browse calculation publication*                                                                              | Sample calculation                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Browse Item                                                                                                           | *URL pointing Browse published item*                                                                                 | https://iochem-bd.iciq.es/browse/handle/100/1722                                                                                                              |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Program                                                                                                               | <scalar dictRef="`cc:program`_"> template                                                                            | VASP 5.3.2                                                                                                                                                    |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Author                                                                                                                | *Username fullname*                                                                                                  | Doe, John                                                                                                                                                     |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | C 1 H 4 Mo 30 O 61                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic  [1]_                                                                                                   | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Functional                                                                                                            | Custom logic  [2]_                                                                                                   | PBE+U                                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Shell type (ISPIN)                                                                                                    | <scalar dictRef="`v:ispin`_">                                                                                        | Open Shell                                                                                                                                                    |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Temperature                                                                                                           | <scalar dictRef="`cc:temp`_">                                                                                        | 0.0K                                                                                                                                                          |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. image:: /imgs/VASP_header.png

Settings
--------

Most relevant calculation input parameters. Almost all information fields come from <module cmlx:templateRef="`incar`_">

-  SIGMA

-  ISMEAR

-  LDIPOL

-  IDIPOL

-  Multiplicity

-  NELECT

-  Cut-Off Energy

-  EDIFF

-  EDDIFG

-  POTIM

-  LDAU (LDAUL, LDAUU, LDAUJ)

-  VDW and VDW Version

-  Parameters for Grimme's potential <module cmlx:templateRef="`grimmes`_">

.. image:: /imgs/VASP_settings.png

Atoms info
----------

After settings section, our HTML resume will output cell coordinates, lattice vectors and a coordinates table with molecule atoms.

Initial geometry its readed from OUTCAR file using: <module cmlx:templateRef="`position`_">, <module cmlx:templateRef="`incar`_">, <module cmlx:templateRef="`potcar`_"> and <module cmlx:templateRef="`laticce`_">

Final geometry will be generated using the same modules than Initial geometry, but coordinates will come from last instance of <module cmlx:templateRef="`calculated.position`_">

For every atom, we will output it's serial number, atom type, cartesian and fractional coordinates (in angstroms) , and `basis used`_.

.. image:: /imgs/VASP_geometry.png

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

K-point generation parameters readed form `KPOINTS file`_

.. image:: /imgs/VASP_molecularinfo.png

Modules
-------

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`energy`_'>

This module will hold Free ,E0 , dE and E-fermi energies.

In case of single calculations (single point, geometry optimization), a table with this values will be displayed.

.. image:: /imgs/VASP_module_energies_single.png
   :alt:  Energies (single calculation)

On Molecular Dynamics calculations, a table with energy and force progression will appear along with a plot of such values.

.. image:: /imgs/VASP_module_energies_md.png

.. image:: /imgs/VASP_module_energies_md2.png

On multiple OUTCAR calculations like Nudge Elastic Band (NEB) or Dimmer, a graphic will be printed with each diferential energy as step.

.. image:: /imgs/VASP_module_energies_multiple.png

Eigenvalues
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`eigenvalues`_'>

This module will display eigenvalues per spin and kpoint.

.. image:: /imgs/VASP_module_eigenvalues.png

DOS
~~~

Data source: DOSCAR file <module cmlx:templateRef='`vasp.doscar`_'>

On calculations where VASP DOSCAR file has been uploaded, a form will be displayed to configure a graph with the Density Of States (DOS) information

In this form we will can select atoms by index, range or atom type, select spin and molecular orbitals. Once all parameters have been set we will add this line to current graph. We can define/delete as much DOS lines as we need.

.. image:: /imgs/VASP_module_dos.png

Magnetization
~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`magnetization`_'>

.. image:: /imgs/VASP_module_magnetization.png

Vibrations
~~~~~~~~~~

Data source: <module cmlx:templateRef='`vibrations`_'>

.. image:: /imgs/VASP_module_vibration.png

Structure
~~~~~~~~~

Lattice replication

.. image:: /imgs/VASP_module_structure.png

.. [1]
   string ``vasp:getCalcType`` nodeset ``ibrion``

   .. code:: xml

          ibrion                   Value of ibrion parameter on <module cmlx:templateRef="convergence.info" >.       
                     
              <xsl:param name="ibrion"/>
                  <xsl:choose>
                      <xsl:when test="count($ibrion) > 1 and exists($ibrion[text() = '44'])"><xsl:value-of select="$vasp:ImprovedDimerMethod"/></xsl:when>
                      <xsl:when test="count($ibrion) > 1"><xsl:value-of select="$vasp:NudgedElasticBand"/></xsl:when>
                      <xsl:otherwise>
                          <xsl:choose>
                              <xsl:when test="$ibrion = -1"><xsl:value-of select="$vasp:SinglePoint"/></xsl:when>
                              <xsl:when test="$ibrion = 0"><xsl:value-of select="$vasp:MolecularDynamics"/></xsl:when>
                              <xsl:when test="$ibrion &gt; 0 and $ibrion &lt; 4"><xsl:value-of select="$vasp:GeometryOptimization"/></xsl:when>
                              <xsl:when test="$ibrion &gt; 4 and $ibrion &lt; 9"><xsl:value-of select="$vasp:FrequencyCalculus"/></xsl:when>
                              <xsl:when test="$ibrion = 44"><xsl:value-of select="$vasp:ImprovedDimerMethod"/></xsl:when>
                              <xsl:otherwise><xsl:value-of select="$vasp:NotAvailable"/></xsl:otherwise>
                          </xsl:choose>                                
                      </xsl:otherwise>
                  </xsl:choose>
           
                                                  

.. [2]
   string ``turbo:getMehod`` string ``gga`` boolean ``lhfcalc`` number ``hfscreen`` number ``aggac`` boolean ``luseVdw`` number ``zabVdw`` number ``param1``> number ``param2`` boolean ``ldau``

   .. code:: xml

       
              gga, lhfcalc, hfscreen , ...           parameters readed from OUTCAR file <module cmlx:templateRef="incar">                                      
                                  
           <xsl:param name="gga"/>
           <xsl:param name="lhfcalc"/>
             
           <xsl:param name="aggac"/>         
           <xsl:param name="hfscreen"/>        
           <xsl:param name="luseVdw"/>
           <xsl:param name="zabVdw"/>
           <xsl:param name="param1"/>
           <xsl:param name="param2"/>        
           <xsl:param name="ldau"/>
           <xsl:choose>
                   <xsl:when test="compare($lhfcalc,'true')=0">
                          <xsl:choose>
                              <xsl:when test="$hfscreen=0.2">HSE06</xsl:when>
                              <xsl:otherwise>HSE03</xsl:otherwise>                        
                          </xsl:choose>
                   </xsl:when>
                   <xsl:when test="compare($luseVdw , 'true')=0 and $aggac = 0.0">
                       <xsl:choose>
                           <xsl:when test="compare($gga,'RE')=0">vdW-DF</xsl:when>
                           <xsl:when test="compare($gga,'OR')=0">optPBE-vdW</xsl:when>
                           <xsl:when test="compare($gga,'BO')=0 and round($param1 * 1000) div 1000 = 0.183 and round($param2 * 100) div 100 = 0.22">optB88-vdW</xsl:when>
                           <xsl:when test="compare($gga,'MK')=0 and round($param1 * 10000) div 10000 = 0.1234 and $param2 = 1.0">optB86d-vdW</xsl:when>
                           <xsl:when test="compare($gga,'ML')=0 and $zabVdw = -1.8867">vdW-DF2</xsl:when>
                           <xsl:otherwise>N/A</xsl:otherwise>
                       </xsl:choose>
                   </xsl:when> 
                   <xsl:when test="compare($gga,'91')=0">PW91</xsl:when>
                   <xsl:when test="compare($gga,'PE')=0">PBE</xsl:when>
                   <xsl:when test="compare($gga,'RP')=0">rPBE</xsl:when>
                   <xsl:when test="compare($gga,'AM')=0">AM05</xsl:when>
                   <xsl:when test="compare($gga,'PS')=0">PBEsol</xsl:when>                          
                   <xsl:otherwise>N/A</xsl:otherwise>             
               </xsl:choose>
               <xsl:if test="compare($ldau,'true')=0">
                   <xsl:text>+U</xsl:text>
               </xsl:if>         
                                  
                                                  

.. _`cc:program`: ../codes/vasp/generator-d3e41528.html
.. _`v:ispin`: ../codes/vasp/incar-d3e41578.html
.. _`cc:temp`: ../codes/vasp/incar-d3e41578.html
.. _incar: ../codes/vasp/incar-d3e41578.html
.. _grimmes: ../codes/vasp/grimmes-d3e43063.html
.. _position: ../codes/vasp/position-d3e42270.html
.. _potcar: ../codes/vasp/potcar-d3e42142.html
.. _laticce: ../codes/vasp/lattice-d3e42230.html
.. _calculated.position: ../codes/vasp/calculated.position-d3e42414.html
.. _basis used: ../codes/vasp/atom.potcar-d3e42150.html
.. _KPOINTS file: ../codes/vasp/vasp.kpoints-d3e52234.html
.. _energy: ../codes/vasp/energy-d3e42653.html
.. _eigenvalues: ../codes/vasp/eigenvalues-d3e42889.html
.. _vasp.doscar: ../codes/vasp/vasp.doscar-d3e52275.html
.. _magnetization: ../codes/vasp/magnetization-d3e42752.html
.. _vibrations: ../codes/vasp/vibrations-d3e42587.html
