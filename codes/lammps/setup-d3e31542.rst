.. _setup-d3e31542:

setup
=====

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
   | *source*                                                                                                                   | LAMMPS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | setup                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*units&#92;s+&#92;S+.\*                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Neighbor&#92;slist&#92;sinfo.\*                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s*Reading&#92;srestart&#92;sfile.\*                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/setup.xml                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   units         metal
   boundary      p p p
   atom_style    atomic
   pair_style    eam
   read_data     .lammps.dat
     orthogonal box = (-0.0167608 -0.0167608 -0.0167608) to (18.1231 18.1231 18.1231)
     3 by 3 by 4 MPI processor grid
     reading atoms ...
     500 atoms
     reading velocities ...
     500 velocities
     read_data CPU = 0.00427604 secs
   pair_coeff    * * Cu_u3.eam
   Reading potential file Cu_u3.eam with DATE: 2007-06-11
   dump          Dump all custom 1000 tmpdir/lammps.dmp.* id type x y z ix iy iz vx vy vz
   thermo_style  custom step time cpu pe ke etotal enthalpy temp press vol density cella cellb cellc cellalpha cellbeta cellgamma
   thermo        100
   fix           ensemble1 all nve
   timestep      5.0e-4
   run           200000
   Neighbor list info ...
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="setup">
          <module cmlx:templateRef="setup">
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">units</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">metal</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">boundary</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">p p p</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">atom_style</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">atomic</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">pair_style</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">eam</scalar>
            </parameter>
            <parameter>
               <list cmlx:templateRef="datafile">
                  <scalar dataType="xsd:string" dictRef="l:line">read_data     .lammps.dat</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">orthogonal box = (-0.0167608 -0.0167608 -0.0167608) to (18.1231 18.1231 18.1231)</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">3 by 3 by 4 MPI processor grid</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">reading atoms ...</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">500 atoms</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">reading velocities ...</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">500 velocities</scalar>
                  <scalar dataType="xsd:string" dictRef="l:line">read_data CPU = 0.00427604 secs</scalar>
               </list>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">pair_coeff</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">* * Cu_u3.eam</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">dump</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">Dump all custom 1000 tmpdir/lammps.dmp.* id type x y z ix iy iz vx vy vz</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">thermo_style</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">custom step time cpu pe ke etotal enthalpy temp press vol density cella cellb cellc cellalpha cellbeta cellgamma</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">thermo</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">100</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">fix</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">ensemble1 all nve</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">timestep</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">5.0e-4</scalar>
            </parameter>
            <parameter>
               <scalar dataType="xsd:string" dictRef="x:label">run</scalar>
               <scalar dataType="xsd:string" dictRef="x:value">200000</scalar>
            </parameter>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="datafile" pattern="read_data\s+\S.*$Reading\sdata.*" pattern2="read_data\s+\S.*$\s\s.*" endPattern="\s+\S+.*$\S+.*" endPattern2="\s+\S+.*$\s*" endOffset="1">    <record id="datafile" repeat="*">{X,l:line}</record>    <transform process="addChild" xpath="." elementName="cml:parameter" />    <transform process="move" xpath=".//cml:list" to=".//cml:parameter" />
           </template>  <template id="parameter" pattern="((?!#|WARNING|Reading\spotential\sfile).*)" endPattern=".*" endPattern2="~" repeat="*">    <record id="parameter">{A,x:label}{X,x:value}</record>    <transform process="addChild" xpath="." elementName="cml:parameter" />    <transform process="move" xpath=".//cml:scalar" to=".//cml:parameter" />
           </template>
       </templateList>
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="x:label" value="units" />
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="x:value" value="lj" />
   <transform process="addAttribute" xpath="./cml:scalar" name="dataType" value="xsd:string" />
   <transform process="addChild" xpath="." elementName="cml:parameter" />
   <transform process="move" xpath="./cml:scalar" to="./cml:parameter[count(*)=0]" />
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="x:label" value="atom_style" />
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="x:value" value="atomic" />
   <transform process="addAttribute" xpath="./cml:scalar" name="dataType" value="xsd:string" />
   <transform process="addChild" xpath="." elementName="cml:parameter" />
   <transform process="move" xpath="./cml:scalar" to="./cml:parameter[count(*)=0]" />
   <transform process="pullup" xpath="./cml:module/cml:parameter" />
   <transform process="delete" xpath=".//cml:module" />
   <transform process="delete" xpath="//cml:parameter[child::cml:scalar[@dictRef='x:label' and text()='units']][position() >1]" />
   <transform process="delete" xpath="//cml:parameter[child::cml:scalar[@dictRef='x:label' and text()='atom_style']][position() >1]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
