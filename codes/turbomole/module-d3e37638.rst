module
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/turbomole/title-d3e37649
   /codes/turbomole/ricc2-d3e37676
   /codes/turbomole/atomcoord-d3e37704
   /codes/turbomole/population.analysis-d3e38101
   /codes/turbomole/basisset-d3e38338
   /codes/turbomole/symmetry-d3e38395
   /codes/turbomole/ground.state-d3e38449
   /codes/turbomole/orbitals-d3e38476
   /codes/turbomole/excitation-d3e38553
   /codes/turbomole/totalroots-d3e38827
   /codes/turbomole/cosmo-d3e38837
   /codes/turbomole/electrostatic.moments-d3e39418
   /codes/turbomole/orbitalenergies-d3e39571
   /codes/turbomole/molecular.orbitals.statistics-d3e40032
   /codes/turbomole/s2-d3e40085
   /codes/turbomole/convergence.info-d3e40109
   /codes/turbomole/nuclear.repulsion-d3e40261
   /codes/turbomole/energy-d3e40293
   /codes/turbomole/zero.point.energy-d3e40390
   /codes/turbomole/fit.pointcharges-d3e40418

======

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
   | *source*                                                                                                                   | Turbomole log                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | module                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Generic module capturing template                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s{20,}(this&#92;sis&#92;s*)?&#92;w&#92;s&#92;w&#92;s&#92;w&#92;s.\*                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;*&#92;*&#92;*&#92;*&#92;s*&#92;w*&#92;s:&#92;sall&#92;sdone&#92;s*&#92;*&#92;*&#92;*&#92;*.\*                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | module.xml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Comment**

::

                                     R I C C 2 - PROGRAM

                             the quantum chemistry groups
                                at the universities in
                              Karlsruhe, Bochum > Mainz
                                      Germany

   ...
      ****  ricc2 : all done  ****
       

.. container:: formalpara-title

   **Comment**

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
       

.. container:: formalpara-title

   **Comment**

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
       
       

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <xi:include href="title.xml" />  <xi:include href="ricc2/ricc2.xml" />  <xi:include href="atomcoord.xml" />  <xi:include href="population/population.analysis.xml" />  <xi:include href="basisset.xml" />  <xi:include href="symmetry.xml" />  <xi:include href="ground.state.xml" />  <xi:include href="orbitals.xml" />  <xi:include href="tddft/excitation.xml" />  <xi:include href="tddft/totalroots.xml" />  <xi:include href="cosmo.xml" />  <xi:include href="electrostatic.moments.xml" />  <xi:include href="molecularorbitals/molecular.orbitals.xml" />  <xi:include href="molecularorbitals/molecular.orbital.statistic.xml" />  <xi:include href="s2.xml" />  <xi:include href="minimumts/convergence.info.xml" />  <xi:include href="nuclear.repulsion.xml" />  <xi:include href="energy.xml" />  <xi:include href="zero.point.energy.xml" />  <xi:include href="fit/fit.pointcharges.xml" />                      
           </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
