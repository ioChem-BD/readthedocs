.. _rhfTriplesCorr-d3e39893:

rhfTriplesCorr
==============

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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | rhfTriplesCorr                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{15,}$&#92;s*RHF&#92;sTRIPLES&#92;sCORRECTION.\*                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*W&#92;(HF&#92;)                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | ci/rhftriplescorr.xml                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

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
       

.. container:: formalpara-title

   **Input**

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

   Triples Correction (T)                     ...     -0.019986943
   Scaling of triples based on CCSD energies (Peterson et al. Molecular Physics 113, 1551 (2015))
   E(T*) = f*E(T) where f = E(F12-CCSD)/E(CCSD)
   f = CCSD (with F12)/ CCSD (without F12)    ...      1.000000000
   Scaled triples correction (T)              ...     -0.019986943

   Final correlation energy                   ...     -0.685813085
   E(CCSD)                                    ...   -228.301709553
   E(CCSD(T))                                 ...   -228.321696496

   NORM  =      1.221657394 sqrt=     1.105286114
   W(HF) =      0.818560101
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="rhfTriplesCorr">
           <module cmlx:templateRef="rhfTriplesCorr">
              <scalar dataType="xsd:double" dictRef="o:tripCorr" units="nonsi:hartree">-0.019986933</scalar>
              <scalar dataType="xsd:double" dictRef="o:finCorrEner" units="nonsi:hartree">-0.685813096</scalar>
              <scalar dataType="xsd:double" dictRef="o:ccsdEner" units="nonsi:hartree">-228.301709575</scalar>
              <scalar dataType="xsd:double" dictRef="o:ccsdtEner" units="nonsi:hartree">-228.321696508</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="rhfTriplesCorr2">
           <module cmlx:templateRef="rhfTriplesCorr">
               <scalar dataType="xsd:double" dictRef="o:tripCorr" units="nonsi:hartree">-0.019986943</scalar>
               <scalar dataType="xsd:double" dictRef="o:finCorrEner" units="nonsi:hartree">-0.685813085</scalar>
               <scalar dataType="xsd:double" dictRef="o:ccsdEner" units="nonsi:hartree">-228.301709553</scalar>
               <scalar dataType="xsd:double" dictRef="o:ccsdtEner" units="nonsi:hartree">-228.321696496</scalar>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template pattern="\s*Triples\sCorrection.*" endPattern="(?!Scaled).*$\s*" endPattern2="~" endOffset="1">    <record>\s*Triples\sCorrection\s\(T\)\s*\.\.\.{F,o:tripCorr}</record>    <record repeat="*">(?!Final).*</record>    <record repeat="*">\s.*(alpha|beta).*</record>    <record>\s*Final\scorrelation\senergy\s*\.\.\.{F,o:finCorrEner}</record>    <record>\s*E\(CCSD\)\s*\.\.\.{F,o:ccsdEner}</record>    <record>\s*E\(CCSD\(T\)\)\s*\.\.\.{F,o:ccsdtEner}</record>
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />
   <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
