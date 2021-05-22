.. _properties-d3e22794:

properties
==========

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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | properties                        |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Expectation\sv                |
   |                                   | alues\sof\svarious\sproperties.\* |
   +-----------------------------------+-----------------------------------+
   | pattern2                          | \\s*(?:\+\+                       |
   |                                   | )?\s*Molecular\s[Pp]roperties:.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\-\-\s\*                      |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | .*ZZ=.*$\s*((?!In).)+             |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/properties/properties.xml |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

      Expectation values of various properties:
      -----------------------------------------
   ...
   --
       

**Input.**

::

         Expectation values of various properties for root number: 1
         -----------------------------------------------------------



   ++       Molecular Properties:
         ---------------------


         Dipole Moment (Debye):                                                          
         Origin of the operator (Ang)=    0.0000    0.0000    0.0000
                        X=    0.0000               Y=    0.0417               Z=    0.0000           Total=    0.0417
         Quadrupole Moment (Debye*Ang):                                                  
         Origin of the operator (Ang)=    0.0000   -0.0011    0.0000
                       XX= -100.0019              XY=    0.0000              XZ=   -8.0446              YY=  -37.1367
                       YZ=    0.0000              ZZ=  -96.3868
         In traceless form (Debye*Ang)
                       XX=  -33.2401              XY=    0.0000              XZ=  -12.0670              YY=   61.0576
                       YZ=    0.0000              ZZ=  -27.8175
   --
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="properties">
           <module cmlx:templateRef="properties">
               <scalar dataType="xsd:integer" dictRef="m:rootnumber">1</scalar>
               <module cmlx:templateRef="mol.props">
                  <list cmlx:templateRef="dipole">
                     <array dataType="xsd:double" dictRef="m:dipole" size="3">0.0000 0.0417 0.0000</array>
                     <scalar dataType="xsd:double" dictRef="m:total">0.0417</scalar>
                     <array dataType="xsd:double" dictRef="m:operatororig" size="3">0.0000 0.0000 0.0000</array>
                  </list>
                  <list cmlx:templateRef="quadrupole">
                     <array dataType="xsd:double" dictRef="m:quadvalue" size="6">-100.0019 0.0000 -8.0446 -37.1367 0.0000 -96.3868</array>
                     <array dataType="xsd:double" dictRef="m:operatororig" size="3">0.0000 -0.0011 0.0000</array>
                     <array dataType="xsd:double" dictRef="m:quadtracevalue" size="6">-33.2401 0.0000 -12.0670 61.0576 0.0000 -27.8175</array>
                  </list>
               </module>
            </module>
       </comment>

**Template definition.**

.. code:: xml

   <xi:include href="modules/properties/prop.root.xml" />
   <xi:include href="modules/properties/mol.props.xml" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='m:rootnumber']" repeat="2" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='root']" />
   <transform process="addChild" id="root" xpath="." elementName="cml:scalar" dictRef="m:rootnumber" value="$string((preceding-sibling::cml:module[@cmlx:templateRef='caspt2.root'])[last()]//cml:scalar/text())" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='m:rootnumber' and not(text())]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
