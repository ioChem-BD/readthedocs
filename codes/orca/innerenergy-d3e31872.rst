.. _innerenergy-d3e31872:

innerenergy
===========

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
   | id                                                                                                                         | innerenergy                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Inner energy                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{10,}$&#92;s*INNER&#92;sENERGY                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Total&#92;scorrection.\*                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | keep                                                                                                                       | last                                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/innerenergy.xml                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   ------------
   INNER ENERGY
   ------------

   The inner energy is: U= E(el) + E(ZPE) + E(vib) + E(rot) + E(trans)
       E(el)   - is the total energy from the electronic structure calculation
                 = E(kin-el) + E(nuc-el) + E(el-el) + E(nuc-nuc)
       E(ZPE)  - the the zero temperature vibrational energy from the frequency calculation
       E(vib)  - the the finite temperature correction to E(ZPE) due to population
                 of excietd vibrational states
       E(rot)  - is the rotational thermal energy
       E(trans)- is the translational thermal energy

   Summary of contributions to the inner energy U:
   Electronic energy                ...   -228.92495871 Eh
   Zero point energy                ...      0.05984322 Eh      37.55 kcal/mol
   Thermal vibrational correction   ...      0.00180167 Eh       1.13 kcal/mol
   Thermal rotational correction    ...      0.00141627 Eh       0.89 kcal/mol
   Thermal translational correction ...      0.00141627 Eh       0.89 kcal/mol
   -----------------------------------------------------------------------
   Total thermal energy                   -228.86048127 Eh


   Summary of corrections to the electronic energy:
   (perhaps to be used in another calculation)
   Total thermal correction                  0.00463421 Eh       2.91 kcal/mol
   Non-thermal (ZPE) correction              0.05984322 Eh      37.55 kcal/mol
   -----------------------------------------------------------------------
   Total correction                          0.06447743 Eh      40.46 kcal/mol


   --------    
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="innerenergy">
           <module cmlx:templateRef="innerenergy">
               <module cmlx:templateRef="contributions">
                  <scalar dataType="xsd:double" dictRef="o:electronic" units="nonsi:hartree">-228.92495871</scalar>
                  <scalar dataType="xsd:double" dictRef="o:zeropoint" units="nonsi:hartree">0.05984322</scalar>
                  <scalar dataType="xsd:double" dictRef="o:thermalvibcorrection" units="nonsi:hartree">0.00180167</scalar>
                  <scalar dataType="xsd:double" dictRef="o:thermalrotcorrection" units="nonsi:hartree">0.00141627</scalar>
                  <scalar dataType="xsd:double" dictRef="o:thermaltrasncorrection" units="nonsi:hartree">0.00141627</scalar>
                  <scalar dataType="xsd:double" dictRef="o:thermaltotal" units="nonsi:hartree">-228.86048127</scalar>
               </module>
               <module cmlx:templateRef="corrections">
                  <scalar dataType="xsd:double" dictRef="o:thermalcorr" units="nonsi:hartree">0.00463421</scalar>
                  <scalar dataType="xsd:double" dictRef="o:nonthermalcorr" units="nonsi:hartree">0.05984322</scalar>
                  <scalar dataType="xsd:double" dictRef="o:totalcorr" units="nonsi:hartree">0.06447743</scalar>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="contributions" pattern="\s*Summary\sof\scontributions\sto\sthe\sinner\senergy\sU.*" endPattern="\s*Total\sthermal\senergy.*" endOffset="1">    <record />    <record>\s*Electronic\senergy\s*\.\.\.{F,o:electronic}.*</record>    <record>\s*Zero\spoint\senergy\s*\.\.\.{F,o:zeropoint}.*</record>    <record>\s*Thermal\svibrational\scorrection\s*\.\.\.{F,o:thermalvibcorrection}.*</record>    <record>\s*Thermal\srotational\scorrection\s*\.\.\.{F,o:thermalrotcorrection}.*</record>    <record>\s*Thermal\stranslational\scorrection\s*\.\.\.{F,o:thermaltrasncorrection}.*</record>    <record />    <record>\s*Total\sthermal\senergy\s*{F,o:thermaltotal}.*</record>    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="delete" xpath=".//cml:list" />
           </template>  <template id="corrections" pattern="\s*Summary\sof\scorrections\sto\sthe\selectronic\senergy.*" endPattern="\s*Total\scorrection.*" endOffset="1">    <record repeat="2" />    <record>\s*Total\sthermal\scorrection{F,o:thermalcorr}.*</record>    <record>\s*Non-thermal\s\(ZPE\)\scorrection{F,o:nonthermalcorr}.*</record>    <record />    <record>\s*Total\scorrection{F,o:totalcorr}.*</record>    <transform process="addUnits" xpath=".//cml:scalar" value="nonsi:hartree" />    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="delete" xpath=".//cml:list" />
           </template>           
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
