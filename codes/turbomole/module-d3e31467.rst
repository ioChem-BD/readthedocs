module
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/turbomole/title-d3e31478
   /codes/turbomole/ricc2-d3e31505
   /codes/turbomole/atomcoord-d3e31533
   /codes/turbomole/population.analysis-d3e31930
   /codes/turbomole/basisset-d3e32167
   /codes/turbomole/symmetry-d3e32224
   /codes/turbomole/ground.state-d3e32278
   /codes/turbomole/orbitals-d3e32305
   /codes/turbomole/excitation-d3e32382
   /codes/turbomole/totalroots-d3e32656
   /codes/turbomole/cosmo-d3e32666
   /codes/turbomole/electrostatic.moments-d3e33247
   /codes/turbomole/orbitalenergies-d3e33400
   /codes/turbomole/molecular.orbitals.statistics-d3e33861
   /codes/turbomole/s2-d3e33914
   /codes/turbomole/convergence.info-d3e33938
   /codes/turbomole/nuclear.repulsion-d3e34090
   /codes/turbomole/energy-d3e34122
   /codes/turbomole/zero.point.energy-d3e34219
   /codes/turbomole/fit.pointcharges-d3e34247

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
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | module                            |
   +-----------------------------------+-----------------------------------+
   | name                              | Generic module capturing template |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s{                              |
   |                                   | 20,}(this\sis\s*)?\w\s\w\s\w\s.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\*\*\*\*\                     |
   |                                   | s*\w*\s:\sall\sdone\s*\*\*\*\*.\* |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | module.xml                        |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

                                     R I C C 2 - PROGRAM

                             the quantum chemistry groups
                                at the universities in
                              Karlsruhe, Bochum > Mainz
                                      Germany

   ...
      ****  ricc2 : all done  ****
       

**Comment.**

::

                                  this is S T A T P T


                        hessian and coordinate update for
                             stationary point search

                        by barbara unterreiner, marek sierka,
                              and reinhart ahlrichs

                             quantum chemistry group
                             universitaet  karlsruhe
                                     germany

   ...
      ****  statpt : all done  ****
       

**Comment.**

::

       
                                    r d g r a d

                             gradient for ridft program

                           by K.Eichkorn, O.Treutler, H.Oehm,
                                M.Haeser and R.Ahlrichs
                     (Chemical Physics Letters 242 (1995) 652-660)
                       parallel version: M.v.Arnim  &  R.Ahlrichs
                               quantum chemistry group
                                university  karlsruhe
                                      germany

       ...
     ****  rdgrad : all done  ****
       
       

**Template definition.**

.. code:: xml

   <templateList>  <xi:include href="title.xml" />  <xi:include href="ricc2/ricc2.xml" />  <xi:include href="atomcoord.xml" />  <xi:include href="population/population.analysis.xml" />  <xi:include href="basisset.xml" />  <xi:include href="symmetry.xml" />  <xi:include href="ground.state.xml" />  <xi:include href="orbitals.xml" />  <xi:include href="tddft/excitation.xml" />  <xi:include href="tddft/totalroots.xml" />  <xi:include href="cosmo.xml" />  <xi:include href="electrostatic.moments.xml" />  <xi:include href="molecularorbitals/molecular.orbitals.xml" />  <xi:include href="molecularorbitals/molecular.orbital.statistic.xml" />  <xi:include href="s2.xml" />  <xi:include href="minimumts/convergence.info.xml" />  <xi:include href="nuclear.repulsion.xml" />  <xi:include href="energy.xml" />  <xi:include href="zero.point.energy.xml" />  <xi:include href="fit/fit.pointcharges.xml" />                      
           </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
