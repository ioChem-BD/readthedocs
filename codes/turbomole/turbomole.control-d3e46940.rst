turbomole.control
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/turbomole/atoms-d3e46947
   /codes/turbomole/methods-d3e47104
   /codes/turbomole/vibrations-d3e47148
   /codes/turbomole/dispersion-d3e47266
   /codes/turbomole/soes-d3e47288
   /codes/turbomole/parameters-d3e47347
   /codes/turbomole/orbitals.control-d3e47461

=================

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
   | *source*                                                                                                                   | Turbomole control file                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | turbomole.control                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Turbomole control file                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Comment**

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
           
       

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList id="init">  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/atoms.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/methods.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/vibrations/vibrations.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/dispersion.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/soes.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/parameters.xml" />  <xi:include href="JUMBO_HOME/jumbo-converters-compchem/jumbo-converters-compchem-turbomole/src/main/resources/org/xmlcml/cml/converters/compchem/turbomole/control/templates/orbitals.xml" />      
       </templateList>
   <transform process="move" xpath="//cml:module[@cmlx:templateRef='vibrations']/cml:module" to="//cml:module[@cmlx:templateRef='vibrations'][1]" />
   <transform process="delete" xpath="//node()[count(*)!=0]/text()" />
   <transform process="delete" xpath="//cml:list[count(*)=0]" />
   <transform process="delete" xpath="//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
