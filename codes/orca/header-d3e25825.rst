.. _header-d3e25825:

header
======

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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | header                            |
   +-----------------------------------+-----------------------------------+
   | name                              | Orca header                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s+\*\s+O\s+R\s+C\s+A\s+\*\s\*   |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*INPUT\sFILE\s\*               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | -1                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | header.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

                                    *****************
                                    * O   R   C   A *
                                    *****************

              --- An Ab Initio, DFT and Semiempirical electronic structure package ---

                     ######################################################
                     #                        -***-                       #
                     #  Department of molecular theory and spectroscopy   #
                     #              Directorship: Frank Neese             #
                     #   Max Planck Institute for Bioinorganic Chemistry  #
                     #                  D-45470 Muelheim/Ruhr             #
                     #                       Germany                      #
                     #                                                    #
                     #                  All rights reserved               #
                     #                        -***-                       #
                     ######################################################


                            Program Version 2.9.0 -  RELEASE  -


    With contributions from (in alphabetic order):
      Ute Becker             : Parallelization
      Dmitry Ganyushin       : Spin-Orbit,Spin-Spin,Magnetic field MRCI
      Andreas Hansen         : Spin unrestricted coupled pair/coupled cluster methods
      Dimitrios Liakos       : Parallel MDCI
      Robert Izsak           : Overlap fitted RIJCOSX
      Christian Kollmar      : KDIIS, orbital optimized coupled pair methods, Brueckner methods
      Simone Kossmann        : Meta GGA functionals, improved MP2 methods
      Taras Petrenko         : TD-DFT gradient, Resonance Raman, ABS, fluorescence, XAS, NRVS
      Christoph Reimann      : Effective Core Potentials
      Michael Roemelt        : Restricted open shell CI
      Christoph Riplinger    : Improved optimizer, TS searches, QM/MM
      Barbara Sandhoefer     : DKH, picture change effects
      Igor Schapiro          : Molecular dynamics
      Kantharuban Sivalingam : CASSCF and multireference perturbation theory
      Boris Wezisla          : Elementary symmetry handling
      Frank Wennmohs         : Technical directorship


    We gratefully acknowledge several collegues who have allowed us to
    interface, adapt or use parts of their codes:
      Stefan Grimme                                : VdW corrections, initial TS optimization
                                                     and many helpful discussions
      Ed Valeev                                    : LibInt (2-el integral package), F12 methods
      Andreas Klamt, Michael Diedenhofen           : otool_cosmo (COSMO solvation model)
      Frank Weinhold                               : gennbo (NPA and NBO analysis)


    Your calculation uses the libint2 library for the computation of 2-el integrals
    For citations please refer to: http://libint.valeyev.net

   Your calculation utilizes the basis: Ahlrichs-VDZ
   Cite in your paper:
   H - Kr: A. Schaefer, H. Horn and R. Ahlrichs, J. Chem. Phys. 97, 2571 (1992).



   *****************************************
   The coordinations will be read from file: ete.xyz
   *****************************************


   ================================================================================
                                           WARNINGS
                          Please study these warnings very carefully!
   ================================================================================
   Now building the actual basis set


   INFO   : the flag for use of LIBINT has been found!

   ================================================================================
                                          INPUT FILE
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="header">
          <module cmlx:templateRef="header">
             <module cmlx:templateRef="program">
                <scalar dataType="xsd:string" dictRef="cc:programVersion">2.9.0</scalar>
                <scalar dataType="xsd:string" dictRef="cc:programSubversion">RELEASE</scalar>
             </module>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="program" pattern="\s+Program\sVersion.*" endPattern=".*">    <record>\s*Program\sVersion{A,cc:programVersion}-{X,cc:programSubversion}-</record>
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
