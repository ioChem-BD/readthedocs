.. _solvation-d3e1404:

solvation
=========

.. table:: Implementation level

   +-----------------------------------+-----------------------------------+
   | Type                              | Status                            |
   +===================================+===================================+
   | CML extraction template           | |image0|                          |
   +-----------------------------------+-----------------------------------+
   | HTML5 representation              | |image1|                          |
   +-----------------------------------+-----------------------------------+

.. table:: Template attributes

   +-----------------------------------+-----------------------------------+
   | Attribute                         | Value                             |
   +===================================+===================================+
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | solvation                         |
   +-----------------------------------+-----------------------------------+
   | name                              | ADF Init solvation parameters     |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*SOLVATION.*$\-\-\-.\*         |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\-\-\-.\*                    |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | solvation.xml                     |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    SOLVATION
   -------------------------------------------

     The Solvent-Excluding surface is calculated

          Division Level for Surface Triangles (NDIV)                  5
          Final Division Level for Triangles (NFDIV)                   1
          Radius of the Solvent (RSOL)                           1.40000 angstr
          Minimum Radius for new sphere (RMINSOLV)               0.50000 angstr
          Overlapping Factor (OFAC)                              0.80000
          New spheres will be assigned to the initials using ASSG1

     Dielectric Constant (EPSL)                                 78.40000

          COSMO equation is solved iteratively-               conjugate-gradient

          Maximun of Iterations for Charges (NCIX)                  1000
          Criterion for Charge convergence (CCNV)                1.0E-10

     Geometry-dependent empirical factor                         0.00000

     COSMO charges included variationally in SCF

          COSMO started at end of SCF

     C-Matrix calculated in cspmtx

     In cspmtx, C-Matrix calculated using fitted potential

   -------------------------------------------
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="solvation">
           <module cmlx:lineCount="30" cmlx:templateRef="solvation">
             <list id="cosmo">
                   <scalar dataType="xsd:integer" dictRef="a:ndiv">5</scalar>
                   <scalar dataType="xsd:integer" dictRef="a:nfdiv">1</scalar>
                   <scalar dataType="xsd:double" dictRef="a:rsol" units="nonsi:angstrom">1.4</scalar>
                   <scalar dataType="xsd:double" dictRef="a:rminsolv" units="nonsi:angstrom">0.5</scalar>
                   <scalar dataType="xsd:double" dictRef="a:ofac">0.8</scalar>
                   <scalar dataType="xsd:double" dictRef="a:epsl">78.4</scalar>
                   <scalar dataType="xsd:string" dictRef="a:cosmomethod">conjugate-gradient</scalar>
                   <scalar dataType="xsd:double" dictRef="a:ncix">1000.0</scalar>
                   <scalar dataType="xsd:double" dictRef="a:ccnv">1.0E-10</scalar>
                   <scalar dataType="xsd:double" dictRef="a:gdsf">0.0</scalar>
               </list>
           </module>     
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Division\sLevel\sfor\sSurface\sTriangles.*" endPattern=".*">    <record id="ndiv">.*\(NDIV\){I,a:ndiv}</record>       
           </template>  <template pattern="\s*Final\sDivision\sLevel\sfor\sTriangles.*" endPattern=".*">    <record id="nfdiv">.*\(NFDIV\){I,a:nfdiv}</record>
           </template>  <template pattern="\s*Radius\sof\sthe\sSolvent.*" endPattern=".*">    <record id="rsol">.*\(RSOL\){F,a:rsol}.*</record>
           </template>  <template pattern="\s*Minimum\sRadius\sfor\snew\ssphere.*" endPattern=".*">    <record id="rminsolv">.*\(RMINSOLV\){F,a:rminsolv}.*</record>
           </template>  <template pattern="\s*Overlapping\sFactor.*" endPattern=".*">    <record id="ofac">.*\(OFAC\){F,a:ofac}</record>
           </template>  <template pattern="\s*Dielectric\sConstant.*" endPattern=".*">    <record id="epsl">.*\(EPSL\){F,a:epsl}</record>
           </template>  <template pattern="\s*COSMO\sequation\sis\ssolved\siteratively.*" endPattern=".*">    <record id="cosmomethod">.*iteratively-{X,a:cosmomethod}</record>
           </template>  <template pattern="\s*Maximun\sof\sIterations\sfor\sCharges.*" endPattern=".*">    <record id="ncix">.*\(NCIX\){F,a:ncix}</record>
           </template>  <template pattern="\s*Criterion\sfor\sCharge\sconvergence.*" endPattern=".*">    <record id="ccnv">.*\(CCNV\){E,a:ccnv}</record>
           </template>  <template pattern="\s*Geometry-dependent\sempirical\sfactor.*" endPattern=".*">    <record id="gdsf">\s*Geometry-dependent\sempirical\sfactor{F,a:gdsf}</record>
           </template>   
       </templateList>
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='a:rsol']" value="nonsi:angstrom" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='a:rminsolv']" value="nonsi:angstrom" />
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="addChild" xpath="." elementName="cml:list" id="cosmo" />
   <transform process="move" xpath=".//cml:scalar" to=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
