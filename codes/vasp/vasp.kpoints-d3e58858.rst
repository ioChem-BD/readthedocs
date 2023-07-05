.. _vasp.kpoints-d3e58858:

vasp.kpoints
============

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
   | *source*                                                                                                                   | VASP KPOINTS                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | vasp.kpoints                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | VASP KPOINTS                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    Automatic generation mesh
    0
   Gamma
    3  3  1 
    0. 0. 0.
       

.. container:: formalpara-title

   **Input**

::

   Explicit k-point list
   4
   Cartesian
   0.0  0.0  0.0   1
   0.0  0.0  0.5   1
   0.0  0.5  0.5   2
   0.5  0.5  0.5   4    
       

.. container:: formalpara-title

   **Input**

::

   Automatic generation
   0
   Cartesian
   0.25 0.00 0.00
   0.00 0.25 0.00
   0.00 0.00 0.25
   0.00 0.00 0.00
        

.. container:: formalpara-title

   **Input**

::

   Line_mode KPOINTS file
   40
   Line_mode
   Reciprocal
   0.0 0.0 0.0 ! \Gamma
   0.5 0.0 0.5 ! X

   0.5 0.0 0.5 ! X
   0.5 0.25 0.75 ! W

   0.5 0.25 0.75 ! W
   0.375 0.375 0.75 ! K

   0.375 0.375 0.75 ! K
   0.0 0.0 0.0 ! \Gamma

   0.0 0.0 0.0 ! \Gamma
   0.5 0.5 0.5 ! L

   0.5 0.5 0.5 ! L
   0.625 0.25 0.625 ! U

   0.625 0.25 0.625 ! U
   0.5 0.25 0.75 ! W

   0.5 0.25 0.75 ! W
   0.5 0.5 0.5 ! L

   0.5 0.5 0.5 ! L
   0.375 0.375 0.75 ! K

   0.625 0.25 0.625 ! U
   0.5 0.0 0.5 ! X
         

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="vasp.kpoints">
           <module id="vasp.kpoints">
               <scalar dataType="xsd:string" dictRef="v:comment">Automatic generation mesh</scalar>
               <scalar dataType="xsd:integer" dictRef="v:kpointnum">0</scalar>
               <scalar dataType="xsd:string" dictRef="v:meshScheme">Gamma</scalar>
               <array dataType="xsd:integer" dictRef="v:subdivisionN" size="3">3 3 1</array>
               <array dataType="xsd:double" dictRef="v:shiftS" size="3">0. 0. 0.</array>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="vasp.kpoints2">
           <module id="vasp.kpoints">
               <scalar dataType="xsd:string" dictRef="v:comment">Explicit k-point list</scalar>
               <scalar dataType="xsd:integer" dictRef="v:kpointnum">4</scalar>
               <scalar dataType="xsd:string" dictRef="v:meshScheme">explicit</scalar>
               <scalar dataType="xsd:string" dictRef="v:coordtype">Cartesian</scalar>
               <array dataType="xsd:double" dictRef="v:kpointlist" size="12">0.0 0.0 0.0 0.0 0.0 0.5 0.0 0.5 0.5 0.5 0.5 0.5</array>
               <array dataType="xsd:integer" dictRef="v:weight" size="4">1 1 2 4</array>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="vasp.kpoints3">
           <module id="vasp.kpoints">
               <scalar dataType="xsd:string" dictRef="v:comment">Automatic generation</scalar>
               <scalar dataType="xsd:integer" dictRef="v:kpointnum">0</scalar>
               <scalar dataType="xsd:string" dictRef="v:meshScheme">automatic</scalar>
               <scalar dataType="xsd:string" dictRef="v:coordtype">Cartesian</scalar>
               <array dataType="xsd:double" dictRef="v:kpointlist" size="12">0.25 0.00 0.00 0.00 0.25 0.00 0.00 0.00 0.25 0.00 0.00 0.00</array>
           </module>
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="vasp.kpoints4">
           <module id="vasp.kpoints">
               <scalar dataType="xsd:string" dictRef="v:comment">Line_mode KPOINTS file</scalar>
               <scalar dataType="xsd:integer" dictRef="v:kpointnum">40</scalar>
               <scalar dataType="xsd:string" dictRef="v:meshScheme">Line_mode</scalar>
               <scalar dataType="xsd:string" dictRef="v:coordtype">Reciprocal</scalar>
               <array dataType="xsd:double" dictRef="v:kpointlist" size="60">0.0 0.0 0.0 0.5 0.0 0.5 0.5 0.0 0.5 0.5 0.25 0.75 0.5 0.25 0.75 0.375 0.375 0.75 0.375 0.375 0.75 0.0 0.0 0.0 0.0 0.0 0.0 0.5 0.5 0.5 0.5 0.5 0.5 0.625 0.25 0.625 0.625 0.25 0.625 0.5 0.25 0.75 0.5 0.25 0.75 0.5 0.5 0.5 0.5 0.5 0.5 0.375 0.375 0.75 0.625 0.25 0.625 0.5 0.0 0.5</array>
               <array dataType="xsd:string" dictRef="v:path" size="20">Γ X X W W K K Γ Γ L L U U W W L L K U X</array>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="gamma" pattern=".*$\s*\d+\s*$\s*(?i)(Gamma|Monkhorst[-\s]pack).*\s*" endPattern="~" endOffset="1">    <record>{X,v:comment}</record>    <record>{I,v:kpointnum}</record>    <record>{X,v:meshScheme}</record>    <record>{3I,v:subdivisionN}</record>    <record>{3F,v:shiftS}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list" />        
           </template>  <template id="automatic" pattern=".*$\s*\d+\s*$\s*(?i)(A).*" endPattern="~" endOffset="1">    <record>{X,v:comment}</record>    <record>{I,v:kpointnum}</record>    <record>{X,v:meshScheme}</record>    <record>{X,v:kpointlenght}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list" />        
           </template>  <template id="explicit" pattern=".*$\s*\d+\s*$\s*(?i)(C|K|Cartesian|Reciprocal|Fractional).*" endPattern="~" endOffset="1">    <record>{X,v:comment}</record>    <record>{I,v:kpointnum}</record>    <record>{X,v:coordtype}</record>    <record repeat="*" makeArray="true">{3F,v:kpointlist}</record>    <record repeat="*" makeArray="true">{3F,v:kpointlist}{I,v:weight}</record>    <transform process="addChild" xpath=".//cml:scalar[@dictRef='v:kpointnum' and text() = '0']/parent::cml:list" elementName="cml:scalar" dictRef="v:meshScheme" value="automatic" />    <transform process="addChild" xpath=".//cml:scalar[@dictRef='v:kpointnum' and text() != '0']/parent::cml:list" elementName="cml:scalar" dictRef="v:meshScheme" value="explicit" />    <transform process="addAttribute" xpath=".//cml:scalar[@dictRef='v:meshScheme']" name="dataType" value="xsd:string" />    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list" />       
           </template>  <template id="linemode" pattern=".*$\s*\d+\s*$\s*(?i)(L).*" endPattern="~" endOffset="1">    <record>{X,v:comment}</record>    <record>{I,v:kpointnum}</record>    <record>{X,v:meshScheme}</record>    <record>{X,v:coordtype}</record>    <template id="line" pattern="\s*\S.*" endPattern="\s*" endPattern2="~" repeat="*">      <record repeat="*">{3F,v:kpointlist}!?{X,v:path}</record>      <transform process="setValue" xpath=".//cml:scalar[@dictRef='v:path' and text() = '\Gamma']" value="Γ" />               
               </template>    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='v:kpointlist']" />    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='v:path']" dataType="xsd:string" dictRef="v:path" />    <transform process="pullup" xpath=".//cml:module//cml:array" repeat="3" />    <transform process="delete" xpath=".//cml:module" />    <transform process="pullup" xpath="//cml:module/cml:list/cml:scalar" />    <transform process="delete" xpath=".//cml:list" />
           </template>
       
       </templateList>
   <transform process="pullup" xpath=".//cml:module/*" />
   <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
