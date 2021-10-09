.. _qespresso.input-d3e42460:

qespresso.input
===============

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
   | *source*                          | QuantumEspresso input             |
   +-----------------------------------+-----------------------------------+
   | id                                | qespresso.input                   |
   +-----------------------------------+-----------------------------------+
   | name                              | QuantumEspresso input             |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | topTemplate.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   &CONTROL
                    calculation = 'relax' ,
                   restart_mode = 'from_scratch' ,
                     wf_collect = .true. ,
                         prefix = 'Fe.USPP.001_2x2_145_vaccum' ,
                      verbosity = 'high' ,
                  etot_conv_thr = 1.0D-9 ,
                  forc_conv_thr = 1.0D-5 ,
                        tstress = .true. ,
                        tprnfor = .true. ,
                       dipfield = .true. ,
    /
   &SYSTEM
                         ibrav = 14,
                             A = 10.2304 ,
                             B = 10.2304 ,
                             C = 28.3548 ,
                         cosAB = -0.5 ,
                         cosAC = 0 ,
                         cosBC = 0 ,
                           nat = 120 ,
                          ntyp = 3,
                       ecutwfc = 40.0 ,
                       ecutrho = 320.0 ,
                     input_dft = 'PBE' ,
                   occupations = 'smearing' ,
                       degauss = 0.02 ,
                      smearing = 'gaussian' ,
                         nspin = 2 ,
       starting_magnetization(1) = 1.0,
       starting_magnetization(2) = -1.0,
       starting_magnetization(3) = 0.0,
                     lda_plus_u = .true. ,
                lda_plus_u_kind = 0 , !type 2 not implemented, ignores J
                   Hubbard_U(1) = 4.2,
                   Hubbard_U(2) = 4.2,
                  Hubbard_J0(1) = 0.0, !Is ignored!
                  Hubbard_J0(2) = 0.0, !Is ignored!
   /
   &ELECTRONS
              electron_maxstep = 800,
                 conv_thr_init = 1e-4 ,
                      conv_thr = 1e-9 ,
                   startingpot = 'atomic' ,
                   startingwfc = 'random' ,
                  adaptive_thr = .true. ,
                   mixing_beta = 0.14,
               diagonalization = 'cg' ,
   /
   &IONS
                  ion_dynamics = 'bfgs' ,
              trust_radius_min =  1.D-5 ,
   /
   ATOMIC_SPECIES
    Fe1   55.84500  Fe.pbe-sp-van_ak.UPF
    Fe2   55.84500  Fe.pbe-sp-van_ak.UPF
      O   15.99990  O.pbe-van_ak.UPF
   ATOMIC_POSITIONS crystal
   Fe2      0.166663898   0.333337143   0.409451359
   Fe1     -0.000002447   0.000003614   0.451051249
   Fe2      0.166660000   0.333340000   0.061240000    0   0   0
   Fe1      0.333340000   0.166670000   0.000000000    0   0   0
   Fe2      0.000000000   0.000000000   0.081950000    0   0   0
   Fe1      0.333340000   0.166670000   0.143190000    0   0   0
   Fe2     -0.000005343   0.000005009   0.225538724
   Fe1      0.166660000   0.333340000   0.163900000    0   0   0
   Fe2      0.333327346   0.166671997   0.246584781
   Fe1      0.166662601   0.333338569   0.308651469
   Fe2      0.333330456   0.166670754   0.396298854
   Fe1     -0.000003950   0.000004548   0.328137387
   O        0.152380000   0.000000000   0.030620000    0   0   0
   O        0.000000000   0.152380000   0.030620000    0   0   0
   O        0.493114653   0.320585686   0.442431216
   O        0.327462379   0.006886637   0.442431019
   O        0.179415420   0.172539124   0.442431172
   O        0.347620000   0.347620000   0.030620000    0   0   0
   O        0.485638190   0.166610684   0.194910500
   O        0.333389960   0.319042226   0.194910254
   O        0.319050000   0.485720000   0.112570000    0   0   0
   O        0.166660000   0.180960000   0.112570000    0   0   0
   O        0.014280000   0.333340000   0.112570000    0   0   0
   O        0.180958728   0.014363721   0.194910054
   O        0.321788281   0.333225075   0.360556075
   O        0.166775360   0.488574984   0.360556183
   O        0.152375882   0.153125384   0.277338078
   O        0.000735347   0.347624423   0.277338029
   O        0.346875072  -0.000734132   0.277338119
   O        0.011425967   0.178212850   0.360556085
   Fe2      0.666663975   0.333337151   0.409451269
   Fe1      0.499997414   0.000003470   0.451051255
   Fe2      0.666660000   0.333340000   0.061240000    0   0   0
   Fe1      0.833330000   0.166670000   0.000000000    0   0   0
   Fe2      0.500000000   0.000000000   0.081950000    0   0   0
   Fe1      0.833330000   0.166670000   0.143190000    0   0   0
   Fe2      0.499993955   0.000003637   0.225539296
   Fe1      0.666660000   0.333340000   0.163900000    0   0   0
   Fe2      0.833328682   0.166672502   0.246584853
   Fe1      0.666662589   0.333338201   0.308651364
   Fe2      0.833330375   0.166670545   0.396298876
   Fe1      0.499996285   0.000004543   0.328137528
   O        0.652380000   0.000000000   0.030620000    0   0   0
   O        0.500000000   0.152380000   0.030620000    0   0   0
   O        0.993114488   0.320585299   0.442431331
   O        0.827462315   0.006886443   0.442431085
   O        0.679415215   0.172538968   0.442431093
   O        0.847620000   0.347620000   0.030620000    0   0   0
   O        0.985636731   0.166611225   0.194910522
   O        0.833388840   0.319042139   0.194910295
   O        0.819050000   0.485720000   0.112570000    0   0   0
   O        0.666660000   0.180960000   0.112570000    0   0   0
   O        0.514280000   0.333340000   0.112570000    0   0   0
   O        0.680957272   0.014362846   0.194909856
   O        0.821788385   0.333224926   0.360556030
   O        0.666775614   0.488574957   0.360556124
   O        0.652376318   0.153125058   0.277338113
   O        0.500734916   0.347623757   0.277338123
   O        0.846874865  -0.000734269   0.277338041
   O        0.511426021   0.178212879   0.360556047
   Fe2      0.166664013   0.833337308   0.409451299
   Fe1     -0.000002422   0.500003543   0.451051094
   Fe2      0.166660000   0.833340000   0.061240000    0   0   0
   Fe1      0.333340000   0.666670000   0.000000000    0   0   0
   Fe2      0.000000000   0.500000000   0.081950000    0   0   0
   Fe1      0.333340000   0.666670000   0.143190000    0   0   0
   Fe2     -0.000005198   0.500005166   0.225538724
   Fe1      0.166660000   0.833340000   0.163900000    0   0   0
   Fe2      0.333327452   0.666671987   0.246584799
   Fe1      0.166662495   0.833338565   0.308651427
   Fe2      0.333330417   0.666670672   0.396298920
   Fe1     -0.000003873   0.500004576   0.328137392
   O        0.152380000   0.500000000   0.030620000    0   0   0
   O        0.000000000   0.652380000   0.030620000    0   0   0
   O        0.493114605   0.820585415   0.442431371
   O        0.327462127   0.506886475   0.442431144
   O        0.179415387   0.672539192   0.442431155
   O        0.347620000   0.847620000   0.030620000    0   0   0
   O        0.485638691   0.666610887   0.194910346
   O        0.333390108   0.819042192   0.194910214
   O        0.319050000   0.985720000   0.112570000    0   0   0
   O        0.166660000   0.680960000   0.112570000    0   0   0
   O        0.014280000   0.833340000   0.112570000    0   0   0
   O        0.180958984   0.514363858   0.194910061
   O        0.321788441   0.833225106   0.360556081
   O        0.166775442   0.988575063   0.360556110
   O        0.152376131   0.653125410   0.277338124
   O        0.000735220   0.847624458   0.277338005
   O        0.346875153   0.499266006   0.277338134
   O        0.011426050   0.678213001   0.360556059
   Fe2      0.666664011   0.833337086   0.409451389
   Fe1      0.499997365   0.500003643   0.451051294
   Fe2      0.666660000   0.833340000   0.061240000    0   0   0
   Fe1      0.833330000   0.666670000   0.000000000    0   0   0
   Fe2      0.500000000   0.500000000   0.081950000    0   0   0
   Fe1      0.833330000   0.666670000   0.143190000    0   0   0
   Fe2      0.499994218   0.500003611   0.225539273
   Fe1      0.666660000   0.833340000   0.163900000    0   0   0
   Fe2      0.833328491   0.666672211   0.246584848
   Fe1      0.666662622   0.833338209   0.308651450
   Fe2      0.833330463   0.666670636   0.396298920
   Fe1      0.499996331   0.500004588   0.328137541
   O        0.652380000   0.500000000   0.030620000    0   0   0
   O        0.500000000   0.652380000   0.030620000    0   0   0
   O        0.993114696   0.820585530   0.442431324
   O        0.827462342   0.506886424   0.442431009
   O        0.679415402   0.672539007   0.442431234
   O        0.847620000   0.847620000   0.030620000    0   0   0
   O        0.985637094   0.666611510   0.194910645
   O        0.833388422   0.819042438   0.194910203
   O        0.819050000   0.985720000   0.112570000    0   0   0
   O        0.666660000   0.680950000   0.112570000    0   0   0
   O        0.514280000   0.833340000   0.112570000    0   0   0
   O        0.680957752   0.514362481   0.194910377
   O        0.821788383   0.833224999   0.360556091
   O        0.666775439   0.988574757   0.360556167
   O        0.652376290   0.653125146   0.277338174
   O        0.500735108   0.847623809   0.277338072
   O        0.846875134   0.499265776   0.277338099
   O        0.511426047   0.678212724   0.360556191
   K_POINTS automatic
   2 2 1 0 0 0
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="qespresso.input">
           <module id="qespresso.input">     
                 <list cmlx:templateRef="CONTROL">
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">calculation</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">relax</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">restart_mode</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">from_scratch</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">wf_collect</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">prefix</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">Fe.USPP.001_2x2_145_vaccum</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">verbosity</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">high</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">etot_conv_thr</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">1.0D-9</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">forc_conv_thr</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">1.0D-5</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">tstress</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">tprnfor</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">dipfield</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
         </list>
      </list>
      <list cmlx:templateRef="SYSTEM">
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">ibrav</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">14</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">A</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">10.2304</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">B</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">10.2304</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">C</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">28.3548</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">cosAB</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">-0.5</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">cosAC</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">cosBC</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">nat</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">120</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">ntyp</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">3</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">ecutwfc</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">40.0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">ecutrho</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">320.0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">input_dft</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">PBE</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">occupations</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">smearing</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">degauss</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.02</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">smearing</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">gaussian</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">nspin</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">2</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">starting_magnetization(1)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">1.0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">starting_magnetization(2)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">-1.0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">starting_magnetization(3)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.0</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">lda_plus_u</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">lda_plus_u_kind</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0 , !type 2 not implemented, ignores J</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">Hubbard_U(1)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">4.2</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">Hubbard_U(2)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">4.2</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">Hubbard_J0(1)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.0, !Is ignored!</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">Hubbard_J0(2)</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.0, !Is ignored!</scalar>
         </list>
      </list>
      <list cmlx:templateRef="ELECTRONS">
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">electron_maxstep</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">800</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">conv_thr_init</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">1e-4</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">conv_thr</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">1e-9</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">startingpot</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">atomic</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">startingwfc</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">random</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">adaptive_thr</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">true</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">mixing_beta</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">0.14</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">diagonalization</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">cg</scalar>
         </list>
      </list>
      <list cmlx:templateRef="IONS">
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">ion_dynamics</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">bfgs</scalar>
         </list>
         <list>
            <scalar dataType="xsd:string" dictRef="cc:parameter">trust_radius_min</scalar>
            <scalar dataType="xsd:string" dictRef="cc:value">1.D-5</scalar>
         </list>
      </list>
      <list dictRef="species">
         <array dataType="xsd:string" dictRef="qex:specie" size="3">Fe1 Fe2 O</array>
         <array dataType="xsd:double" dictRef="cc:mass" size="3">55.84500 55.84500 15.99990</array>
         <array dataType="xsd:string" dictRef="qex:pseudopot" size="3">Fe.pbe-sp-van_ak.UPF Fe.pbe-sp-van_ak.UPF O.pbe-van_ak.UPF</array>
         <array dictRef="cc:elementType" size="3">Fe Fe O</array>
         <map id="speciesToAtomTypeMap">
            <link from="Fe1" to="Fe" />
            <link from="Fe2" to="Fe" />
            <link from="O" to="O" />
         </map>
      </list>
         <list cmlx:templateRef="atoms">
               <atom elementType="Fe" id="a1" specie="Fe2" x3="" xFract="0.166663898" y3="" yFract="0.333337143" z3="" zFract="0.409451359">Fe</atom>
               <atom elementType="Fe" id="a2" specie="Fe1" x3="" xFract="-2.447E-6" y3="" yFract="3.614E-6" z3="" zFract="0.451051249">Fe</atom>
               <atom elementType="Fe" id="a3" specie="Fe2" x3="" xFract="0.16666" y3="" yFract="0.33334" z3="" zFract="0.06124">Fe</atom>
               <atom elementType="Fe" id="a4" specie="Fe1" x3="" xFract="0.33334" y3="" yFract="0.16667" z3="" zFract="0.0">Fe</atom>
               <atom elementType="Fe" id="a5" specie="Fe2" x3="" xFract="0.0" y3="" yFract="0.0" z3="" zFract="0.08195">Fe</atom>
               <atom elementType="Fe" id="a6" specie="Fe1" x3="" xFract="0.33334" y3="" yFract="0.16667" z3="" zFract="0.14319">Fe</atom>
               <atom elementType="Fe" id="a7" specie="Fe2" x3="" xFract="-5.343E-6" y3="" yFract="5.009E-6" z3="" zFract="0.225538724">Fe</atom>
               <atom elementType="Fe" id="a8" specie="Fe1" x3="" xFract="0.16666" y3="" yFract="0.33334" z3="" zFract="0.1639">Fe</atom>
               <atom elementType="Fe" id="a9" specie="Fe2" x3="" xFract="0.333327346" y3="" yFract="0.166671997" z3="" zFract="0.246584781">Fe</atom>
               <atom elementType="Fe" id="a10" specie="Fe1" x3="" xFract="0.166662601" y3="" yFract="0.333338569" z3="" zFract="0.308651469">Fe</atom>
               <atom elementType="Fe" id="a11" specie="Fe2" x3="" xFract="0.333330456" y3="" yFract="0.166670754" z3="" zFract="0.396298854">Fe</atom>
               <atom elementType="Fe" id="a12" specie="Fe1" x3="" xFract="-3.95E-6" y3="" yFract="4.548E-6" z3="" zFract="0.328137387">Fe</atom>
               <atom elementType="O" id="a13" specie="O" x3="" xFract="0.15238" y3="" yFract="0.0" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a14" specie="O" x3="" xFract="0.0" y3="" yFract="0.15238" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a15" specie="O" x3="" xFract="0.493114653" y3="" yFract="0.320585686" z3="" zFract="0.442431216">O</atom>
               <atom elementType="O" id="a16" specie="O" x3="" xFract="0.327462379" y3="" yFract="0.006886637" z3="" zFract="0.442431019">O</atom>
               <atom elementType="O" id="a17" specie="O" x3="" xFract="0.17941542" y3="" yFract="0.172539124" z3="" zFract="0.442431172">O</atom>
               <atom elementType="O" id="a18" specie="O" x3="" xFract="0.34762" y3="" yFract="0.34762" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a19" specie="O" x3="" xFract="0.48563819" y3="" yFract="0.166610684" z3="" zFract="0.1949105">O</atom>
               <atom elementType="O" id="a20" specie="O" x3="" xFract="0.33338996" y3="" yFract="0.319042226" z3="" zFract="0.194910254">O</atom>
               <atom elementType="O" id="a21" specie="O" x3="" xFract="0.31905" y3="" yFract="0.48572" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a22" specie="O" x3="" xFract="0.16666" y3="" yFract="0.18096" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a23" specie="O" x3="" xFract="0.01428" y3="" yFract="0.33334" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a24" specie="O" x3="" xFract="0.180958728" y3="" yFract="0.014363721" z3="" zFract="0.194910054">O</atom>
               <atom elementType="O" id="a25" specie="O" x3="" xFract="0.321788281" y3="" yFract="0.333225075" z3="" zFract="0.360556075">O</atom>
               <atom elementType="O" id="a26" specie="O" x3="" xFract="0.16677536" y3="" yFract="0.488574984" z3="" zFract="0.360556183">O</atom>
               <atom elementType="O" id="a27" specie="O" x3="" xFract="0.152375882" y3="" yFract="0.153125384" z3="" zFract="0.277338078">O</atom>
               <atom elementType="O" id="a28" specie="O" x3="" xFract="7.35347E-4" y3="" yFract="0.347624423" z3="" zFract="0.277338029">O</atom>
               <atom elementType="O" id="a29" specie="O" x3="" xFract="0.346875072" y3="" yFract="-7.34132E-4" z3="" zFract="0.277338119">O</atom>
               <atom elementType="O" id="a30" specie="O" x3="" xFract="0.011425967" y3="" yFract="0.17821285" z3="" zFract="0.360556085">O</atom>
               <atom elementType="Fe" id="a31" specie="Fe2" x3="" xFract="0.666663975" y3="" yFract="0.333337151" z3="" zFract="0.409451269">Fe</atom>
               <atom elementType="Fe" id="a32" specie="Fe1" x3="" xFract="0.499997414" y3="" yFract="3.47E-6" z3="" zFract="0.451051255">Fe</atom>
               <atom elementType="Fe" id="a33" specie="Fe2" x3="" xFract="0.66666" y3="" yFract="0.33334" z3="" zFract="0.06124">Fe</atom>
               <atom elementType="Fe" id="a34" specie="Fe1" x3="" xFract="0.83333" y3="" yFract="0.16667" z3="" zFract="0.0">Fe</atom>
               <atom elementType="Fe" id="a35" specie="Fe2" x3="" xFract="0.5" y3="" yFract="0.0" z3="" zFract="0.08195">Fe</atom>
               <atom elementType="Fe" id="a36" specie="Fe1" x3="" xFract="0.83333" y3="" yFract="0.16667" z3="" zFract="0.14319">Fe</atom>
               <atom elementType="Fe" id="a37" specie="Fe2" x3="" xFract="0.499993955" y3="" yFract="3.637E-6" z3="" zFract="0.225539296">Fe</atom>
               <atom elementType="Fe" id="a38" specie="Fe1" x3="" xFract="0.66666" y3="" yFract="0.33334" z3="" zFract="0.1639">Fe</atom>
               <atom elementType="Fe" id="a39" specie="Fe2" x3="" xFract="0.833328682" y3="" yFract="0.166672502" z3="" zFract="0.246584853">Fe</atom>
               <atom elementType="Fe" id="a40" specie="Fe1" x3="" xFract="0.666662589" y3="" yFract="0.333338201" z3="" zFract="0.308651364">Fe</atom>
               <atom elementType="Fe" id="a41" specie="Fe2" x3="" xFract="0.833330375" y3="" yFract="0.166670545" z3="" zFract="0.396298876">Fe</atom>
               <atom elementType="Fe" id="a42" specie="Fe1" x3="" xFract="0.499996285" y3="" yFract="4.543E-6" z3="" zFract="0.328137528">Fe</atom>
               <atom elementType="O" id="a43" specie="O" x3="" xFract="0.65238" y3="" yFract="0.0" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a44" specie="O" x3="" xFract="0.5" y3="" yFract="0.15238" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a45" specie="O" x3="" xFract="0.993114488" y3="" yFract="0.320585299" z3="" zFract="0.442431331">O</atom>
               <atom elementType="O" id="a46" specie="O" x3="" xFract="0.827462315" y3="" yFract="0.006886443" z3="" zFract="0.442431085">O</atom>
               <atom elementType="O" id="a47" specie="O" x3="" xFract="0.679415215" y3="" yFract="0.172538968" z3="" zFract="0.442431093">O</atom>
               <atom elementType="O" id="a48" specie="O" x3="" xFract="0.84762" y3="" yFract="0.34762" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a49" specie="O" x3="" xFract="0.985636731" y3="" yFract="0.166611225" z3="" zFract="0.194910522">O</atom>
               <atom elementType="O" id="a50" specie="O" x3="" xFract="0.83338884" y3="" yFract="0.319042139" z3="" zFract="0.194910295">O</atom>
               <atom elementType="O" id="a51" specie="O" x3="" xFract="0.81905" y3="" yFract="0.48572" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a52" specie="O" x3="" xFract="0.66666" y3="" yFract="0.18096" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a53" specie="O" x3="" xFract="0.51428" y3="" yFract="0.33334" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a54" specie="O" x3="" xFract="0.680957272" y3="" yFract="0.014362846" z3="" zFract="0.194909856">O</atom>
               <atom elementType="O" id="a55" specie="O" x3="" xFract="0.821788385" y3="" yFract="0.333224926" z3="" zFract="0.36055603">O</atom>
               <atom elementType="O" id="a56" specie="O" x3="" xFract="0.666775614" y3="" yFract="0.488574957" z3="" zFract="0.360556124">O</atom>
               <atom elementType="O" id="a57" specie="O" x3="" xFract="0.652376318" y3="" yFract="0.153125058" z3="" zFract="0.277338113">O</atom>
               <atom elementType="O" id="a58" specie="O" x3="" xFract="0.500734916" y3="" yFract="0.347623757" z3="" zFract="0.277338123">O</atom>
               <atom elementType="O" id="a59" specie="O" x3="" xFract="0.846874865" y3="" yFract="-7.34269E-4" z3="" zFract="0.277338041">O</atom>
               <atom elementType="O" id="a60" specie="O" x3="" xFract="0.511426021" y3="" yFract="0.178212879" z3="" zFract="0.360556047">O</atom>
               <atom elementType="Fe" id="a61" specie="Fe2" x3="" xFract="0.166664013" y3="" yFract="0.833337308" z3="" zFract="0.409451299">Fe</atom>
               <atom elementType="Fe" id="a62" specie="Fe1" x3="" xFract="-2.422E-6" y3="" yFract="0.500003543" z3="" zFract="0.451051094">Fe</atom>
               <atom elementType="Fe" id="a63" specie="Fe2" x3="" xFract="0.16666" y3="" yFract="0.83334" z3="" zFract="0.06124">Fe</atom>
               <atom elementType="Fe" id="a64" specie="Fe1" x3="" xFract="0.33334" y3="" yFract="0.66667" z3="" zFract="0.0">Fe</atom>
               <atom elementType="Fe" id="a65" specie="Fe2" x3="" xFract="0.0" y3="" yFract="0.5" z3="" zFract="0.08195">Fe</atom>
               <atom elementType="Fe" id="a66" specie="Fe1" x3="" xFract="0.33334" y3="" yFract="0.66667" z3="" zFract="0.14319">Fe</atom>
               <atom elementType="Fe" id="a67" specie="Fe2" x3="" xFract="-5.198E-6" y3="" yFract="0.500005166" z3="" zFract="0.225538724">Fe</atom>
               <atom elementType="Fe" id="a68" specie="Fe1" x3="" xFract="0.16666" y3="" yFract="0.83334" z3="" zFract="0.1639">Fe</atom>
               <atom elementType="Fe" id="a69" specie="Fe2" x3="" xFract="0.333327452" y3="" yFract="0.666671987" z3="" zFract="0.246584799">Fe</atom>
               <atom elementType="Fe" id="a70" specie="Fe1" x3="" xFract="0.166662495" y3="" yFract="0.833338565" z3="" zFract="0.308651427">Fe</atom>
               <atom elementType="Fe" id="a71" specie="Fe2" x3="" xFract="0.333330417" y3="" yFract="0.666670672" z3="" zFract="0.39629892">Fe</atom>
               <atom elementType="Fe" id="a72" specie="Fe1" x3="" xFract="-3.873E-6" y3="" yFract="0.500004576" z3="" zFract="0.328137392">Fe</atom>
               <atom elementType="O" id="a73" specie="O" x3="" xFract="0.15238" y3="" yFract="0.5" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a74" specie="O" x3="" xFract="0.0" y3="" yFract="0.65238" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a75" specie="O" x3="" xFract="0.493114605" y3="" yFract="0.820585415" z3="" zFract="0.442431371">O</atom>
               <atom elementType="O" id="a76" specie="O" x3="" xFract="0.327462127" y3="" yFract="0.506886475" z3="" zFract="0.442431144">O</atom>
               <atom elementType="O" id="a77" specie="O" x3="" xFract="0.179415387" y3="" yFract="0.672539192" z3="" zFract="0.442431155">O</atom>
               <atom elementType="O" id="a78" specie="O" x3="" xFract="0.34762" y3="" yFract="0.84762" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a79" specie="O" x3="" xFract="0.485638691" y3="" yFract="0.666610887" z3="" zFract="0.194910346">O</atom>
               <atom elementType="O" id="a80" specie="O" x3="" xFract="0.333390108" y3="" yFract="0.819042192" z3="" zFract="0.194910214">O</atom>
               <atom elementType="O" id="a81" specie="O" x3="" xFract="0.31905" y3="" yFract="0.98572" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a82" specie="O" x3="" xFract="0.16666" y3="" yFract="0.68096" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a83" specie="O" x3="" xFract="0.01428" y3="" yFract="0.83334" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a84" specie="O" x3="" xFract="0.180958984" y3="" yFract="0.514363858" z3="" zFract="0.194910061">O</atom>
               <atom elementType="O" id="a85" specie="O" x3="" xFract="0.321788441" y3="" yFract="0.833225106" z3="" zFract="0.360556081">O</atom>
               <atom elementType="O" id="a86" specie="O" x3="" xFract="0.166775442" y3="" yFract="0.988575063" z3="" zFract="0.36055611">O</atom>
               <atom elementType="O" id="a87" specie="O" x3="" xFract="0.152376131" y3="" yFract="0.65312541" z3="" zFract="0.277338124">O</atom>
               <atom elementType="O" id="a88" specie="O" x3="" xFract="7.3522E-4" y3="" yFract="0.847624458" z3="" zFract="0.277338005">O</atom>
               <atom elementType="O" id="a89" specie="O" x3="" xFract="0.346875153" y3="" yFract="0.499266006" z3="" zFract="0.277338134">O</atom>
               <atom elementType="O" id="a90" specie="O" x3="" xFract="0.01142605" y3="" yFract="0.678213001" z3="" zFract="0.360556059">O</atom>
               <atom elementType="Fe" id="a91" specie="Fe2" x3="" xFract="0.666664011" y3="" yFract="0.833337086" z3="" zFract="0.409451389">Fe</atom>
               <atom elementType="Fe" id="a92" specie="Fe1" x3="" xFract="0.499997365" y3="" yFract="0.500003643" z3="" zFract="0.451051294">Fe</atom>
               <atom elementType="Fe" id="a93" specie="Fe2" x3="" xFract="0.66666" y3="" yFract="0.83334" z3="" zFract="0.06124">Fe</atom>
               <atom elementType="Fe" id="a94" specie="Fe1" x3="" xFract="0.83333" y3="" yFract="0.66667" z3="" zFract="0.0">Fe</atom>
               <atom elementType="Fe" id="a95" specie="Fe2" x3="" xFract="0.5" y3="" yFract="0.5" z3="" zFract="0.08195">Fe</atom>
               <atom elementType="Fe" id="a96" specie="Fe1" x3="" xFract="0.83333" y3="" yFract="0.66667" z3="" zFract="0.14319">Fe</atom>
               <atom elementType="Fe" id="a97" specie="Fe2" x3="" xFract="0.499994218" y3="" yFract="0.500003611" z3="" zFract="0.225539273">Fe</atom>
               <atom elementType="Fe" id="a98" specie="Fe1" x3="" xFract="0.66666" y3="" yFract="0.83334" z3="" zFract="0.1639">Fe</atom>
               <atom elementType="Fe" id="a99" specie="Fe2" x3="" xFract="0.833328491" y3="" yFract="0.666672211" z3="" zFract="0.246584848">Fe</atom>
               <atom elementType="Fe" id="a100" specie="Fe1" x3="" xFract="0.666662622" y3="" yFract="0.833338209" z3="" zFract="0.30865145">Fe</atom>
               <atom elementType="Fe" id="a101" specie="Fe2" x3="" xFract="0.833330463" y3="" yFract="0.666670636" z3="" zFract="0.39629892">Fe</atom>
               <atom elementType="Fe" id="a102" specie="Fe1" x3="" xFract="0.499996331" y3="" yFract="0.500004588" z3="" zFract="0.328137541">Fe</atom>
               <atom elementType="O" id="a103" specie="O" x3="" xFract="0.65238" y3="" yFract="0.5" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a104" specie="O" x3="" xFract="0.5" y3="" yFract="0.65238" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a105" specie="O" x3="" xFract="0.993114696" y3="" yFract="0.82058553" z3="" zFract="0.442431324">O</atom>
               <atom elementType="O" id="a106" specie="O" x3="" xFract="0.827462342" y3="" yFract="0.506886424" z3="" zFract="0.442431009">O</atom>
               <atom elementType="O" id="a107" specie="O" x3="" xFract="0.679415402" y3="" yFract="0.672539007" z3="" zFract="0.442431234">O</atom>
               <atom elementType="O" id="a108" specie="O" x3="" xFract="0.84762" y3="" yFract="0.84762" z3="" zFract="0.03062">O</atom>
               <atom elementType="O" id="a109" specie="O" x3="" xFract="0.985637094" y3="" yFract="0.66661151" z3="" zFract="0.194910645">O</atom>
               <atom elementType="O" id="a110" specie="O" x3="" xFract="0.833388422" y3="" yFract="0.819042438" z3="" zFract="0.194910203">O</atom>
               <atom elementType="O" id="a111" specie="O" x3="" xFract="0.81905" y3="" yFract="0.98572" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a112" specie="O" x3="" xFract="0.66666" y3="" yFract="0.68095" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a113" specie="O" x3="" xFract="0.51428" y3="" yFract="0.83334" z3="" zFract="0.11257">O</atom>
               <atom elementType="O" id="a114" specie="O" x3="" xFract="0.680957752" y3="" yFract="0.514362481" z3="" zFract="0.194910377">O</atom>
               <atom elementType="O" id="a115" specie="O" x3="" xFract="0.821788383" y3="" yFract="0.833224999" z3="" zFract="0.360556091">O</atom>
               <atom elementType="O" id="a116" specie="O" x3="" xFract="0.666775439" y3="" yFract="0.988574757" z3="" zFract="0.360556167">O</atom>
               <atom elementType="O" id="a117" specie="O" x3="" xFract="0.65237629" y3="" yFract="0.653125146" z3="" zFract="0.277338174">O</atom>
               <atom elementType="O" id="a118" specie="O" x3="" xFract="0.500735108" y3="" yFract="0.847623809" z3="" zFract="0.277338072">O</atom>
               <atom elementType="O" id="a119" specie="O" x3="" xFract="0.846875134" y3="" yFract="0.499265776" z3="" zFract="0.277338099">O</atom>
               <atom elementType="O" id="a120" specie="O" x3="" xFract="0.511426047" y3="" yFract="0.678212724" z3="" zFract="0.360556191">O</atom>
         </list>
      <list cmlx:templateRef="KPOINTS">
         <scalar dataType="xsd:string" dictRef="qex:meshScheme">automatic</scalar>
         <array dataType="xsd:integer" dictRef="qex:subdivisionN" size="3">2 2 1</array>
         <array dataType="xsd:double" dictRef="qex:shiftS" size="3">0 0 0</array>
      </list>
              
              
           </module> 
   </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*\u0026\S+.*" endPattern="\s*\u002F\s*" endPattern2="\s*\u0026\S+.*" endPattern3="~" endOffset="0" repeat="*">    <record>\s*\u0026{X,x:section}</record>    <record repeat="*">\s*!\s*</record>    <record id="section" repeat="*">{X,cc:parameter}=\s*['\.]?{X,cc:value}['\.]?\s*,?\s*</record>    <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='section']" name="cmlx:templateRef" value="$string(preceding-sibling::cml:list/cml:scalar[@dictRef='x:section']/text())" />          
           </template>  <template pattern="\s*K_POINTS.*" endPattern="\s*" endPattern2="((?!(\s*[0-9]+){3,}).)*" endPattern3="~">    <record id="KPOINTS">\s*K_POINTS{X,qex:meshScheme}</record>    <record id="kpoints_info" repeat="*">{3I,qex:subdivisionN}{3F,qex:shiftS}</record>    <transform process="moveRelative" xpath=".//cml:array" to="preceding::cml:scalar[@dictRef='qex:meshScheme']/parent::cml:list" />    <transform process="addAttribute" xpath="./cml:list[child::cml:list]" name="cmlx:templateRef" value="KPOINTS" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />                 
           </template>  <template id="species" name="Atomic species" pattern="\s*ATOMIC_SPECIES.*" endPattern="\s*((?!\S+\s+[0-9\.\-]+\s+\S+).)*" endPattern2="~">    <record repeat="1" />    <record repeat="*">{A,qex:specie}{F,cc:mass}{X,qex:pseudopot}</record>    <transform process="addChild" xpath=".//cml:list[child::cml:scalar]" elementName="cml:scalar" dictRef="cc:elementType" />    <transform process="setValue" xpath=".//cml:scalar[@dictRef='cc:elementType']" value="$string(tokenize(.//preceding-sibling::cml:scalar[@dictRef='qex:pseudopot'],'[\._]')[1])" />    <transform process="addMap" xpath="." id="speciesToAtomTypeMap" from=".//cml:scalar[@dictRef='qex:specie']" to=".//cml:scalar[@dictRef='cc:elementType']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='qex:specie']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:mass']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='qex:pseudopot']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:elementType']" />    <transform process="addChild" xpath="." elementName="cml:list" dictRef="species" />    <transform process="move" xpath=".//cml:scalar" to="./cml:list[@dictRef='species']" />    <transform process="move" xpath=".//cml:array" to="./cml:list[@dictRef='species']" />    <transform process="move" xpath=".//cml:map" to="./cml:list[@dictRef='species']" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />          
           </template>  <template id="positions" name="Atomic positions" pattern="\s*ATOMIC_POSITIONS.*" endPattern="(?!\s*\S+(\s+[0-9\.-]+){3}).*" endPattern2="~">    <record>\s*ATOMIC_POSITIONS{X,qex:coordtype}</record>    <record id="atoms" repeat="*">{A,qex:specie}{F,x:coordX}{F,x:coordY}{F,x:coordZ}.*</record>    <transform process="moveRelative" xpath=".//cml:scalar[@dictRef='qex:coordtype']" to="./parent::cml:list/following-sibling::cml:list[@cmlx:templateRef='atom']" position="1" />    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='x:coordX']" args="operator=multiply operand=$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'bohr')) then 0.529177249 else 1)" />    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='x:coordY']" args="operator=multiply operand=$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'bohr')) then 0.529177249 else 1)" />    <transform process="operateScalar" xpath=".//cml:scalar[@dictRef='x:coordZ']" args="operator=multiply operand=$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'bohr')) then 0.529177249 else 1)" />    <transform process="setValue" xpath="//cml:scalar[@dictRef='qex:coordtype' and contains(lower-case(text()), 'bohr')]" value="angstrom" />
           </template>  <transform process="addChild" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list" elementName="cml:atom" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="id" value="$string(concat('a',count(.//preceding::cml:atom) + 1))" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="specie" value="$string(./preceding-sibling::cml:scalar[@dictRef='qex:specie'])" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="x3" value="$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'angstrom')) then ./preceding-sibling::cml:scalar[@dictRef='x:coordX'] else '')" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="y3" value="$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'angstrom')) then ./preceding-sibling::cml:scalar[@dictRef='x:coordY'] else '')" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="z3" value="$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'angstrom')) then ./preceding-sibling::cml:scalar[@dictRef='x:coordZ'] else '')" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="xFract" value="$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'crystal')) then ./preceding-sibling::cml:scalar[@dictRef='x:coordX'] else '')" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="yFract" value="$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'crystal')) then ./preceding-sibling::cml:scalar[@dictRef='x:coordY'] else '')" />  <transform process="addAttribute" xpath=".//cml:list[@cmlx:templateRef='atoms']/cml:list/cml:atom" name="zFract" value="$number(if(contains(//cml:scalar[@dictRef='qex:coordtype']/text(), 'crystal')) then ./preceding-sibling::cml:scalar[@dictRef='x:coordZ'] else '')" />  <transform process="setValue" xpath=".//cml:atom" map="//cml:map[@id='speciesToAtomTypeMap']" value="$string(./@specie)" />  <transform process="setValue" xpath=".//cml:atom" value="$string(concat(upper-case(substring(./text(), 1, 1)), lower-case(substring(./text(), 2))))" />  <transform process="addAttribute" xpath=".//cml:atom" name="elementType" value="$string(./text())" />  <transform process="pullup" xpath=".//cml:atom" />  <transform process="delete" xpath=".//cml:list[@cmlx:templateRef='atoms']//cml:scalar" />  <transform process="move" xpath="//cml:scalar[@dictRef='qex:coordtype']" to="//cml:list[@cmlx:templateRef='atoms']" />  <transform process="delete" xpath="//cml:scalar[@dictRef='qex:coordtype']" />  <transform process="delete" xpath=".//cml:list[@cmlx:templateRef='missingID']" />  <transform process="pullup" xpath="./cml:module/cml:list" />  <transform process="delete" xpath="./cml:module" />  <transform process="delete" xpath=".//cml:list[count(*)= 0]" />  <transform process="delete" xpath="//cml:list/text()" />  <transform process="delete" xpath="//cml:list/text()" />  <transform process="delete" xpath="//cml:module/text()" />        
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
