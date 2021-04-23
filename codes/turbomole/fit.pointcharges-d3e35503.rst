.. _fit.pointcharges-d3e35503:

fit.pointcharges
================

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
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | fit.pointcharges                  |
   +-----------------------------------+-----------------------------------+
   | name                              | Fit of point charges due to       |
   |                                   | electrostatic potential           |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*={20,}\s                      |
   |                                   | *$\s*fit\sof\spoint\scharges\sdue |
   |                                   | \sto\selectrostatic\spotential.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s*={20,}\s\*                |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | fit/fit.pointcharges.xml          |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ==============================================================================
                 fit of point charges due to electrostatic potential
   ==============================================================================
       
   ... 
   ------------------------------------------------------------------------------
           charges resulting from fit:
   ------------------------------------------------------------------------------

     atom  radius/au   charge
      1 c   4.497548  0.276087
      2 c   4.497548 -0.215139
      3 c   4.497548 -0.287583
      4 c   4.497548  0.316100
      5 c   4.497548 -0.218323
      6 c   4.497548 -0.240288
      7 h   3.174740  0.163610
      8 h   3.174740  0.150389
      9 h   3.174740  0.170721
     10 h   3.174740  0.164721
     11 f   3.889056 -0.171465
     12 o   4.021337 -0.515902
     13 h   3.174740  0.407072     

   .. 
   ==============================================================================  
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="fit.pointcharges">
           <module cmlx:templateRef="fit.pointcharges">
               <module cmlx:templateRef="fitcharges">
                   <array dataType="xsd:integer" dictRef="cc:serial" size="13">1 2 3 4 5 6 7 8 9 10 11 12 13</array>
                   <array dataType="xsd:string" dictRef="cc:elementType" size="13">c c c c c c h h h h f o h</array>
                   <array dataType="xsd:double" dictRef="t:charge" size="13">0.276087 -0.215139 -0.287583 0.316100 -0.218323 -0.240288 0.163610 0.150389 0.170721 0.164721 -0.171465 -0.515902 0.407072</array>
               </module>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="fitcharges" pattern="\s*-{20,}\s*$\s*charges\sresulting\sfrom\sfit:\s*" endPattern="\s+\w+.*$\s*" endOffset="1">    <record repeat="5" />    <record repeat="*" makeArray="true">{I,cc:serial}{A,cc:elementType}\s+\S+\s+{F,t:charge}</record>    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list" />    <transform process="delete" xpath=".//cml:module" />
           </template>
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
