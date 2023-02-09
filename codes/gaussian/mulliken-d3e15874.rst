mulliken
-------------------------------------- 

.. toctree::
   :maxdepth: 5    
      
   /codes/gaussian/l601.mullikenspin-d3e15914

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
   | *source*                                                                                                                   | Gaussian log                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | mulliken                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | mulliken                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | newline                                                                                                                    | $                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Mulliken&#92;s*([Aa]tomic)?&#92;s*charges:&#92;s\*                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*Charge=.\*                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | l601/l601.mulliken.xml                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    Mulliken atomic charges:
                 1
        1  C   -0.619218
        2  H    0.154804
        3  H    0.154804
        4  H    0.154804
        5  H    0.154804
    Sum of Mulliken charges=   0.00000
    Atomic charges with hydrogens summed into heavy atoms:
                 1
        1  C    0.000000
        2  H    0.000000
        3  H    0.000000
        4  H    0.000000
        5  H    0.000000
    Sum of Mulliken charges=   0.00000
    Electronic spatial extent (au):  <R**2>=    36.2154
    Charge=     0.0000 electrons
     

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="l601.mulliken">
       <module cmlx:templateRef="mulliken">
         <module cmlx:lineCount="8" cmlx:templateRef="l601.mullik">
           <scalar dataType="xsd:string" dictRef="g:title">Mulliken atomic charges:</scalar>
           <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
           <list cmlx:lineCount="5" cmlx:templateRef="row">
             <array dataType="xsd:integer" dictRef="cc:serial" size="5">1 2 3 4 5</array>
             <array dataType="xsd:string" dictRef="cc:elementType" size="5">C H H H H</array>
             <array dataType="xsd:double" dictRef="x:charge" size="5">-0.619218 0.154804 0.154804 0.154804 0.154804</array>
           </list>
           <scalar dataType="xsd:string" dictRef="x:type">Mulliken</scalar>
           <scalar dataType="xsd:double" dictRef="x:chargesum">0.0</scalar>
         </module>
         <module cmlx:lineCount="8" cmlx:templateRef="l601.mullik">
           <scalar dataType="xsd:string" dictRef="g:title">Atomic charges with hydrogens summed into heavy atoms:</scalar>
           <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
           <list cmlx:lineCount="5" cmlx:templateRef="row">
             <array dataType="xsd:integer" dictRef="cc:serial" size="5">1 2 3 4 5</array>
             <array dataType="xsd:string" dictRef="cc:elementType" size="5">C H H H H</array>
             <array dataType="xsd:double" dictRef="x:charge" size="5">0.0 0.0 0.0 0.0 0.0</array>
           </list>
           <scalar dataType="xsd:string" dictRef="x:type">Mulliken</scalar>
           <scalar dataType="xsd:double" dictRef="x:chargesum">0.0</scalar>
         </module>
         <scalar dataType="xsd:double" dictRef="g:electextent2">36.2154</scalar>
         <scalar dataType="xsd:double" dictRef="g:charge">0.0</scalar>
       </module>
     </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="l601.mullik" repeat="*" pattern=".*[Aa]tomic\scharges.*|\s*Mulliken\scharges.*|\s+Atomic\scharges\swith\shydrogens\ssummed.*|\s+APT\satomic\scharges.*|\s+Mulliken\scharges\swith\shydrogens.*" endPattern="\s*Sum of.*" endOffset="1">    <record id="title">{X,g:title}</record>    <record id="serial">{I,cc:serial}</record>    <record id="row" makeArray="true" repeat="*">{I,cc:serial}{A,cc:elementType}{F,x:charge}</record>    <record id="sum">\s+Sum\sof.*={F,x:chargesum}</record>
       </template>  <template id="l601.spatial" pattern="\s*Electronic spatial extent.*" repeat="*" endPattern=".*" endOffset="0">    <record id="l601.elect">\s*Electronic spatial extent.*={F,g:electextent2}\s*</record>
       </template>  <template id="l601.charge" pattern="\s*Charge\s*=.*" repeat="*" endPattern=".*" endOffset="0">    <record id="l601.charge">\s*Charge=\s*{F,g:charge}\s*electrons\s*</record>
       </template>  <template pattern="\s*" endPattern=".*">    <record repeat="1" />
       </template>  <xi:include href="l601.mullikenspin.xml" />
     </templateList>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="pullup" xpath=".//cml:list/cml:scalar" />
   <transform process="pullup" xpath=".//cml:module[@cmlx:templateRef='l601.spatial']/cml:scalar" />
   <transform process="pullup" xpath=".//cml:module[@cmlx:templateRef='l601.charge']/cml:scalar" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='l601.spatial']" />
   <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='l601.charge']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
