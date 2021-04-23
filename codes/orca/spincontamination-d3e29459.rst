.. _spincontamination-d3e29459:

spincontamination
=================

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
   | id                                | spincontamination                 |
   +-----------------------------------+-----------------------------------+
   | name                              | UHF Spin contamination            |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-{10,}\s                      |
   |                                   | *$\s*UHF\sSPIN\sCONTAMINATION\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*-{10,}$\s*\w                  |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s+\*{20,}.\*                    |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/scf/spincontamination.xml     |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ----------------------
   UHF SPIN CONTAMINATION
   ----------------------

   Warning: in a DFT calculation there is little theoretical justification to 
            calculate <S**2> as in Hartree-Fock theory. We will do it anyways
            but you should keep in mind that the values have only limited relevance

   Expectation value of <S**2>     :     2.002400
   Ideal value S*(S+1) for S=1.0   :     2.000000
   Deviation                       :     0.002400

   ----------------        
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="spincontamination">
           <module cmlx:templateRef="spincontamination" dictRef="cc:userDefinedModule">
              <scalar dataType="xsd:double" dictRef="cc:s2">2.002400</scalar>
              <scalar dataType="xsd:double" dictRef="cc:sideal">1.0</scalar>
              <scalar dataType="xsd:double" dictRef="cc:s2ideal">2.000000</scalar>
              <scalar dataType="xsd:double" dictRef="cc:s2deviation">0.002400</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="s2" pattern="\s*Expectation.*" endPattern="\s*Deviation.*" endPattern2="~" endOffset="1">    <record>\s*Expectation\svalue\sof\s\WS\*\*2\W.*\s*:{F,cc:s2}</record>    <record>\s*Ideal\svalue\sS\*\(S\+1\)\sfor\sS={F,cc:sideal}:{F,cc:s2ideal}</record>    <record>\s*Deviation\s*:{F,cc:s2deviation}</record>
           </template>
       </templateList>
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
