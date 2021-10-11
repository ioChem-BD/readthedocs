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
   | Author                                                                                                                | *Username fullname*                                                                                                  | Alvarez Moreno, Moises                                                                                                                                        |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Formula                                                                                                               | *Atom count from final geometry*                                                                                     | C 1 H 4 Mo 30 O 61                                                                                                                                            |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Calculation type                                                                                                      | Custom logic                                                                                                         | Geometry optimization                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Functional                                                                                                            | Custom logic                                                                                                         | PBE+U                                                                                                                                                         |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Shell type (ISPIN)                                                                                                    | <scalar dictRef="`v:ispin`_">                                                                                        | Open Shell                                                                                                                                                    |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Temperature                                                                                                           | <scalar dictRef="`cc:temp`_">                                                                                        | 0.0K                                                                                                                                                          |
   +-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

|image0|

 [1]_

 [2]_

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

|image1|

Atoms info
----------

After settings section, our HTML resume will output cell coordinates, lattice vectors and a coordinates table with molecule atoms.

Initial geometry its readed from OUTCAR file using: <module cmlx:templateRef="`position`_">, <module cmlx:templateRef="`incar`_">, <module cmlx:templateRef="`potcar`_"> and <module cmlx:templateRef="`laticce`_">

Final geometry will be generated using the same modules than Initial geometry, but coordinates will come from last instance of <module cmlx:templateRef="`calculated.position`_">

For every atom, we will output it's serial number, atom type, cartesian and fractional coordinates (in angstroms) , and `basis used`_.

|image2|

Molecular Info
--------------

This section captures molecule additional information not captured on previous section.

K-point generation parameters readed form `KPOINTS file`_

|image3|

Modules
-------

Energies
~~~~~~~~

Data source: <module cmlx:templateRef='`energy`_'>

This module will hold Free ,E0 , dE and E-fermi energies.

In case of single calculations (single point, geometry optimization), a table with this values will be displayed.

On multiple OUTCAR calculations like Nudge Elastic Band (NEB) or Dimmer, a graphic will be printed with each diferential energy as step.

|image4|

|image5|

Eigenvalues
~~~~~~~~~~~

Data source: <module cmlx:templateRef='`eigenvalues`_'>

This module will display eigenvalues per spin and kpoint.

|image6|

DOS
~~~

Data source: DOSCAR file <module cmlx:templateRef='`vasp.doscar`_'>

On calculations where VASP DOSCAR file has been uploaded, a form will be displayed to configure a graph with the Density Of States (DOS) information

In this form we will can select atoms by index, range or atom type, select spin and molecular orbitals. Once all parameters have been set we will add this line to current graph. We can define/delete as much DOS lines as we need.

|image7|

Magnetization
~~~~~~~~~~~~~

Data source: <module cmlx:templateRef='`magnetization`_'>

|image8|

Vibrations
~~~~~~~~~~

Data source: <module cmlx:templateRef='`vibrations`_'>

|image9|

Structure
~~~~~~~~~

Lattice replication

|image10|

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
                                  
                              

.. _`cc:program`: #generator
.. _`v:ispin`: #incar
.. _`cc:temp`: #incar
.. _incar: #incar
.. _grimmes: #grimmes
.. _position: #position
.. _potcar: #potcar
.. _laticce: #lattice
.. _calculated.position: #calculated.position
.. _basis used: #atom.potcar
.. _KPOINTS file: ../codes/from/vasp.kpoints-d3e41979.html
.. _energy: #energy
.. _eigenvalues: #eigenvalues
.. _vasp.doscar: ../codes/from/vasp.doscar-d3e42019.html
.. _magnetization: #magnetization
.. _vibrations: #vibrations

.. |image0| image:: /imgs/VASP_header.png
.. |image1| image:: /imgs/VASP_settings.png
.. |image2| image:: /imgs/VASP_geometry.png
.. |image3| image:: /imgs/VASP_molecularinfo.png
.. |image4| image:: /imgs/VASP_module_energies_single.png
.. |image5| image:: /imgs/VASP_module_energies_multiple.png
.. |image6| image:: /imgs/VASP_module_eigenvalues.png
.. |image7| image:: /imgs/VASP_module_dos.png
.. |image8| image:: /imgs/VASP_module_magnetization.png
.. |image9| image:: /imgs/VASP_module_vibration.png
.. |image10| image:: /imgs/VASP_module_structure.png
