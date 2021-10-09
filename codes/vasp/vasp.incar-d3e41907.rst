.. _vasp.incar-d3e41907:

vasp.incar
==========

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
   | *source*                          | VASP INCAR                        |
   +-----------------------------------+-----------------------------------+
   | id                                | vasp.incar                        |
   +-----------------------------------+-----------------------------------+
   | name                              | VASP INCAR                        |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | topTemplate.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   # +-----------------------------+ #
   # |         INCAR CeO2          | #
   # | Startparameter for this run | #
   # +-----------------------------+ #

   SYSTEM = Ag111-Bz
   ISTART = 1
   ICHARG = 2
   ISPIN  = 1
   GGA    = PE

   # ==> Electronic Relaxation <== #
   ENCUT  = 500
   EDIFF  = 1E-6
   LREAL  = AUTO
   ALGO   = FAST
   NELM   = 250
   NELMIN = 8

   # ==> Ionic Relaxation <== #
   NSW    = 400
   IBRION = 1
   POTIM  = 0.2 
   EDIFFG = 1E-3

   # ==> DOS related values <== #
   ISMEAR = 1 
   SIGMA  = 0.2

   # ==> Other Parameters <== #
   LASPH  = .TRUE.
   NPAR   = 2
   NSIM   = 12

   LDIPOL = .TRUE.
   IDIPOL = 3

   LWAVE  = .FALSE.
   LCHARG = .FALSE.

   SYMPREC = 1E-8 


   LVDW   = .TRUE. #switches dispersion on
   VDW_VERSION= 3 #switches between 2(DFT-D2), 3(DFT-D3(zero damping)) and 4(DFT-D3(BJ-damping))
   VDW_RADIUS= 40.0 #cutoff radius for considering neighboring imagecells
   VDW_s6 = 1.0 #s6-scaling parameter
   VDW_s8 = 0.7875 #s8-scaling factor
   VDW_a1 = 0.4289 #scaling for damping function
   VDW_a2 = 4.4407 #scaling for damping function
   VDW_SCALING= 1.0 #for PBE   
       

**Input.**

::

       # +-----------------------------+ #
           # |         INCAR CeO2          | #
           # | Startparameter for this run | #
           # +-----------------------------+ #
           
           SYSTEM = CeO2-2x2-9L-H2
           ISTART = 1
           ISPIN  = 2
           GGA    = PE
           
           # ==> Electronic Relaxation <== #
           ENCUT  = 500
           EDIFF  = 1E-5
           EDIFFG = 1E-4
           LREAL  = Auto
           NELM   = 250
           
           LMAXMIX= 6 #parameters recommended by VASP
           INIMIX = 0
           AMIX   = 0.2
           BMIX   = 0.0001
           AMIX_MAG= 0.8
           BMIX_MAG= 0.0001
           
           # ==> Ionic Relaxation <== #
           NSW    = 400
           IBRION = 1
           POTIM  = 0.05
           
           # ==> DOS related values <== #
           ISMEAR = 0
           SIGMA  = 0.05
           LORBIT = 11
           
           # ==> Other Parameters <== #
           LASPH  = .TRUE.
           LDAU   = .TRUE.
           LDAUL  = 3 3 -1 -1 -1
           LDAUU  = 5.5 5.5 0.0 0.0 0.0
           LDAUJ  = 1.0 1.0 0.0 0.0 0.0
           NPAR   = 4
           
           LDIPOL = .TRUE.
           IDIPOL = 3
           
           
           IALGO  = 38
           
           # ==> NEB Comments <== #
           IMAGES = 4
           ISPRING = -5
           SPRING = -5
           SPOWER = 1
           LSCALAPACK = .FALSE.
           LCLIMB = .TRUE.
           efirst = 0.
           elast = 0.
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="vasp.incar">
           <module id="vasp.incar">
               <scalar dictRef="v:lvdw">true</scalar>
               <scalar dataType="xsd:integer" dictRef="v:vdwversion">3</scalar>
           </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="vasp.incar2">
           <module id="vasp.incar">
               <array dataType="xsd:integer" dictRef="v:ldaul" size="5">3 3 -1 -1 -1</array>
               <array dataType="xsd:double" dictRef="v:ldauu" size="5">5.5 5.5 0.0 0.0 0.0</array>
               <array dataType="xsd:double" dictRef="v:ldauj" size="5">1.0 1.0 0.0 0.0 0.0</array>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*LDAUU\s*.*" endPattern=".*" endPattern2="~">    <record>\s*LDAUU\s*={1_50F,v:ldauu}\s*#?.*</record>
           </template>  <template pattern="\s*LDAUL\s*.*" endPattern=".*" endPattern2="~">    <record>\s*LDAUL\s*={1_50I,v:ldaul}\s*#?.*</record>
           </template>  <template pattern="\s*LDAUJ\s*.*" endPattern=".*" endPattern2="~">    <record>\s*LDAUJ\s*={1_50F,v:ldauj}\s*#?.*</record>
           </template>  <template pattern="\s*LVDW\s*=\s*\.TRUE\.\s*#?.*" endPattern=".*" endPattern2="~">    <transform process="addChild" xpath="." elementName="scalar" value="true" dictRef="v:lvdw" />
           </template>  <template pattern="\s*VDW_VERSION\s*=.*" endPattern=".*" endPattern2="~">    <record>\s*VDW_VERSION\s*=\s*{I,v:vdwversion}\s*#?.*</record>
           </template>               
       </templateList>
   <transform process="move" xpath="//cml:scalar" to="." />
   <transform process="move" xpath="//cml:array" to="." />
   <transform process="delete" xpath="//cml:module" />
   <transform process="delete" xpath="//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
