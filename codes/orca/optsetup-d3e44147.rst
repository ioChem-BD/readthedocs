.. _optsetup-d3e44147:

optsetup
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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | optsetup                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Optimization Coordinate Setup                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{20,}$&#92;s*Redundant&#92;sInternal&#92;sCoordinates.\*                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Number&#92;sof&#92;sdegrees&#92;sof&#92;sfreedom.\*                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s*&#92;*{10,}.\*                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | keep                                                                                                                       | first                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/optsetup.xml                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       -----------------------------------------------------------------
                       Redundant Internal Coordinates


       -----------------------------------------------------------------
            Definition                    Initial Value    Approx d2E/dq
       -----------------------------------------------------------------
         1. B(H   1,O   0)                  1.0000         0.448900   
         2. B(H   2,O   0)                  1.0000         0.448900   
         3. A(H   1,O   0,H   2)           90.0000         0.306850 C 
       -----------------------------------------------------------------

   Number of atoms                         .... 3
   Number of degrees of freedom            .... 3  
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="optsetup">        
           <module cmlx:templateRef="optsetup" dictRef="cc:userDefinedModule">
              <list>
                 <scalar dataType="xsd:string" dictRef="x:restriction">A</scalar>
                 <array dataType="xsd:integer" dictRef="x:serial" size="3">1 0 2</array>
                 <scalar dataType="xsd:double" dictRef="x:parameter">90.0000</scalar>
                 <scalar dataType="xsd:double" dictRef="o:d2E_dq">0.306850</scalar>
              </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <record repeat="7" />
   <templateList>  <template id="cartesian" pattern=".*C.*\(.*\).*C\s*" endPattern=".*" endPattern2="~" repeat="*">    <record>.*\.{A,x:restriction}\(\w+\s+{I,x:serial}\){F,x:parameter}{F,o:d2E_dq}.*C\s*</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:serial']" />          
           </template>  <template id="bond" pattern=".*B\(.*\).*C\s*" endPattern=".*" endPattern2="~" repeat="*">    <record>.*\.{A,x:restriction}\(\w+\s+{I,x:serial},\w+\s+{I,x:serial}\){F,x:parameter}{F,o:d2E_dq}.*C\s*</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:serial']" />         
           </template>  <template id="angle" pattern=".*A\(.*\).*C\s*" endPattern=".*" endPattern2="~" repeat="*">    <record>.*\.{A,x:restriction}\(\w+\s+{I,x:serial},\w+\s+{I,x:serial},\w+\s+{I,x:serial}\){F,x:parameter}{F,o:d2E_dq}.*C\s*</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:serial']" />
           </template>  <template id="dihedral" pattern=".*D\(.*\).*C\s*" endPattern=".*" endPattern2="~" repeat="*">    <record>.*\.{A,x:restriction}\(\w+\s+{I,x:serial},\w+\s+{I,x:serial},\w+\s+{I,x:serial},\w+\s+{I,x:serial}\){F,x:parameter}{F,o:d2E_dq}.*C\s*</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:serial']" />
           </template>  <template id="plane" pattern=".*L\(.*\).*C\s*" endPattern=".*" endPattern2="~" repeat="*">    <record>.*\.{A,x:restriction}\(\w+\s+{I,x:serial},\w+\s+{I,x:serial},\w+\s+{I,x:serial},\w+\s+{I,x:serial},{I,x:value}\){F,x:parameter}{F,o:d2E_dq}.*C\s*</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:serial']" />
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:list[./cml:scalar]" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
