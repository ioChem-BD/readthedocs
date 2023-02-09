.. _input.parameters-d3e26692:

input.parameters
================

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
   | *source*                                                                                                                   | GROMACS log                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | input.parameters                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Input section                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | Input&#92;sParameters:.\*                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/input.xml                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   Input Parameters:
      integrator                     = md
      tinit                          = 0
      dt                             = 0.0005
      nsteps                         = 8000000
      init-step                      = 0
      simulation-part                = 1
      comm-mode                      = Linear
      nstcomm                        = 10
      bd-fric                        = 0
      ld-seed                        = 1993
      emtol                          = 10
      emstep                         = 0.01
      niter                          = 20
      fcstep                         = 0
      nstcgsteep                     = 1000
      nbfgscorr                      = 10
      rtpi                           = 0.05
      nstxout                        = 1000
      nstvout                        = 1000
      nstfout                        = 1000
      nstlog                         = 500
      nstcalcenergy                  = 10
      nstenergy                      = 1000
      nstxout-compressed             = 2000
      compressed-x-precision         = 1000
      cutoff-scheme                  = Verlet
      nstlist                        = 40
      ns-type                        = Grid
      pbc                            = xyz
      periodic-molecules             = FALSE
      verlet-buffer-tolerance        = 0.005
      rlist                          = 1.7
      rlistlong                      = 1.7
      nstcalclr                      = 10
      coulombtype                    = PME
      coulomb-modifier               = Potential-shift
      rcoulomb-switch                = 0
      rcoulomb                       = 1.7
      epsilon-r                      = 1
      epsilon-rf                     = 1
      vdw-type                       = Cut-off
      vdw-modifier                   = Potential-shift
      rvdw-switch                    = 0
      rvdw                           = 1.7
      DispCorr                       = EnerPres
      table-extension                = 1
      fourierspacing                 = 0.12
      fourier-nx                     = 128
      fourier-ny                     = 128
      fourier-nz                     = 128
      pme-order                      = 4
      ewald-rtol                     = 1e-05
      ewald-rtol-lj                  = 0.001
      lj-pme-comb-rule               = Geometric
      ewald-geometry                 = 0
      epsilon-surface                = 0
      implicit-solvent               = No
      gb-algorithm                   = Still
      nstgbradii                     = 1
      rgbradii                       = 1
      gb-epsilon-solvent             = 80
      gb-saltconc                    = 0
      gb-obc-alpha                   = 1
      gb-obc-beta                    = 0.8
      gb-obc-gamma                   = 4.85
      gb-dielectric-offset           = 0.009
      sa-algorithm                   = Ace-approximation
      sa-surface-tension             = 2.05016
      tcoupl                         = Berendsen
      nsttcouple                     = 2
      nh-chain-length                = 0
      print-nose-hoover-chain-variables = FALSE
      pcoupl                         = Parrinello-Rahman
      pcoupltype                     = Isotropic
      nstpcouple                     = 2
      tau-p                          = 4
      compressibility (3x3):
         compressibility[    0]={ 4.50000e-05,  0.00000e+00,  0.00000e+00}
         compressibility[    1]={ 0.00000e+00,  4.50000e-05,  0.00000e+00}
         compressibility[    2]={ 0.00000e+00,  0.00000e+00,  4.50000e-05}
      ref-p (3x3):
         ref-p[    0]={ 1.00000e+00,  0.00000e+00,  0.00000e+00}
         ref-p[    1]={ 0.00000e+00,  1.00000e+00,  0.00000e+00}
         ref-p[    2]={ 0.00000e+00,  0.00000e+00,  1.00000e+00}
      refcoord-scaling               = No
      posres-com (3):
         posres-com[0]= 0.00000e+00
         posres-com[1]= 0.00000e+00
         posres-com[2]= 0.00000e+00
      posres-comB (3):
         posres-comB[0]= 0.00000e+00
         posres-comB[1]= 0.00000e+00
         posres-comB[2]= 0.00000e+00
      QMMM                           = FALSE
      QMconstraints                  = 0
      QMMMscheme                     = 0
      MMChargeScaleFactor            = 1
   qm-opts:
      ngQM                           = 0
      constraint-algorithm           = Lincs
      continuation                   = TRUE
      Shake-SOR                      = TRUE
      shake-tol                      = 0.0001
      lincs-order                    = 4
      lincs-iter                     = 1
      lincs-warnangle                = 30
      nwall                          = 0
      wall-type                      = 9-3
      wall-r-linpot                  = -1
      wall-atomtype[0]               = -1
      wall-atomtype[1]               = -1
      wall-density[0]                = 0
      wall-density[1]                = 0
      wall-ewald-zfac                = 3
      pull                           = no
      rotation                       = FALSE
      interactiveMD                  = FALSE
      disre                          = No
      disre-weighting                = Conservative
      disre-mixed                    = FALSE
      dr-fc                          = 1000
      dr-tau                         = 0
      nstdisreout                    = 100
      orire-fc                       = 0
      orire-tau                      = 0
      nstorireout                    = 100
      free-energy                    = no
      cos-acceleration               = 0
      deform (3x3):
         deform[    0]={ 0.00000e+00,  0.00000e+00,  0.00000e+00}
         deform[    1]={ 0.00000e+00,  0.00000e+00,  0.00000e+00}
         deform[    2]={ 0.00000e+00,  0.00000e+00,  0.00000e+00}
      simulated-tempering            = FALSE
      E-x:
         n = 0
      E-xt:
         n = 0
      E-y:
         n = 0
      E-yt:
         n = 0
      E-z:
         n = 0
      E-zt:
         n = 0
      swapcoords                     = no
      adress                         = FALSE
      userint1                       = 0
      userint2                       = 0
      userint3                       = 0
      userint4                       = 0
      userreal1                      = 0
      userreal2                      = 0
      userreal3                      = 0
      userreal4                      = 0
   grpopts:
      nrdf:     2027.99     2139.99      563301
      ref-t:         300         300         300
      tau-t:        0.02         0.1         0.1
   annealing:          No          No          No
   annealing-npoints:           0           0           0
      acc:            0           0           0
      nfreeze:           N           N           N
      energygrp-flags[  0]: 0 0 0
      energygrp-flags[  1]: 0 0 0
      energygrp-flags[  2]: 0 0 0

       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="input.parameters">
           <module cmlx:templateRef="input.parameters">
            <scalar dataType="xsd:string" dictRef="gm:integrator">md</scalar>
            <scalar dataType="xsd:string" dictRef="gm:tinit">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:dt">0.0005</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nsteps">8000000</scalar>
            <scalar dataType="xsd:string" dictRef="gm:init.step">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:simulation.part">1</scalar>
            <scalar dataType="xsd:string" dictRef="gm:comm.mode">Linear</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nstcomm">10</scalar>
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
            <scalar dataType="xsd:string" dictRef="gm:nstcalcenergy">10</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nstenergy">1000</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nstxout.compressed">2000</scalar>
            <scalar dataType="xsd:string" dictRef="gm:compressed.x.precision">1000</scalar>
            <scalar dataType="xsd:string" dictRef="gm:cutoff.scheme">Verlet</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nstlist">40</scalar>
            <scalar dataType="xsd:string" dictRef="gm:ns.type">Grid</scalar>
            <scalar dataType="xsd:string" dictRef="gm:pbc">xyz</scalar>
            <scalar dataType="xsd:string" dictRef="gm:periodic.molecules">FALSE</scalar>
            <scalar dataType="xsd:string" dictRef="gm:verlet.buffer.tolerance">0.005</scalar>
            <scalar dataType="xsd:string" dictRef="gm:rlist">1.7</scalar>
            <scalar dataType="xsd:string" dictRef="gm:rlistlong">1.7</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nstcalclr">10</scalar>
            <scalar dataType="xsd:string" dictRef="gm:coulombtype">PME</scalar>
            <scalar dataType="xsd:string" dictRef="gm:coulomb.modifier">Potential-shift</scalar>
            <scalar dataType="xsd:string" dictRef="gm:rcoulomb.switch">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:rcoulomb">1.7</scalar>
            <scalar dataType="xsd:string" dictRef="gm:epsilon.r">1</scalar>
            <scalar dataType="xsd:string" dictRef="gm:epsilon.rf">1</scalar>
            <scalar dataType="xsd:string" dictRef="gm:vdw.type">Cut-off</scalar>
            <scalar dataType="xsd:string" dictRef="gm:vdw.modifier">Potential-shift</scalar>
            <scalar dataType="xsd:string" dictRef="gm:rvdw.switch">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:rvdw">1.7</scalar>
            <scalar dataType="xsd:string" dictRef="gm:dispcorr">EnerPres</scalar>
            <scalar dataType="xsd:string" dictRef="gm:table.extension">1</scalar>
            <scalar dataType="xsd:string" dictRef="gm:fourierspacing">0.12</scalar>
            <scalar dataType="xsd:string" dictRef="gm:fourier.nx">128</scalar>
            <scalar dataType="xsd:string" dictRef="gm:fourier.ny">128</scalar>
            <scalar dataType="xsd:string" dictRef="gm:fourier.nz">128</scalar>
            <scalar dataType="xsd:string" dictRef="gm:pme.order">4</scalar>
            <scalar dataType="xsd:string" dictRef="gm:ewald.rtol">1e-05</scalar>
            <scalar dataType="xsd:string" dictRef="gm:ewald.rtol.lj">0.001</scalar>
            <scalar dataType="xsd:string" dictRef="gm:lj.pme.comb.rule">Geometric</scalar>
            <scalar dataType="xsd:string" dictRef="gm:ewald.geometry">0</scalar>
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
            <scalar dataType="xsd:string" dictRef="gm:sa.surface.tension">2.05016</scalar>
            <scalar dataType="xsd:string" dictRef="gm:tcoupl">Berendsen</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nsttcouple">2</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nh.chain.length">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:print.nose.hoover.chain.variables">FALSE</scalar>
            <scalar dataType="xsd:string" dictRef="gm:pcoupl">Parrinello-Rahman</scalar>
            <scalar dataType="xsd:string" dictRef="gm:pcoupltype">Isotropic</scalar>
            <scalar dataType="xsd:string" dictRef="gm:nstpcouple">2</scalar>
            <scalar dataType="xsd:string" dictRef="gm:tau.p">4</scalar>
            <scalar dataType="xsd:string" dictRef="gm:refcoord.scaling">No</scalar>
            <matrix cols="3" dataType="xsd:double" dictRef="gm:compressibility" rows="3">4.50000e-05 0.00000e+00 0.00000e+00 0.00000e+00 4.50000e-05 0.00000e+00 0.00000e+00 0.00000e+00 4.50000e-05</matrix>
            <matrix cols="3" dataType="xsd:double" dictRef="gm:ref.p" rows="3">1.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 1.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 1.00000e+00</matrix>
            <scalar dataType="xsd:string" dictRef="gm:qmmm">FALSE</scalar>
            <scalar dataType="xsd:string" dictRef="gm:qmconstraints">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:qmmmscheme">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:mmchargescalefactor">1</scalar>
            <array dataType="xsd:double" dictRef="gm:posres.com" size="3">0.00000e+00 0.00000e+00 0.00000e+00</array>
            <array dataType="xsd:double" dictRef="gm:posres.comb" size="3">0.00000e+00 0.00000e+00 0.00000e+00</array>
            <scalar dataType="xsd:string" dictRef="gm:simulated.tempering">FALSE</scalar>
            <matrix cols="3" dataType="xsd:double" dictRef="gm:deform" rows="3">0.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00 0.00000e+00</matrix>
            <array dataType="xsd:string" dictRef="gm:nrdf" size="3">2027.99 2139.99 563301</array>
            <scalar dataType="xsd:string" dictRef="gm:swapcoords">no</scalar>
            <scalar dataType="xsd:string" dictRef="gm:adress">FALSE</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userint1">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userint2">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userint3">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userint4">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userreal1">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userreal2">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userreal3">0</scalar>
            <scalar dataType="xsd:string" dictRef="gm:userreal4">0</scalar>
            <array dataType="xsd:string" dictRef="gm:ref.t" size="3">300 300 300</array>
            <array dataType="xsd:string" dictRef="gm:tau.t" size="3">0.02 0.1 0.1</array>
            <array dataType="xsd:string" dictRef="gm:annealing" size="3">No No No</array>
            <array dataType="xsd:string" dictRef="gm:annealing.npoints" size="3">0 0 0</array>
            <array dataType="xsd:string" dictRef="gm:acc" size="3">0 0 0</array>
            <array dataType="xsd:string" dictRef="gm:nfreeze" size="3">N N N</array>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record />
   <template id="discarded" pattern="\s*E-.*" endPattern=".*" endOffset="1"> 
       </template>
   <template id="array" pattern="\s*\w.+:\s+\S+.*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">  <record>{A,gm:name}:{X,gm:value}</record>  <transform process="createArray" xpath=".//cml:scalar[@dictRef='gm:value']" splitter="\s+" from="." />  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(lower-case(./text()))" />  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(replace(./text(), '[-_]', '.'))" />  <transform process="pullup" xpath=".//cml:scalar" />  <transform process="pullup" xpath=".//cml:array" />  <transform process="addAttribute" xpath=".//cml:array" name="dictRef" value="$string(concat('gm:', ../cml:scalar[@dictRef='gm:name']))" />  <transform process="pullup" xpath=".//cml:array" repeat="2" /> 
       </template>
   <template id="single" pattern="\s{3}\w.+=.+" endPattern=".+\(.*\):.*" endPattern2="~" endOffset="0" repeat="*">  <record id="r2" repeat="*">\s*{X,gm:name}\s*=\s*{X,gm:value}</record>  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(lower-case(./text()))" />  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(replace(./text(), '[-_]', '.'))" />  <transform process="createNameValue" xpath="./cml:list/cml:list" name="*[@dictRef='gm:name']" value="*[@dictRef='gm:value']" />  <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
       </template>
   <template id="array" pattern=".+\(\d+\):.*" endPattern=".+\(\d+\):.*" endPattern2=".+\(.+x.+\):.*" endPattern3="\s{1,5}\w.*" endPattern4="~" endOffset="0" repeat="*">  <record>{X,gm:name}\(.*</record>  <record repeat="*" makeArray="true">.*={X,gm:value}</record>  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(lower-case(./text()))" />  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(replace(./text(), '[-_]', '.'))" />  <transform process="pullup" xpath=".//cml:scalar" />  <transform process="pullup" xpath=".//cml:array" />  <transform process="addAttribute" xpath=".//cml:array" name="dataType" value="xsd:double" />  <transform process="addAttribute" xpath=".//cml:array" name="dictRef" value="$string(concat('gm:', parent::cml:module/cml:scalar[@dictRef='gm:name']))" />  <transform process="pullup" xpath=".//cml:array" />        
       </template>
   <template id="matrix" pattern=".+\(.+x.+\):.*" endPattern=".+\(.+x.+\):.*" endPattern2="\s{1,5}\w.*" endPattern3="~" endOffset="0" repeat="*">  <record>{X,gm:name}\(.*</record>  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(lower-case(./text()))" />  <transform process="setValue" xpath="//cml:scalar[@dictRef='gm:name']" value="$string(replace(./text(), '[-_]', '.'))" />  <transform process="pullup" xpath=".//cml:scalar" />  <record repeat="*">.*\{{X,cc:dummy},*\}</record>  <transform process="split" xpath=".//cml:scalar[@dictRef='cc:dummy']" splitter=",\s*" />  <transform process="createArray" xpath=".//cml:list[@dictRef='cc:dummy']" from="cml:scalar" />  <transform process="addAttribute" xpath=".//cml:array" name="dataType" value="xsd:double" />  <transform process="createMatrix" xpath="." from=".//cml:array" dictRef="cc:dummy" />  <transform process="pullup" xpath=".//cml:matrix" repeat="2" />  <transform process="addAttribute" xpath=".//cml:matrix" name="dictRef" value="$string(concat('gm:', parent::cml:module/cml:scalar[@dictRef='gm:name']))" />  <transform process="pullup" xpath=".//cml:matrix" />
       </template>
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
