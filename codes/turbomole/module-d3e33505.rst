module
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/turbomole/title-d3e33516
   /codes/turbomole/ricc2-d3e33543
   /codes/turbomole/atomcoord-d3e33571
   /codes/turbomole/population.analysis-d3e33968
   /codes/turbomole/basisset-d3e34205
   /codes/turbomole/symmetry-d3e34262
   /codes/turbomole/ground.state-d3e34316
   /codes/turbomole/orbitals-d3e34343
   /codes/turbomole/excitation-d3e34420
   /codes/turbomole/totalroots-d3e34694
   /codes/turbomole/cosmo-d3e34704
   /codes/turbomole/electrostatic.moments-d3e35285
   /codes/turbomole/orbitalenergies-d3e35438
   /codes/turbomole/molecular.orbitals.statistics-d3e35899
   /codes/turbomole/s2-d3e35952
   /codes/turbomole/convergence.info-d3e35976
   /codes/turbomole/nuclear.repulsion-d3e36128
   /codes/turbomole/energy-d3e36160
   /codes/turbomole/zero.point.energy-d3e36257
   /codes/turbomole/fit.pointcharges-d3e36285

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
