.. _control-d3e6953:

control
=======

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
   | *source*                                                                                                                   | Amber log                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | control                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Control data                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{20,}.*$&#92;s*2&#92;.&#92;s+CONTROL&#92;s+DATA&#92;s+FOR&#92;s+THE&#92;s+RUN.\*                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*-{20,}.                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/control.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   --------------------------------------------------------------------------------
      2.  CONTROL  DATA  FOR  THE  RUN
   --------------------------------------------------------------------------------

   default_name                                                                    

   General flags:
        imin    =       0, nmropt  =       0

   Nature and format of input:
        ntx     =       5, irest   =       1, ntrx    =       1

   Nature and format of output:
        ntxo    =       2, ntpr    =  100000, ntrx    =       1, ntwr    =50000000
        iwrap   =       0, ntwx    =  100000, ntwv    =       0, ntwe    =       0
        ioutfm  =       1, ntwprt  =       0, idecomp =       0, rbornstat=      0

   Potential function:
        ntf     =       2, ntb     =       2, igb     =       0, nsnb    =      25
        ipol    =       0, gbsa    =       0, iesp    =       0
        dielc   =   1.00000, cut     =  10.00000, intdiel =   1.00000

   Frozen or restrained atoms:
        ibelly  =       0, ntr     =       0

   Molecular dynamics:
        nstlim  =  50000000, nscm    =      1000, nrespa  =         1
        t       =   0.00000, dt      =   0.00200, vlimit  =  -1.00000

   Langevin dynamics temperature regulation:
        ig      =  847044
        temp0   = 300.00000, tempi   =   0.00000, gamma_ln=   2.00000

   Pressure regulation:
        ntp     =       1
        pres0   =   1.00000, comp    =  44.60000, taup    =   1.00000
        Monte-Carlo Barostat:
        mcbarint  =     100

   SHAKE:
        ntc     =       2, jfastw  =       0
        tol     =   0.00001

   | Intermolecular bonds treatment:
   |     no_intermolecular_bonds =       1

   | Energy averages sample interval:
   |     ene_avg_sampling =  100000

   Ewald parameters:
        verbose =       0, ew_type =       0, nbflag  =       1, use_pme =       1
        vdwmeth =       1, eedmeth =       1, netfrc  =       1
        Box X =   46.578   Box Y =   46.578   Box Z =   46.578
        Alpha =  109.471   Beta  =  109.471   Gamma =  109.471
        NFFT1 =   48       NFFT2 =   48       NFFT3 =   48
        Cutoff=   10.000   Tol   =0.100E-04
        Ewald Coefficient =  0.27511
        Interpolation order =    4
   | MONTE CARLO BAROSTAT IMPORTANT NOTE:
   |   The Monte-Carlo barostat does not require the virial to adjust the system volume.
   |   Since it is an expensive calculation, it is skipped for efficiency. A side-effect
   |   is that the reported pressure is always 0 because it is not calculated.

   --------------------------------------------------------------------------------
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="">
         <module cmlx:templateRef="control">
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">General flags</scalar>
               <scalar dataType="xsd:string" dictRef="am:imin">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:nmropt">0</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Nature and format of input</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntx">5</scalar>
               <scalar dataType="xsd:string" dictRef="am:irest">1</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntrx">1</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Nature and format of output</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntxo">2</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntpr">100000</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntrx">1</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntwr">50000000</scalar>
               <scalar dataType="xsd:string" dictRef="am:iwrap">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntwx">100000</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntwv">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntwe">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:ioutfm">1</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntwprt">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:idecomp">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:rbornstat">0</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Potential function</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntf">2</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntb">2</scalar>
               <scalar dataType="xsd:string" dictRef="am:igb">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:nsnb">25</scalar>
               <scalar dataType="xsd:string" dictRef="am:ipol">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:gbsa">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:iesp">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:dielc">1.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:cut">10.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:intdiel">1.00000</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Frozen or restrained atoms</scalar>
               <scalar dataType="xsd:string" dictRef="am:ibelly">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntr">0</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Molecular dynamics</scalar>
               <scalar dataType="xsd:string" dictRef="am:nstlim">50000000</scalar>
               <scalar dataType="xsd:string" dictRef="am:nscm">1000</scalar>
               <scalar dataType="xsd:string" dictRef="am:nrespa">1</scalar>
               <scalar dataType="xsd:string" dictRef="am:t">0.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:dt">0.00200</scalar>
               <scalar dataType="xsd:string" dictRef="am:vlimit">-1.00000</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Langevin dynamics temperature regulation</scalar>
               <scalar dataType="xsd:string" dictRef="am:temp0">300.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:tempi">0.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:gamma.ln">2.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:ig">847044</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">Pressure regulation</scalar>
               <scalar dataType="xsd:string" dictRef="am:pres0">1.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:comp">44.60000</scalar>
               <scalar dataType="xsd:string" dictRef="am:taup">1.00000</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntp">1</scalar>
               <scalar dataType="xsd:string" dictRef="am:mcbarint">100</scalar>
            </list>
            <list cmlx:templateRef="section">
               <scalar dataType="xsd:string" dictRef="am:section.name">SHAKE</scalar>
               <scalar dataType="xsd:string" dictRef="am:ntc">2</scalar>
               <scalar dataType="xsd:string" dictRef="am:jfastw">0</scalar>
               <scalar dataType="xsd:string" dictRef="am:tol">0.00001</scalar>
            </list>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="section" pattern="\s*[a-zA-Z0-9](?!wald\sparameters).*:" endPattern="\s*" endPattern2="~" endOffset="0" repeat="*">    <record id="section">{X,am:section.name}:</record>    <templateList>      <template id="section" pattern=".+,.+,.+,.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">        <record>{X,am:name}={A,am:value},{X,am:name}={A,am:value},{X,am:name}={A,am:value},{X,am:name}={A,am:value}</record>        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
                   </template>      <template id="section" pattern=".+,.+,.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">        <record>{X,am:name}={A,am:value},{X,am:name}={A,am:value},{X,am:name}={A,am:value}</record>        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
                   </template>      <template id="section" pattern=".+,.+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">        <record>{X,am:name}={A,am:value},{X,am:name}={A,am:value}</record>        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="pullup" xpath=".//cml:scalar" repeat="3" />                                         
                   </template>      <template id="section" pattern=".+" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">        <record>{X,am:name}={A,am:value}</record>        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(lower-case(./text()))" />        <transform process="setValue" xpath=".//cml:scalar[@dictRef='am:name']" value="$string(replace(./text(), '[-_ ]', '.'))" />        <transform process="createNameValue" xpath="./cml:list/cml:list" name="./cml:scalar[@dictRef='am:name'][position() = 1]" value="./cml:scalar[@dictRef='am:value'][position()= 1]" />        <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
                   </template>               
               </templateList>    <transform process="moveRelative" xpath="./cml:scalar" to="parent::cml:module/cml:list" />    <transform process="delete" xpath="./cml:module" />    <transform process="pullup" xpath="./cml:list" />   
           </template>
       </templateList>
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
