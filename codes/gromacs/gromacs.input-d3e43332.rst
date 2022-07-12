.. _gromacs.input-d3e43332:

gromacs.input
=============

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image2|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | GROMACS input                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | gromacs.input                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | GROMACS input                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   ;
   ;   File 'mdout.mdp' was generated
   ;   By user: unknown (1095)
   ;   On host: node2178
   ;   At date: Tue Dec 11 15:42:14 2018
   ;

   ; VARIOUS PREPROCESSING OPTIONS
   ; Preprocessor information: use cpp syntax.
   ; e.g.: -I/home/joe/doe -I/home/mary/roe
   include                  = -I../top
   ; e.g.: -DPOSRES -DFLEXIBLE (note these variable names are case sensitive)
   define                   = 

   ; RUN CONTROL PARAMETERS
   integrator               = md
   ; Start time and timestep in ps
   tinit                    = 0
   dt                       = 0.0005
   nsteps                   = 80000000
   ; For exact run continuation or redoing part of a run
   init_step                = 0
   ; Part index is updated automatically on checkpointing (keeps files separate)
   simulation_part          = 1
   ; mode for center of mass motion removal
   comm-mode                = Linear
   ; number of steps for center of mass motion removal
   nstcomm                  = 10
   ; group(s) for center of mass motion removal
   comm-grps                = 

   ; LANGEVIN DYNAMICS OPTIONS
   ; Friction coefficient (amu/ps) and random seed
   bd-fric                  = 0
   ld-seed                  = 1993

   ; ENERGY MINIMIZATION OPTIONS
   ; Force tolerance and initial step-size
   emtol                    = 10
   emstep                   = 0.01
   ; Max number of iterations in relax-shells
   niter                    = 20
   ; Step size (ps^2) for minimization of flexible constraints
   fcstep                   = 0
   ; Frequency of steepest descents steps when doing CG
   nstcgsteep               = 1000
   nbfgscorr                = 10

   ; TEST PARTICLE INSERTION OPTIONS
   rtpi                     = 0.05

   ; OUTPUT CONTROL OPTIONS
   ; Output frequency for coords (x), velocities (v) and forces (f)
   nstxout                  = 1000
   nstvout                  = 1000
   nstfout                  = 1000
   ; Output frequency for energies to log file and energy file
   nstlog                   = 500
   nstcalcenergy            = -1
   nstenergy                = 1000
   ; Output frequency and precision for .xtc file
   nstxout-compressed       = 2000
   compressed-x-precision   = 1000
   ; This selects the subset of atoms for the compressed
   ; trajectory file. You can select multiple groups. By
   ; default, all atoms will be written.
   compressed-x-grps        = SOL LIN LI
   ; Selection of energy groups
   energygrps               = SOL LIN LI

   ; NEIGHBORSEARCHING PARAMETERS
   ; cut-off scheme (Verlet: particle based cut-offs, group: using charge groups)
   cutoff-scheme            = Verlet
   ; nblist update frequency
   nstlist                  = 10
   ; ns algorithm (simple or grid)
   ns-type                  = grid
   ; Periodic boundary conditions: xyz, no, xy
   pbc                      = xyz
   periodic_molecules       = no
   ; Allowed energy error due to the Verlet buffer in kJ/mol/ps per atom,
   ; a value of -1 means: use rlist
   verlet-buffer-tolerance  = 0.005
   ; nblist cut-off        
   rlist                    = 1.7
   ; long-range cut-off for switched potentials
   rlistlong                = -1
   nstcalclr                = -1

   ; OPTIONS FOR ELECTROSTATICS AND VDW
   ; Method for doing electrostatics
   coulombtype              = PME
   coulomb-modifier         = Potential-shift-Verlet
   rcoulomb-switch          = 0
   rcoulomb                 = 1.7
   ; Relative dielectric constant for the medium and the reaction field
   epsilon_r                = 1
   epsilon_rf               = 1
   ; Method for doing Van der Waals
   vdwtype                  = cut-off
   vdw-modifier             = Potential-shift-Verlet
   ; cut-off lengths       
   rvdw-switch              = 0
   rvdw                     = 1.7
   ; Apply long range dispersion corrections for Energy and Pressure
   DispCorr                 = EnerPres
   ; Extension of the potential lookup tables beyond the cut-off
   table-extension          = 1
   ; Separate tables between energy group pairs
   energygrp-table          = 
   ; Spacing for the PME/PPPM FFT grid
   fourierspacing           = 0.12
   ; FFT grid size, when a value is 0 fourierspacing will be used
   fourier_nx               = 0
   fourier_ny               = 0
   fourier_nz               = 0
   ; EWALD/PME/PPPM parameters
   pme_order                = 4
   ewald_rtol               = 1e-05
   ewald-rtol-lj            = 0.001
   lj-pme-comb-rule         = Geometric
   ewald_geometry           = 3d
   epsilon_surface          = 0

   ; IMPLICIT SOLVENT ALGORITHM
   implicit_solvent         = No

   ; GENERALIZED BORN ELECTROSTATICS
   ; Algorithm for calculating Born radii
   gb_algorithm             = Still
   ; Frequency of calculating the Born radii inside rlist
   nstgbradii               = 1
   ; Cutoff for Born radii calculation; the contribution from atoms
   ; between rlist and rgbradii is updated every nstlist steps
   rgbradii                 = 1
   ; Dielectric coefficient of the implicit solvent
   gb_epsilon_solvent       = 80
   ; Salt concentration in M for Generalized Born models
   gb_saltconc              = 0
   ; Scaling factors used in the OBC GB model. Default values are OBC(II)
   gb_obc_alpha             = 1
   gb_obc_beta              = 0.8
   gb_obc_gamma             = 4.85
   gb_dielectric_offset     = 0.009
   sa_algorithm             = Ace-approximation
   ; Surface tension (kJ/mol/nm^2) for the SA (nonpolar surface) part of GBSA
   ; The value -1 will set default value for Still/HCT/OBC GB-models.
   sa_surface_tension       = -1

   ; OPTIONS FOR WEAK COUPLING ALGORITHMS
   ; Temperature coupling  
   tcoupl                   = Berendsen
   nsttcouple               = 2
   nh-chain-length          = 10
   print-nose-hoover-chain-variables = no
   ; Groups to couple separately
   tc-grps                  = SOL LIN LI
   ; Time constant (ps) and reference temperature (K)
   tau-t                    = 0.1 0.02 0.1
   ref-t                    = 300 300 300
   ; pressure coupling     
   Pcoupl                   = Berendsen
   Pcoupltype               = Isotropic
   nstpcouple               = 2
   ; Time constant (ps), compressibility (1/bar) and reference P (bar)
   tau-p                    = 1.0
   compressibility          = 4.5e-5
   ref-p                    = 1.0
   ; Scaling of reference coordinates, No, All or COM
   refcoord_scaling         = No

   ; OPTIONS FOR QMMM calculations
   QMMM                     = no
   ; Groups treated Quantum Mechanically
   QMMM-grps                = 
   ; QM method             
   QMmethod                 = 
   ; QMMM scheme           
   QMMMscheme               = normal
   ; QM basisset           
   QMbasis                  = 
   ; QM charge             
   QMcharge                 = 
   ; QM multiplicity       
   QMmult                   = 
   ; Surface Hopping       
   SH                       = 
   ; CAS space options     
   CASorbitals              = 
   CASelectrons             = 
   SAon                     = 
   SAoff                    = 
   SAsteps                  = 
   ; Scale factor for MM charges
   MMChargeScaleFactor      = 1
   ; Optimization of QM subsystem
   bOPT                     = 
   bTS                      = 

   ; SIMULATED ANNEALING  
   ; Type of annealing for each temperature group (no/single/periodic)
   annealing                = 
   ; Number of time points to use for specifying annealing in each group
   annealing-npoints        = 
   ; List of times at the annealing points for each group
   annealing-time           = 
   ; Temp. at each annealing point, for each group.
   annealing-temp           = 

   ; GENERATE VELOCITIES FOR STARTUP RUN
   gen-vel                  = no
   gen-temp                 = 300
   gen-seed                 = 173529

   ; OPTIONS FOR BONDS    
   constraints              = all-bonds
   ; Type of constraint algorithm
   constraint-algorithm     = Lincs
   ; Do not constrain the start configuration
   continuation             = yes
   ; Use successive overrelaxation to reduce the number of shake iterations
   Shake-SOR                = yes
   ; Relative tolerance of shake
   shake-tol                = 0.0001
   ; Highest order in the expansion of the constraint coupling matrix
   lincs-order              = 4
   ; Number of iterations in the final step of LINCS. 1 is fine for
   ; normal simulations, but use 2 to conserve energy in NVE runs.
   ; For energy minimization with constraints it should be 4 to 8.
   lincs-iter               = 1
   ; Lincs will write a warning to the stderr if in one step a bond
   ; rotates over more degrees than
   lincs-warnangle          = 30
   ; Convert harmonic bonds to morse potentials
   morse                    = no

   ; ENERGY GROUP EXCLUSIONS
   ; Pairs of energy groups for which all non-bonded interactions are excluded
   energygrp-excl           = 

   ; WALLS                
   ; Number of walls, type, atom types, densities and box-z scale factor for Ewald
   nwall                    = 0
   wall_type                = 9-3
   wall_r_linpot            = -1
   wall-atomtype            = 
   wall-density             = 
   wall_ewald_zfac          = 3

   ; COM PULLING          
   ; Pull type: no, umbrella, constraint or constant-force
   pull                     = no

   ; ENFORCED ROTATION    
   ; Enforced rotation: No or Yes
   rotation                 = no

   ; Group to display and/or manipulate in interactive MD session
   IMD-group                = 

   ; NMR refinement stuff 
   ; Distance restraints type: No, Simple or Ensemble
   disre                    = No
   ; Force weighting of pairs in one distance restraint: Conservative or Equal
   disre-weighting          = Conservative
   ; Use sqrt of the time averaged times the instantaneous violation
   disre-mixed              = no
   disre-fc                 = 1000
   disre-tau                = 0
   ; Output frequency for pair distances to energy file
   nstdisreout              = 100
   ; Orientation restraints: No or Yes
   orire                    = no
   ; Orientation restraints force constant and tau for time averaging
   orire-fc                 = 0
   orire-tau                = 0
   orire-fitgrp             = 
   ; Output frequency for trace(SD) and S to energy file
   nstorireout              = 100

   ; Free energy variables
   free-energy              = no
   couple-moltype           = 
   couple-lambda0           = vdw-q
   couple-lambda1           = vdw-q
   couple-intramol          = no
   init-lambda              = 0
   init-lambda-state        = -1
   delta-lambda             = 0
   nstdhdl                  = 10
   fep-lambdas              = 
   mass-lambdas             = 
   coul-lambdas             = 
   vdw-lambdas              = 
   bonded-lambdas           = 
   restraint-lambdas        = 
   temperature-lambdas      = 
   calc-lambda-neighbors    = 1
   init-lambda-weights      = 
   dhdl-print-energy        = no
   sc-alpha                 = 0
   sc-power                 = 0
   sc-r-power               = 6
   sc-sigma                 = 0.3
   sc-coul                  = no
   separate-dhdl-file       = yes
   dhdl-derivatives         = yes
   dh_hist_size             = 0
   dh_hist_spacing          = 0.1

   ; Non-equilibrium MD stuff
   acc-grps                 = 
   accelerate               = 
   freezegrps               = 
   freezedim                = 
   cos-acceleration         = 0
   deform                   = 

   ; simulated tempering variables
   simulated-tempering      = no
   simulated-tempering-scaling = geometric
   sim-temp-low             = 300
   sim-temp-high            = 300

   ; Electric fields      
   ; Format is number of terms (int) and for all terms an amplitude (real)
   ; and a phase angle (real)
   E-x                      = 
   E-xt                     = 
   E-y                      = 
   E-yt                     = 
   E-z                      = 
   E-zt                     = 

   ; Ion/water position swapping for computational electrophysiology setups
   ; Swap positions along direction: no, X, Y, Z
   swapcoords               = no

   ; AdResS parameters    
   adress                   = no

   ; User defined thingies
   user1-grps               = 
   user2-grps               = 
   userint1                 = 0
   userint2                 = 0
   userint3                 = 0
   userint4                 = 0
   userreal1                = 0
   userreal2                = 0
   userreal3                = 0
   userreal4                = 0
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="gromacs.input">
           <module id="gromacs.input">
               <scalar dataType="xsd:string" dictRef="gm:include">-I../top</scalar>
               <scalar dataType="xsd:string" dictRef="gm:define" />
               <scalar dataType="xsd:string" dictRef="gm:integrator">md</scalar>
               <scalar dataType="xsd:string" dictRef="gm:tinit">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:dt">0.0005</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nsteps">8000000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:init.step">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:simulation.part">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:comm.mode">Linear</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstcomm">10</scalar>
               <scalar dataType="xsd:string" dictRef="gm:comm.grps" />
               <scalar dataType="xsd:string" dictRef="gm:bd.fric">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ld.seed">1993</scalar>
               <scalar dataType="xsd:string" dictRef="gm:emtol">10</scalar>
               <scalar dataType="xsd:string" dictRef="gm:emstep">0.01</scalar>
               <scalar dataType="xsd:string" dictRef="gm:niter">20</scalar>
               <scalar dataType="xsd:string" dictRef="gm:fcstep">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstcgsteep">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nbfgscorr">10</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rtpi">0.05</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstxout">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstvout">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstfout">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstlog">500</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstcalcenergy">-1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstenergy">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstxout.compressed">2000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:compressed.x.precision">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:compressed.x.grps">LIG COT TBA</scalar>
               <scalar dataType="xsd:string" dictRef="gm:energygrps">LIG COT TBA</scalar>
               <scalar dataType="xsd:string" dictRef="gm:cutoff.scheme">Verlet</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstlist">10</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ns.type">grid</scalar>
               <scalar dataType="xsd:string" dictRef="gm:pbc">xyz</scalar>
               <scalar dataType="xsd:string" dictRef="gm:periodic.molecules">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:verlet.buffer.tolerance">0.005</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rlist">1.7</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rlistlong">-1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstcalclr">-1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:coulombtype">PME</scalar>
               <scalar dataType="xsd:string" dictRef="gm:coulomb.modifier">Potential-shift-Verlet</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rcoulomb.switch">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rcoulomb">1.7</scalar>
               <scalar dataType="xsd:string" dictRef="gm:epsilon.r">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:epsilon.rf">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:vdwtype">cut-off</scalar>
               <scalar dataType="xsd:string" dictRef="gm:vdw.modifier">Potential-shift-Verlet</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rvdw.switch">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rvdw">1.7</scalar>
               <scalar dataType="xsd:string" dictRef="gm:dispcorr">EnerPres</scalar>
               <scalar dataType="xsd:string" dictRef="gm:table.extension">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:energygrp.table" />
               <scalar dataType="xsd:string" dictRef="gm:fourierspacing">0.12</scalar>
               <scalar dataType="xsd:string" dictRef="gm:fourier.nx">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:fourier.ny">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:fourier.nz">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:pme.order">4</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ewald.rtol">1e-05</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ewald.rtol.lj">0.001</scalar>
               <scalar dataType="xsd:string" dictRef="gm:lj.pme.comb.rule">Geometric</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ewald.geometry">3d</scalar>
               <scalar dataType="xsd:string" dictRef="gm:epsilon.surface">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:implicit.solvent">No</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.algorithm">Still</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstgbradii">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rgbradii">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.epsilon.solvent">80</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.saltconc">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.obc.alpha">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.obc.beta">0.8</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.obc.gamma">4.85</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gb.dielectric.offset">0.009</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sa.algorithm">Ace-approximation</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sa.surface.tension">-1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:tcoupl">Berendsen</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nsttcouple">2</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nh.chain.length">10</scalar>
               <scalar dataType="xsd:string" dictRef="gm:print.nose.hoover.chain.variables">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:tc.grps">COT TBA LIG</scalar>
               <scalar dataType="xsd:string" dictRef="gm:tau.t">0.02 0.1 0.1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ref.t">300 300 300</scalar>
               <scalar dataType="xsd:string" dictRef="gm:pcoupl">Parrinello-Rahman</scalar>
               <scalar dataType="xsd:string" dictRef="gm:pcoupltype">Isotropic</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstpcouple">2</scalar>
               <scalar dataType="xsd:string" dictRef="gm:tau.p">4.0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:compressibility">4.5e-5</scalar>
               <scalar dataType="xsd:string" dictRef="gm:ref.p">1.0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:refcoord.scaling">No</scalar>
               <scalar dataType="xsd:string" dictRef="gm:qmmm">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:qmmm.grps" />
               <scalar dataType="xsd:string" dictRef="gm:qmmethod" />
               <scalar dataType="xsd:string" dictRef="gm:qmmmscheme">normal</scalar>
               <scalar dataType="xsd:string" dictRef="gm:qmbasis" />
               <scalar dataType="xsd:string" dictRef="gm:qmcharge" />
               <scalar dataType="xsd:string" dictRef="gm:qmmult" />
               <scalar dataType="xsd:string" dictRef="gm:sh" />
               <scalar dataType="xsd:string" dictRef="gm:casorbitals" />
               <scalar dataType="xsd:string" dictRef="gm:caselectrons" />
               <scalar dataType="xsd:string" dictRef="gm:saon" />
               <scalar dataType="xsd:string" dictRef="gm:saoff" />
               <scalar dataType="xsd:string" dictRef="gm:sasteps" />
               <scalar dataType="xsd:string" dictRef="gm:mmchargescalefactor">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:bopt" />
               <scalar dataType="xsd:string" dictRef="gm:bts" />
               <scalar dataType="xsd:string" dictRef="gm:annealing" />
               <scalar dataType="xsd:string" dictRef="gm:annealing.npoints" />
               <scalar dataType="xsd:string" dictRef="gm:annealing.time" />
               <scalar dataType="xsd:string" dictRef="gm:annealing.temp" />
               <scalar dataType="xsd:string" dictRef="gm:gen.vel">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gen.temp">300</scalar>
               <scalar dataType="xsd:string" dictRef="gm:gen.seed">173529</scalar>
               <scalar dataType="xsd:string" dictRef="gm:constraints">all-bonds</scalar>
               <scalar dataType="xsd:string" dictRef="gm:constraint.algorithm">Lincs</scalar>
               <scalar dataType="xsd:string" dictRef="gm:continuation">yes</scalar>
               <scalar dataType="xsd:string" dictRef="gm:shake.sor">yes</scalar>
               <scalar dataType="xsd:string" dictRef="gm:shake.tol">0.0001</scalar>
               <scalar dataType="xsd:string" dictRef="gm:lincs.order">4</scalar>
               <scalar dataType="xsd:string" dictRef="gm:lincs.iter">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:lincs.warnangle">30</scalar>
               <scalar dataType="xsd:string" dictRef="gm:morse">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:energygrp.excl" />
               <scalar dataType="xsd:string" dictRef="gm:nwall">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:wall.type">9-3</scalar>
               <scalar dataType="xsd:string" dictRef="gm:wall.r.linpot">-1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:wall.atomtype" />
               <scalar dataType="xsd:string" dictRef="gm:wall.density" />
               <scalar dataType="xsd:string" dictRef="gm:wall.ewald.zfac">3</scalar>
               <scalar dataType="xsd:string" dictRef="gm:pull">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:rotation">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:imd.group" />
               <scalar dataType="xsd:string" dictRef="gm:disre">No</scalar>
               <scalar dataType="xsd:string" dictRef="gm:disre.weighting">Conservative</scalar>
               <scalar dataType="xsd:string" dictRef="gm:disre.mixed">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:disre.fc">1000</scalar>
               <scalar dataType="xsd:string" dictRef="gm:disre.tau">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstdisreout">100</scalar>
               <scalar dataType="xsd:string" dictRef="gm:orire">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:orire.fc">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:orire.tau">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:orire.fitgrp" />
               <scalar dataType="xsd:string" dictRef="gm:nstorireout">100</scalar>
               <scalar dataType="xsd:string" dictRef="gm:free.energy">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:couple.moltype" />
               <scalar dataType="xsd:string" dictRef="gm:couple.lambda0">vdw-q</scalar>
               <scalar dataType="xsd:string" dictRef="gm:couple.lambda1">vdw-q</scalar>
               <scalar dataType="xsd:string" dictRef="gm:couple.intramol">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:init.lambda">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:init.lambda.state">-1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:delta.lambda">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:nstdhdl">10</scalar>
               <scalar dataType="xsd:string" dictRef="gm:fep.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:mass.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:coul.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:vdw.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:bonded.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:restraint.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:temperature.lambdas" />
               <scalar dataType="xsd:string" dictRef="gm:calc.lambda.neighbors">1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:init.lambda.weights" />
               <scalar dataType="xsd:string" dictRef="gm:dhdl.print.energy">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sc.alpha">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sc.power">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sc.r.power">6</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sc.sigma">0.3</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sc.coul">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:separate.dhdl.file">yes</scalar>
               <scalar dataType="xsd:string" dictRef="gm:dhdl.derivatives">yes</scalar>
               <scalar dataType="xsd:string" dictRef="gm:dh.hist.size">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:dh.hist.spacing">0.1</scalar>
               <scalar dataType="xsd:string" dictRef="gm:acc.grps" />
               <scalar dataType="xsd:string" dictRef="gm:accelerate" />
               <scalar dataType="xsd:string" dictRef="gm:freezegrps" />
               <scalar dataType="xsd:string" dictRef="gm:freezedim" />
               <scalar dataType="xsd:string" dictRef="gm:cos.acceleration">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:deform" />
               <scalar dataType="xsd:string" dictRef="gm:simulated.tempering">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:simulated.tempering.scaling">geometric</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sim.temp.low">300</scalar>
               <scalar dataType="xsd:string" dictRef="gm:sim.temp.high">300</scalar>
               <scalar dataType="xsd:string" dictRef="gm:e.x" />
               <scalar dataType="xsd:string" dictRef="gm:e.xt" />
               <scalar dataType="xsd:string" dictRef="gm:e.y" />
               <scalar dataType="xsd:string" dictRef="gm:e.yt" />
               <scalar dataType="xsd:string" dictRef="gm:e.z" />
               <scalar dataType="xsd:string" dictRef="gm:e.zt" />
               <scalar dataType="xsd:string" dictRef="gm:swapcoords">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:adress">no</scalar>
               <scalar dataType="xsd:string" dictRef="gm:user1.grps" />
               <scalar dataType="xsd:string" dictRef="gm:user2.grps" />
               <scalar dataType="xsd:string" dictRef="gm:userint1">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:userint2">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:userint3">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:userint4">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:userreal1">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:userreal2">0</scalar>
               <scalar dataType="xsd:string" dictRef="gm:userreal3">0</scalar>     
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList id="init">  <template name="Input parameters" pattern="\s*\S+\s*=.*" endPattern=".*" endOffset="0" repeat="*">    <record id="r2" repeat="*">\s*{X,gm:name}\s*=\s*{X,gm:value}</record>    <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(lower-case(./text()))" />    <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(replace(./text(), '[_-]', '.'))" />    <transform process="createNameValue" xpath="./cml:list/cml:list" name="*[@dictRef='gm:name']" value="*[@dictRef='gm:value']" />    <transform process="pullup" xpath="//cml:scalar" repeat="3" />    <transform process="delete" xpath="//cml:module" />
           </template>               
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
