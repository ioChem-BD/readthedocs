.. _orbital.line-d3e35543:

orbital.line
============

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
   | id                                | orbital.line                      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*irrep.\*                      |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | orbital.line.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

           irrep                  1a1'        2a1'        3a1'        4a1'        5a1' 
    eigenvalues H       -256.02776   -29.97174   -10.18645    -3.38954    -0.88456
               eV       -6966.9251   -815.5790   -277.1896    -92.2348    -24.0702
    occupation              2.0000      2.0000      2.0000      2.0000      2.0000 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="orbital.line">
         <module cmlx:lineCount="5" cmlx:templateRef="orbital">
             <array dataType="xsd:string" size="5" dictRef="cc:irrep">1a1' 2a1' 3a1' 4a1' 5a1'</array>
             <array dataType="xsd:double" size="5" dictRef="t:eigen">-256.02776 -29.97174 -10.18645 -3.38954 -0.88456</array>
             <array dataType="xsd:double" size="5" dictRef="t:orbitalenergy">-6966.9251 -815.579 -277.1896 -92.2348 -24.0702</array>
             <array dataType="xsd:double" size="5" dictRef="cc:occupation">2.0000 2.0000 2.0000 2.0000 2.0000</array>
         </module>
       
       
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="irrep" pattern="\s*irrep.*" endPattern=".*" endPattern2="~" endOffset="0">    <record id="irrep">\s*irrep{1_5A,cc:irrep}</record>                                         
           </template>  <template id="eigenvalues" pattern="\s*eigenvalues.*" endPattern=".*" endPattern2="~" endOffset="0">    <record id="eigenvalues">\s*eigenvalues\sH{1_5F,t:eigen}</record>                                      
           </template>  <template id="orbitalEnergy" pattern="\s*eV.*" endPattern=".*" endPattern2="~" endOffset="0">    <record id="orbitalEnergy">\s*eV{1_5F,t:orbitalenergy}</record>
           </template>  <template id="occupation" pattern="\s*occupation.*" endPattern=".*" endPattern2="~" endOffset="0">    <record id="occupation" makeArray="false">\s*occupation{1_5F,cc:occupation}</record>                 
           </template>  <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:occupation" value="0.0000" />  <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:occupation" value="0.0000" />  <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:occupation" value="0.0000" />  <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:occupation" value="0.0000" />  <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:occupation" value="0.0000" />  <transform process="delete" xpath="    ./cml:scalar[@dictRef='cc:occupation' and position() > (     ..//cml:array[@dictRef='cc:irrep']/@size -      ..//cml:array[@dictRef='cc:occupation']/@size     )]" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:occupation']" />  <transform process="addAttribute" xpath=".//cml:array[@dictRef='cc:occupation']" name="dataType" value="xsd:double" />        
                       
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
