.. _coupledClusterEnergy-d3e29108:

coupledClusterEnergy
====================

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
   | id                                | coupledClusterEnergy              |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{15,                         |
   |                                   | }$\s*COUPLED\sCLUSTER\sENERGY\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s*-{15,}                    |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*\*{20,}\s\*                   |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | ci/coupledcluster.xml             |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ----------------------
   COUPLED CLUSTER ENERGY
   ----------------------

   E(0)                                       ...   -227.635883412
   E(CORR)                                    ...     -0.665826163
   E(TOT)                                     ...   -228.301709575
   Singles Norm <S|S>**1/2                    ...      0.074835151
   T1 diagnostic                              ...      0.015275661

   ------------------
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="coupledClusterEnergy">
           <module cmlx:templateRef="coupledClusterEnergy">
               <scalar dataType="xsd:double" dictRef="o:t1diag">0.015275661</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="4" />
   <record>\s*E\(0\)\s*\.\.\.{F,o:e0}</record>
   <record>\s*E\(CORR\)\s*\.\.\.{F,o:ecorr}</record>
   <record>\s*E\(TOT\)\s*\.\.\.{F,o:etot}</record>
   <record>\s*T1\sdiagnostic\s*\.\.\.{F,o:t1diag}</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
