.. _rhfTriplesCorr-d3e28489:

rhfTriplesCorr
==============

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
   | id                                | rhfTriplesCorr                    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{15                          |
   |                                   | ,}$\s*RHF\sTRIPLES\sCORRECTION.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*W\(HF\)                       |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | rhftriplescorr.xml                |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ----------------------
   RHF TRIPLES CORRECTION (Algorithm 1)
   ----------------------

   Multiplier for the singles contribution    ...      1.000000000

   10% done
   20% done
   30% done
   40% done
   50% done
   60% done
   70% done
   80% done
   90% done

   Triples Correction (T)                     ...     -0.019986933
   Final correlation energy                   ...     -0.685813096
   E(CCSD)                                    ...   -228.301709575
   E(CCSD(T))                                 ...   -228.321696508

   NORM  =      1.221657626 sqrt=     1.105286219
   W(HF) =      0.818559946
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="rhfTriplesCorr">
           <module cmlx:templateRef="rhfTriplesCorr">
              <scalar dataType="xsd:double" dictRef="o:tripCorr" units="nonsi:hartree">-0.019986933</scalar>
              <scalar dataType="xsd:double" dictRef="o:finCorrEner" units="nonsi:hartree">-0.685813096</scalar>
              <scalar dataType="xsd:double" dictRef="o:ccsdEner" units="nonsi:hartree">-228.301709575</scalar>
              <scalar dataType="xsd:double" dictRef="o:ccsdtEner" units="nonsi:hartree">-228.321696508</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Triples\sCorrection.*" endPattern="\s*" endPattern2="~">    <record>\s*Triples\sCorrection\s\(T\)\s*\.\.\.{F,o:tripCorr}</record>    <record repeat="*">\s.*(alpha|beta).*</record>    <record>\s*Final\scorrelation\senergy\s*\.\.\.{F,o:finCorrEner}</record>    <record>\s*E\(CCSD\)\s*\.\.\.{F,o:ccsdEner}</record>    <record>\s*E\(CCSD\(T\)\)\s*\.\.\.{F,o:ccsdtEner}</record>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
