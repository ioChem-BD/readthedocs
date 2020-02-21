incar
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/vasp/dimension-d3e34551
   /codes/vasp/startparameters-d3e34584
   /codes/vasp/electronic.relaxation-d3e34614
   /codes/vasp/ionic.relaxation-d3e34661
   /codes/vasp/exchange.correlation-d3e34705
   /codes/vasp/atom.info-d3e34827
   /codes/vasp/dipole-d3e34871
   /codes/vasp/vcw-d3e34916
   /codes/vasp/dos-d3e34978

=====

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
   | *source*                          | VASP outcar                       |
   +-----------------------------------+-----------------------------------+
   | id                                | incar                             |
   +-----------------------------------+-----------------------------------+
   | name                              | INCAR parameters section          |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s\* Dimension\sof\sarrays:\s\*  |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*-{30,}\s\*                    |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | incar/incar.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Dimension of arrays:
      k-points           NKPTS =      5   k-points in BZ     NKDIM =      5   number of bands    NBANDS=    192
      number of dos      NEDOS =    301   number of ions     NIONS =     49
      non local maximal  LDIM  =      8   non local SUM 2l+1 LMDIM =     32
      total plane-waves  NPLWV = 290304
      max r-space proj   IRMAX =   3928   max aug-charges    IRDMAX=  12951
      dimension x,y,z NGX =    48 NGY =   48 NGZ =  126
      dimension x,y,z NGXF=    96 NGYF=   96 NGZF=  252
      support grid    NGXF=    96 NGYF=   96 NGZF=  252
      ions per type =              12  24   3  10
    NGX,Y,Z   is equivalent  to a cutoff of  10.27, 10.27,  9.13 a.u.
    NGXF,Y,Z  is equivalent  to a cutoff of  20.53, 20.53, 18.27 a.u.


    I would recommend the setting:
      dimension x,y,z NGX =    43 NGY =   43 NGZ =  125
    SYSTEM =  IDM-4ring                               
    POSCAR =  CIF file                                

   Startparameter for this run:
      NWRITE =      2    write-flag & timer
      PREC   = normal    normal or accurate (medium, high low for compatibility)
      ISTART =      1    job   : 0-new  1-cont  2-samecut
      ICHARG =      0    charge: 1-file 2-atom 10-const
      ISPIN  =      2    spin polarized calculation?
      LNONCOLLINEAR =      F non collinear calculations
      LSORBIT =      F    spin-orbit coupling
      INIWAV =      1    electr: 0-lowe 1-rand  2-diag
      LASPH  =      T    aspherical Exc in radial PAW
      METAGGA=      F    non-selfconsistent MetaGGA calc.

    Electronic Relaxation 1
      ENCUT  =  500.0 eV  36.75 Ry    6.06 a.u.  14.17 14.17 41.81*2*pi/ulx,y,z
      ENINI  =  500.0     initial cutoff
      ENAUG  =  644.9 eV  augmentation charge cutoff
      NELM   =    250;   NELMIN=  2; NELMDL=  0     # of ELM steps 
      EDIFF  = 0.1E-04   stopping-criterion for ELM
      LREAL  =      T    real-space projection
      NLSPLINE    = F    spline interpolate recip. space projectors
      LCOMPAT=      F    compatible to vasp.4.4
      GGA_COMPAT  = T    GGA compatible to vasp.4.4-vasp.4.6
      LMAXPAW     = -100 max onsite density
      LMAXMIX     =    6 max onsite mixed and CHGCAR
      VOSKOWN=      0    Vosko Wilk Nusair interpolation
      ROPT   =   -0.00050  -0.00050  -0.00050  -0.00050
    Ionic relaxation
      EDIFFG = 0.1E-03   stopping-criterion for IOM
      NSW    =    600    number of steps for IOM
      NBLOCK =      1;   KBLOCK =    600    inner block; outer block 
      IBRION =     44    ionic relax: 0-MD 1-quasi-New 2-CG
      NFREE  =      0    steps in history (QN), initial steepest desc. (CG)
      ISIF   =      2    stress and relaxation
      IWAVPR =     11    prediction:  0-non 1-charg 2-wave 3-comb
      ISYM   =      2    0-nonsym 1-usesym 2-fastsym
      LCORR  =      T    Harris-Foulkes like correction to forces

      POTIM  = 0.0500    time-step for ionic-motion
      TEIN   = ******    initial temperature
      TEBEG  =    0.0;   TEEND  =   0.0 temperature during run
      SMASS  =  -3.00    Nose mass-parameter (am)
      estimated Nose-frequenzy (Omega)   =  0.10E-29 period in steps =****** mass=  -0.138E-26a.u.
      SCALEE = 1.0000    scale energy and forces
      NPACO  =    256;   APACO  = 16.0  distance and # of slots for P.C.
      PSTRESS=    0.0 pullay stress

     Mass of Ions in am
      POMASS = 140.12 16.00 12.01  1.00
     Ionic Valenz
      ZVAL   =  12.00  6.00  4.00  1.00
     Atomic Wigner-Seitz radii
      RWIGS  =  -1.00 -1.00 -1.00 -1.00
     virtual crystal weights 
      VCA    =   1.00  1.00  1.00  1.00
      NELECT =     310.0000    total number of electrons
      NUPDOWN=      -1.0000    fix difference up-down

    DOS related values:
      EMIN   =  10.00;   EMAX   =-10.00  energy-range for DOS
      EFERMI =   0.00
      ISMEAR =     0;   SIGMA  =   0.05  broadening in eV -4-tet -1-fermi 0-gaus

    Electronic relaxation 2 (details)
      IALGO  =     38    algorithm
      LDIAG  =      T    sub-space diagonalisation (order eigenvalues)
      LSUBROT=      T    optimize rotation matrix (better conditioning)
      TURBO    =      0    0=normal 1=particle mesh
      IRESTART =      0    0=no restart 2=restart with 2 vectors
      NREBOOT  =      0    no. of reboots
      NMIN     =      0    reboot dimension
      EREF     =   0.00    reference energy to select bands
      IMIX   =      4    mixing-type and parameters
        AMIX     =   0.20;   BMIX     =  0.00
        AMIX_MAG =   0.80;   BMIX_MAG =  0.00
        AMIN     =   0.10
        WC   =   100.;   INIMIX=   0;  MIXPRE=   1;  MAXMIX= -45

    Intra band minimization:
      WEIMIN = 0.0010     energy-eigenvalue tresh-hold
      EBREAK =  0.13E-07  absolut break condition
      DEPER  =   0.30     relativ break condition  

      TIME   =   0.40     timestep for ELM

     volume/ion in A,a.u.               =      24.49       165.24
     Fermi-wavevector in a.u.,A,eV,Ry     =   1.042690  1.970399 14.792291  1.087203
     Thomas-Fermi vector in A             =   2.177366
    
    Write flags
      LWAVE  =      T    write WAVECAR
      LCHARG =      T    write CHGCAR
      LVTOT  =      F    write LOCPOT, total local potential
      LVHAR  =      F    write LOCPOT, Hartree potential only
      LELF   =      F    write electronic localiz. function (ELF)
      LORBIT =     11    0 simple, 1 ext, 2 COOP (PROOUT)


    Dipole corrections
      LMONO  =      F    monopole corrections only (constant potential shift)
      LDIPOL =      T    correct potential (dipole corrections)
      IDIPOL =      3    1-x, 2-y, 3-z, 4-all directions 
      EPSILON=  1.0000000 bulk dielectric constant

    LDA+U is selected, type is set to LDAUTYPE =  2
      angular momentum for each species LDAUL =     3   -1   -1   -1
      U (eV)           for each species LDAUU =   5.5  0.0  0.0  0.0
      J (eV)           for each species LDAUJ =   1.0  0.0  0.0  0.0
    Exchange correlation treatment:
      GGA     =    PE    GGA type
      LEXCH   =     8    internal setting for exchange type
      VOSKOWN=      0    Vosko Wilk Nusair interpolation
      LHFCALC =     F    Hartree Fock is set to
      LHFONE  =     F    Hartree Fock one center treatment
      AEXX    =    0.0000 exact exchange contribution

    Linear response parameters
      LEPSILON=     F    determine dielectric tensor
      LRPA    =     F    only Hartree local field effects (RPA)
      LNABLA  =     F    use nabla operator in PAW spheres
      LVEL    =     F    velocity operator in full k-point grid
      LINTERFAST=   F  fast interpolation
      KINTER  =     0    interpolate to denser k-point grid
      CSHIFT  =0.1000    complex shift for real part using Kramers Kronig
      OMEGAMAX=  -1.0    maximum frequency
      DEG_THRESHOLD= 0.2000000E-02 threshold for treating states as degnerate
      RTIME   =    0.100 relaxation time in fs

    Orbital magnetization related:
      ORBITALMAG=     F  switch on orbital magnetization
      LCHIMAG   =     F  perturbation theory with respect to B field
      DQ        =  0.001000  dq finite difference perturbation B field



   --------------------------------------------------------------------------------------------------------    
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="incar">
           <module cmlx:templateRef="incar">      
               <scalar dataType="xsd:integer" dictRef="v:ispin">2</scalar>
               <scalar dataType="xsd:integer" dictRef="v:energyCutoff" units="nonsi:electronvolt">500</scalar>
               <scalar dataType="xsd:double" dictRef="v:ediff">0.1</scalar>
               <scalar dataType="xsd:double" dictRef="v:ediffg">0.1</scalar>
               <scalar dataType="xsd:integer" dictRef="v:ibrion">44</scalar>
               <scalar dataType="xsd:double" dictRef="v:potim">0.0500</scalar>
               <scalar dataType="xsd:double" dictRef="v:nelect">310.0000</scalar>
               <scalar dataType="xsd:double" dictRef="v:nupdown">-1.0000</scalar>
               <scalar dataType="xsd:integer" dictRef="v:ismear">0</scalar>
               <scalar dataType="xsd:double" dictRef="v:sigma">0.05</scalar>
               <scalar dataType="xsd:string" dictRef="v:ldipol">T</scalar>
               <scalar dataType="xsd:integer" dictRef="v:idipol">3</scalar>
               <scalar dictRef="v:ldau">true</scalar>
               <scalar dataType="xsd:integer" dictRef="v:ldautype">2</scalar>
               <scalar dataType="xsd:string" dictRef="v:gga">PE</scalar>
               <scalar dataType="xsd:boolean" dictRef="v:lhfcalc">false</scalar>
               <array dataType="xsd:integer" dictRef="cc:atomcount" size="4">12 24 3 10</array>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <xi:include href="incar/dimension.xml" />  <xi:include href="incar/startparameters.xml" />  <xi:include href="incar/electronic.relaxation.xml" />  <xi:include href="incar/ionic.relaxation.xml" />  <xi:include href="incar/exchange.correlation.xml" />  <xi:include href="incar/atom.info.xml" />  <xi:include href="incar/dipole.xml" />  <xi:include href="incar/vcw.xml" />  <xi:include href="incar/dos.xml" />
       </templateList>
   <templateList>  <template id="temperature" pattern="\s*TEIN.*" endPattern=".*" endPattern2="~">    <record id="temperature">\s*TEIN\s*={F,cc:temp}initial\stemperature.*</record>    <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:temp']" value="si:k" />
           </template>  <template id="potim" pattern="\s*POTIM.*" endPattern=".*" endPattern2="~">    <record id="potim">\s*POTIM\s*={F,v:potim}.*</record>
           </template>  <template id="ldau" pattern="\s*LDA.*is\sselected,\stype\sis\sset.*" endPattern2="~">    <record id="ldau">\s*LDA.*is\sselected,\stype\sis\sset\sto\sLDAUTYPE\s={I,v:ldautype}.*</record>    <transform process="addChild" xpath="." elementName="cml:scalar" position="0" dictRef="v:ldau" value="true" />
           </template>
       </templateList>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
