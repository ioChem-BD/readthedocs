adf.runtype
-------------------------------------- 

.. toctree::
   :maxdepth: 5    
      
   /codes/adf/geometry-d3e1819
   /codes/adf/symmetry-d3e2154

===========

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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | adf.runtype                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s                               |
   |                                   | +\*\s+R\sU\sN\s+T\sY\sP\sE\s\:.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\*{80,}.\*                    |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 2                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | adf/runtype/runtype.xml           |
   +-----------------------------------+-----------------------------------+

**Input.**

::

                          ************************************
                          *  R U N   T Y P E : SINGLE POINT  *
                          ************************************

    ===============
    G E O M E T R Y  ***  Planar Molecule  ***
    ===============
     

    ATOMS
    =====                            X Y Z                    CHARGE
                                   (Angstrom)             Nucl     +Core       At.Mass
                          --------------------------    ----------------       -------
       1  O               0.0000    0.0000    0.0000      8.00      6.00       15.9949
       2  H               0.0000   -0.6894   -0.5785      1.00      1.00        1.0078
       3  H               0.0000    0.6894   -0.5785      1.00      1.00        1.0078
   ...

   =====================================
    S Y M M E T R Y ,   E L E C T R O N S
    =====================================
    ...


    ***************************************************************************************************    
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="adf.runType">
         <module cmlx:lineCount="241" cmlx:templateRef="adf.runtype">       
          <scalar dataType="xsd:string" dictRef="cc:runtype">SINGLE POINT</scalar>
            <module cmlx:lineCount="12" cmlx:templateRef="geometry">
             <molecule id="a25">
               <atomArray>
                 <atom id="a1" elementType="O" x3="0.0" y3="0.0" z3="0.0">
                   <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
                   <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">8</scalar>
                 </atom>
                 <atom id="a2" elementType="H" x3="0.0" y3="-0.6894" z3="-0.5785">
                   <scalar dataType="xsd:integer" dictRef="cc:serial">2</scalar>
                   <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                 </atom>
                 <atom id="a3" elementType="H" x3="0.0" y3="0.6894" z3="-0.5785">
                   <scalar dataType="xsd:integer" dictRef="cc:serial">3</scalar>
                   <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
                 </atom>
               </atomArray>
               <formula formalCharge="0" concise="H 2 O 1">
                 <atomArray elementType="H O" count="2.0 1.0" />
               </formula>
               <bondArray>
                 <bond atomRefs2="a1 a2" id="a1_a2" order="S" />
                 <bond atomRefs2="a1 a3" id="a1_a3" order="S" />
               </bondArray>
               <property dictRef="cml:molmass">
                 <scalar dataType="xsd:double" units="unit:dalton">18.01528</scalar>
               </property>
             </molecule>
           </module>
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern=".*R\sU\sN\s+T\sY\sP\sE.*" endPattern=".*" endOffset="0">    <record id="runtype">.*R\sU\sN\s+T\sY\sP\sE\s\:{X,cc:runtype}\*.*</record>    <transform process="pullup" repeat="2" xpath=".//cml:scalar[@dictRef='cc:runtype']" />
           </template>  <xi:include href="runtype/geometry.xml" />  <xi:include href="runtype/symmetry.xml" />   
       </templateList>
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
