turbomole.control
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/turbomole/atoms-d3e38272
   /codes/turbomole/methods-d3e38429
   /codes/turbomole/vibrations-d3e38473
   /codes/turbomole/dispersion-d3e38591
   /codes/turbomole/soes-d3e38613
   /codes/turbomole/parameters-d3e38672
   /codes/turbomole/orbitals.control-d3e38786

=================

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image0|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | Turbomole control file                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | turbomole.control                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Turbomole control file                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

**Comment.**

::

          
   $symmetry c1
   $atoms
   fe 1                                                                           \
      basis =fe def2-SV(P)
   n  2-7                                                                         \
      basis =n def2-SV(P)
   h  8-31                                                                        \
      basis =h def2-SV(P)
   c  32-61                                                                       \
      basis =c def2-SV(P)
   $soes
   a  4
   #
   # NumForce insertion:
   #
   $scfconv 8
   $drvopt
      frequency analysis only nofreeze
   $hessian  file=hessian
   $dipgrad  file=dipgrad
   $grad  file=gradient
   #
   # end of NumForce insertion.
   #
   $title
   Fe(bipy)3 MLCT
   $operating system unix
       ...
           
       

**Template definition.**

.. code:: xml

   <templateList id="init">  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/atoms.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/methods.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/vibrations/vibrations.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/dispersion.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/soes.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/parameters.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/orbitals.xml" />      
       </templateList>
   <transform process="move" xpath="//cml:module[@cmlx:templateRef='vibrations']/cml:module" to="//cml:module[@cmlx:templateRef='vibrations'][1]" />
   <transform process="delete" xpath="//node()[count(*)!=0]/text()" />
   <transform process="delete" xpath="//cml:list[count(*)=0]" />
   <transform process="delete" xpath="//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
