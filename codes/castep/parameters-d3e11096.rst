.. _parameters-d3e11096:

parameters
==========

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
   | *source*                                                                                                                   | CASTEP log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | parameters                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | CASTEP parameter section                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;*{10,}&#92;s*Title.\*                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*&#92;*{10,}&#92;s*General&#92;sParameters.\*                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;*{60,}&#92;s\*                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | parameters/parameters.xml                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    ************************************ Title ************************************
    CASTEP calculation from Materials Studio

    ***************************** General Parameters ******************************
     
    output verbosity                               : normal  (1)
    write checkpoint data to                       : Si_51688.check
    type of calculation                            : geometry optimization
    stress calculation                             : on
    density difference calculation                 : off
    electron localisation func (ELF) calculation   : off
    Hirshfeld analysis                             : on
    polarisation (Berry phase) analysis            : off
    molecular orbital projected DOS                : off
    deltaSCF calculation                           : off
    unlimited duration calculation
    timing information                             : on
    memory usage estimate                          : on
    write extra output files                       : on
    write final potential to formatted file        : off
    write final density to formatted file          : off
    write BibTeX reference list                    : on
    write OTFG pseudopotential files               : on
    write electrostatic potential file             : on
    write bands file                               : on
    checkpoint writing                             : both castep_bin and check files
     
    output         length unit                     : A
    output           mass unit                     : amu
    output           time unit                     : ps
    output         charge unit                     : e
    output           spin unit                     : hbar/2
    output         energy unit                     : eV
    output          force unit                     : eV/A
    output       velocity unit                     : A/ps
    output       pressure unit                     : GPa
    output     inv_length unit                     : 1/A
    output      frequency unit                     : cm-1
    output force constant unit                     : eV/A**2
    output         volume unit                     : A**3
    output   IR intensity unit                     : (D/A)**2/amu
    output         dipole unit                     : D
    output         efield unit                     : eV/A/e
    output        entropy unit                     : J/mol/K
    output    efield chi2 unit                     : pm/V
     
    wavefunctions paging                           : none
    random number generator seed                   : randomised (203424294)
    data distribution                              : optimal for this architecture
    optimization strategy                          : balance speed and memory

    *********************** Exchange-Correlation Parameters ***********************
     
    using functional                               : Perdew Burke Ernzerhof
    relativistic treatment                         : Koelling-Harmon
    DFT+D: Semi-empirical dispersion correction    : off

    ...

    *******************************************************************************        
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="parameters">
           <module cmlx:templateRef="parameters">      
            <scalar dataType="xsd:string" dictRef="cc:title">CASTEP calculation from Materials Studio</scalar>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">output verbosity</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">normal (1)</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">continuing from</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Si_51688_BandStr.check</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write checkpoint data to</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Si_51688_BandStr.check</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">type of calculation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Electronic Spectroscopy</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">stress calculation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">density difference calculation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">electron localisation func (ELF) calculation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">Hirshfeld analysis</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">polarisation (Berry phase) analysis</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">molecular orbital projected DOS</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">deltaSCF calculation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">timing information</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">memory usage estimate</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write extra output files</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write final potential to formatted file</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write final density to formatted file</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write BibTeX reference list</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write OTFG pseudopotential files</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write electrostatic potential file</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">write bands file</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">on</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">checkpoint writing</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">both castep_bin and check files</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">wavefunctions paging</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">none</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">random number generator seed</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">203424294</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">data distribution</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">optimal for this architecture</scalar>
            </parameter>
            <parameter title="general">
               <scalar dataType="xsd:string" dictRef="x:label">optimization strategy</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">balance speed and memory</scalar>
            </parameter>
            <parameter title="exchange.correlation">
               <scalar dataType="xsd:string" dictRef="x:label">using functional</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Perdew Burke Ernzerhof</scalar>
            </parameter>
            <parameter title="exchange.correlation">
               <scalar dataType="xsd:string" dictRef="x:label">relativistic treatment</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Koelling-Harmon</scalar>
            </parameter>
            <parameter title="exchange.correlation">
               <scalar dataType="xsd:string" dictRef="x:label">DFT+D: Semi-empirical dispersion correction</scalar>
               <scalar dataType="xsd:string" dictRef="x:value"> off</scalar>
            </parameter>
            <parameter title="pseudopotential">
               <scalar dataType="xsd:string" dictRef="x:label">pseudopotential representation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">reciprocal space</scalar>
            </parameter>
            <parameter title="pseudopotential">
               <scalar dataType="xsd:string" dictRef="x:label"><beta|phi> representation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">reciprocal space</scalar>
            </parameter>
            <parameter title="pseudopotential">
               <scalar dataType="xsd:string" dictRef="x:label">spin-orbit coupling</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">plane wave basis set cut-off</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">136.1000</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">size of standard grid</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">2.0000</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">size of fine gmax</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:reciprocalAngstrom">11.9536</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">largest prime factor in FFT</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">5</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">finite basis set correction</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">automatic</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">number of sample energies</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">3</scalar>
            </parameter>
            <parameter title="basis.set">
               <scalar dataType="xsd:string" dictRef="x:label">sample spacing</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">5.0000</scalar>
            </parameter>
            <parameter title="electronic">
               <scalar dataType="xsd:string" dictRef="x:label">number of electrons</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">32.00</scalar>
            </parameter>
            <parameter title="electronic">
               <scalar dataType="xsd:string" dictRef="x:label">net charge of system</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">0.000</scalar>
            </parameter>
            <parameter title="electronic">
               <scalar dataType="xsd:string" dictRef="x:label">net spin of system</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">0.000</scalar>
            </parameter>
            <parameter title="electronic">
               <scalar dataType="xsd:string" dictRef="x:label">number of up spins</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">16.00</scalar>
            </parameter>
            <parameter title="electronic">
               <scalar dataType="xsd:string" dictRef="x:label">number of down spins</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">16.00</scalar>
            </parameter>
            <parameter title="electronic">
               <scalar dataType="xsd:string" dictRef="x:label">number of bands</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">26</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">Method</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Treating system as metallic with density mixing treatment of electrons,</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">and number of SD steps</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">1</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">and number of CG steps</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">4</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">total energy / atom convergence tol.</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">0.5000E-06</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">eigen-energy convergence tolerance</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">0.1538E-06</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">max force / atom convergence tol.</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">ignored</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">convergence tolerance window</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi2:cycle">3</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">max. number of SCF cycles</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">100</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">number of fixed-spin iterations</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">6</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">smearing scheme</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Gaussian</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">smearing width</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">0.1000</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">Fermi energy convergence tolerance</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">0.2721E-13</scalar>
            </parameter>
            <parameter title="electronic.minimization">
               <scalar dataType="xsd:string" dictRef="x:label">periodic dipole correction</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">NONE</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">density-mixing scheme</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Pulay</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">max. length of mixing history</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">10</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">charge density mixing amplitude</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">0.1000</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">spin density mixing amplitude</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">0.1000</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">cut-off energy for mixing</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">136.1</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">charge density mixing g-vector</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:reciprocalAngstrom">0.2000</scalar>
            </parameter>
            <parameter title="density.mixing">
               <scalar dataType="xsd:string" dictRef="x:label">spin density mixing g-vector</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:reciprocalAngstrom">0.2000</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">electronic spectroscopy with theory level</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">DFT</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">spectroscopy calculation</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">band structure</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">max. number of iterations</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">60</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">max. steps per iteration</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">5</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">number of bands / k-point</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">43</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">band convergence tolerance</scalar>
               <scalar dataType="xsd:string" dictRef="x:value" units="nonsi:electronvolt">0.1000E-04</scalar>
            </parameter>
            <parameter title="electronic.spectroscopy">
               <scalar dataType="xsd:string" dictRef="x:label">write orbitals file</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">off</scalar>
            </parameter>
            <map id="output.units">
               <link from="length" to="A" />
               <link from="mass" to="amu" />
               <link from="time" to="ps" />
               <link from="charge" to="e" />
               <link from="spin" to="hbar/2" />
               <link from="energy" to="eV" />
               <link from="force" to="eV/A" />
               <link from="velocity" to="A/ps" />
               <link from="pressure" to="GPa" />
               <link from="inv_length" to="1/A" />
               <link from="frequency" to="cm-1" />
               <link from="force constant" to="eV/A**2" />
               <link from="volume" to="A**3" />
               <link from="IR intensity" to="(D/A)**2/amu" />
               <link from="dipole" to="D" />
               <link from="efield" to="eV/A/e" />
               <link from="entropy" to="J/mol/K" />
               <link from="efield chi2" to="pm/V" />
            </map>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="title" pattern="\s*\*{10,}\s*Title.*" endPattern="\s*" endPattern2="\s*\*{10,}.*" endOffset="0">    <record />    <record>{X, cc:title}</record>    <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:title']" repeat="2" />
           </template>  <template id="general" pattern="\s*\*{10,}\s*\w+.*" endPattern="\s*$\s*\*{10,}.*" endPattern2="~" endOffset="0" repeat="*">    <record>\s*\*{10,}\s*{X,ca:parameter.type}\sParameters.*</record>    <record repeat="1" />    <templateList>      <template id="parameters" pattern="\s*((?!output.+\s+unit).)*:\s+\w+((?!\s\s\s\S+).)*" endPattern=".*" endPattern2="~" repeat="*">        <record id="parameter" name="parameter" repeat="*">{X,x:label}\s*:{X, x:value}</record>        <transform process="addChild" xpath=".//cml:list[cml:scalar]" elementName="cml:parameter" />        <transform process="moveRelative" xpath=".//cml:scalar" to="following-sibling::cml:parameter" />        <transform process="move" xpath=".//cml:parameter" to="." />        <transform process="delete" xpath=".//cml:list" />
                   </template>      <template id="parameters" pattern="\s*((?!output.+\s+unit).)*:\s+\w+.*\s\s\s\S+.*" endPattern=".*" endPattern2="~" repeat="*">        <record id="parameter" name="parameter">{X,x:label}\s*:{X, x:value}{A,ca:units}</record>        <transform process="addChild" xpath=".//cml:list[cml:scalar]" elementName="cml:parameter" />        <transform process="moveRelative" xpath=".//cml:scalar" to="following-sibling::cml:parameter" />        <transform process="move" xpath=".//cml:parameter" to="." />        <transform process="delete" xpath=".//cml:list" />
                   </template>      <template id="units" pattern="\s*output.*unit.*" endPattern="\s*" endPattern2="~" repeat="*">        <record repeat="*">\s*output{X,x:label}unit\s*:{X,x:value}</record>               
                   </template>      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'eV']]" value="nonsi:electronvolt" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = '1/A']]" value="nonsi:reciprocalAngstrom" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'amu']]" value="nonsi2:amu" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'A']]" value="nonsi:angstrom" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'ps']]" value="nonsi:picoseconds" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'e']]" value="nonsi:elementaryCharge" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'eV/atom']]" value="nonsi2:electronvolt.atom-1" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'hbar/2']]" value="nonsi2:hbar.2-1" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'eV/A']]" value="nonsi2:ev.angstrom-1" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'A/ps']]" value="nonsi2:angstrom.picoseconds-1" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'GPa']]" value="nonsi2:gigapascal" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'cm-1']]" value="nonsi:cm-1" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'eV/A**2']]" value="nonsi2:electronvolt.angstrom-2" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'A**3']]" value="nonsi:angstrom3" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = '(D/A)**2/amu']]" value="nonsi2:debye.angstrom-1.2.amu" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'D']]" value="nonsi:debye" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'cycles']]" value="nonsi2:cycle" />      <transform process="addUnits" xpath="//cml:scalar[@dictRef='x:value' and following-sibling::cml:scalar[@dictRef='ca:units' and text() = 'steps']]" value="nonsi2:step" />            
               </templateList>    <transform process="setValue" xpath=".//cml:scalar[@dictRef='ca:parameter.type']" value="$string(replace(lower-case(./text()), '\W+','.'))" />    <transform process="addAttribute" xpath=".//cml:parameter" name="title" value="$string(../../cml:list/cml:scalar[@dictRef='ca:parameter.type']/text())" />
           </template>
       </templateList>
   <transform process="setValue" xpath="//cml:parameter//cml:scalar[starts-with(text(),'Semi-empirical dispersion correction')]/preceding-sibling::cml:scalar" value="$string(concat(., ': Semi-empirical dispersion correction'))" />
   <transform process="setValue" xpath="//cml:parameter//cml:scalar[@dictRef='x:value' and starts-with(text(),'Semi-empirical dispersion correction')]" value="$string(substring-after(./text(), ':'))" />
   <transform process="delete" xpath=".//cml:parameter/cml:scalar[@dictRef='ca:units']" />
   <transform process="addMap" xpath="." id="output.units" from=".//cml:module[@cmlx:templateRef='units']//cml:scalar[@dictRef='x:label']" to=".//cml:module[@cmlx:templateRef='units']//cml:scalar[@dictRef='x:value']" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='units']" />
   <transform process="move" xpath=".//cml:module[@cmlx:templateRef='parameters']//cml:parameter" to="(.//cml:module[@cmlx:templateRef='parameters'])[1]" />
   <transform process="pullup" xpath=".//cml:module[@cmlx:templateRef='parameters']/cml:parameter" repeat="2" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='title']" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
