.. _constraint-d3e24216:

constraint
==========

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image0|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | constraint                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Contraints section                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*(?i)()(CONSTRAINTS){5,}.\*                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*(?i)()(CONSTRAINTS){5,}.*$&#92;s*(?i)()(CONSTRAINTS){5,}.\*                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 2                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/constraint.xml                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

**Input.**

::

   ConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraints
   ConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraints
   Constraints                                                                                        Constraints
   Constraints                                 C O N S T R A I N T S                                  Constraints
   Constraints                                                                                        Constraints

   ************************************************************************************************************************
   A = ANGLE H1 O H2                                                                                                       
   VALUES                                                                                                                  
   A = 110 DEGREES                                                                                                         
   ************************************************************************************************************************


    *************************************************************
    * Values of the primitive constraints                       *
    *************************************************************
    A        : Angle=      108.9246   / Degree    1.901094 / rad


    *******************************************
    * Values of the constraints   / au or rad *
    *******************************************
      Label        C         C0
    Cns001      1.901094  1.919862

   Constraints                                                                                        Constraints
   ConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraints
   ConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraintsConstraints          
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="constraint">
           <module cmlx:templateRef="constraint">
               <list>
                  <scalar dataType="xsd:string" dictRef="m:restrictionlabel">A</scalar>
                  <scalar dataType="xsd:string" dictRef="m:restriction">ANGLE</scalar>
                  <scalar dataType="xsd:string" dictRef="m:restrictionextras">H1 O H2</scalar>
               </list>
               <list>
                  <scalar dataType="xsd:string" dictRef="m:restrictionlabel">A</scalar>
                  <scalar dataType="xsd:string" dictRef="m:restrictionvalue">110</scalar>
                  <scalar dataType="xsd:string" dictRef="m:restrictionunit">DEGREES</scalar>
               </list>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <template pattern="\s*\*{40,}\s*$\s*.*(ANGLE|BOND|DIHEDRAL|OUTOFP).*" endPattern="\s*VALUES.*">  <record />  <record repeat="*">{A,m:restrictionlabel}={A,m:restriction}{X,m:restrictionextras}</record>                    
       </template>
   <template pattern="\s*VALUES.*" endPatern="\s*\*{40,}">  <record />  <record repeat="*">{A,m:restrictionlabel}={A,m:restrictionvalue}{X,m:restrictionunit}</record>
       </template>
   <transform process="move" xpath=".//cml:list/cml:list" to="." />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
