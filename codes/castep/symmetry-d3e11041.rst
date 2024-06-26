.. _symmetry-d3e11041:

symmetry
========

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
   | id                                                                                                                         | symmetry                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Symmetry and constraints                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;-{10,}.*$&#92;s*Symmetry&#92;sand&#92;sConstraints.\*                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*&#92;-{10,}                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | setup/symmetry.xml                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                              -------------------------------
                                  Symmetry and Constraints
                              -------------------------------

                         Cell is a supercell containing 4 primitive cells
                         Maximum deviation from symmetry = 0.120582E-14     ANG

                         Number of symmetry operations   =         192
            There are no ionic constraints specified or generated for this cell
                         Point group of crystal =    32: Oh, m-3m, 4/m -3 2/m
                         Space group of crystal =   227: Fd-3m, F 4d 2 3 -1d

                Set iprint > 1 for details on symmetry rotations/translations

                            Centre of mass is NOT constrained

                            Number of cell constraints= 5
                            Cell constraints are:  1 1 1 0 0 0

                            External pressure/stress (GPa)
                             0.00000   0.00000   0.00000
                                       0.00000   0.00000
                                                 0.00000   

       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="symmetry">
           <module cmlx:templateRef="symmetry">
               <module cmlx:templateRef="operations">
                  <scalar dataType="xsd:integer" dictRef="ca:nsym">192</scalar>
               </module>
               <module cmlx:templateRef="pointgroup">
                  <scalar dataType="xsd:string" dictRef="cc:pointgroup">32: Oh, m-3m, 4/m -3 2/m</scalar>
                  <scalar dataType="xsd:string" dictRef="ca:spacegroup">227: Fd-3m, F 4d 2 3 -1d</scalar>
               </module>
           </module> 
       
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="operations" pattern="\s*Number\sof\ssymmetry\soperations.*" endPattern=".*" endPattern2=".*$\s*">    <record>\s*Number\sof\ssymmetry\soperations\s*={I,ca:nsym}</record>
           </template>  <template id="pointgroup" pattern="\s*Point\sgroup\sof\scrystal.*" endPattern="\s*Space\sgroup\sof\scrystal.*" endPattern2=".*$\s*" endOffset="1">    <record>\s*Point\sgroup\sof\scrystal\s*={X,cc:pointgroup}</record>    <record>\s*Space\sgroup\sof\scrystal\s*={X,ca:spacegroup}</record>     
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
