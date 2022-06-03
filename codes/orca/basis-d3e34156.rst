.. _basis-d3e34156:

basis
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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | basis                                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Basis Set Information                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;-+&#92;s*$&#92;s*BASIS&#92;sSET&#92;sINFORMATION&#92;s*$&#92;s*&#92;-+&#92;s\*                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s+&#92;*{5,}.\*                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;-+.*$&#92;S+.*$&#92;-+.\*                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | job/basis.xml                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   ---------------------
   BASIS SET INFORMATION
   ---------------------
   There are 4 groups of distinct atoms

    Group   1 Type O   : 7s4p1d contracted to 3s2p1d pattern {511/31/1}
    Group   2 Type H   : 4s1p contracted to 2s1p pattern {31/1}
    Group   3 Type C   : 7s4p1d contracted to 3s2p1d pattern {511/31/1}
    Group   4 Type N   : 7s4p1d contracted to 3s2p1d pattern {511/31/1}

   Atom   0O    basis set group =>   1
   Atom   1O    basis set group =>   1
   Atom   2H    basis set group =>   2
   Atom   3H    basis set group =>   2
   Atom   4H    basis set group =>   2
   Atom   5H    basis set group =>   2
   Atom   6O    basis set group =>   1
   Atom   7C    basis set group =>   3
   Atom   8C    basis set group =>   3
   Atom   9C    basis set group =>   3
   Atom  10H    basis set group =>   2
   Atom  11H    basis set group =>   2
   Atom  12H    basis set group =>   2
   Atom  13H    basis set group =>   2
   Atom  14H    basis set group =>   2
   Atom  15H    basis set group =>   2
   Atom  16O    basis set group =>   1
   Atom  17N    basis set group =>   4
   Atom  18N    basis set group =>   4
   Atom  19C    basis set group =>   3
   Atom  20C    basis set group =>   3
   Atom  21C    basis set group =>   3
   Atom  22C    basis set group =>   3
   Atom  23C    basis set group =>   3
   Atom  24C    basis set group =>   3
   Atom  25C    basis set group =>   3
   Atom  26C    basis set group =>   3
   Atom  27H    basis set group =>   2
   Atom  28H    basis set group =>   2
   Atom  29H    basis set group =>   2
   Atom  30H    basis set group =>   2
   Atom  31H    basis set group =>   2
   Atom  32H    basis set group =>   2
   Atom  33H    basis set group =>   2
   Atom  34H    basis set group =>   2
   Atom  35H    basis set group =>   2
   Atom  36H    basis set group =>   2
   Atom  37H    basis set group =>   2
   Atom  38H    basis set group =>   2
   Atom  39H    basis set group =>   2
   Atom  40H    basis set group =>   2
   -------------------------------
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="basis">
         <module cmlx:templateRef="basis">        
            <list cmlx:templateRef="group">
               <array dataType="xsd:integer" dictRef="o:group" size="4">1 2 3 4</array>
               <array dataType="xsd:string" dictRef="o:primitive" size="4">7s4p1d 4s1p 7s4p1d 7s4p1d</array>
               <array dataType="xsd:string" dictRef="o:contraction" size="4">3s2p1d 2s1p 3s2p1d 3s2p1d</array>
            </list>
            <list dictRef="atombasis">
               <array dataType="xsd:integer" dictRef="cc:serial" size="41">0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40</array>
               <array dataType="xsd:string" dictRef="cc:elementType" size="41">O O H H H H O C C C H H H H H H O N N C C C C C C C C H H H H H H H H H H H H H H</array>
               <array dataType="xsd:integer" dictRef="o:group" size="41">1 1 2 2 2 2 1 3 3 3 2 2 2 2 2 2 1 4 4 3 3 3 3 3 3 3 3 2 2 2 2 2 2 2 2 2 2 2 2 2 2</array>
            </list>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="basisgroups" pattern="\s*Group.*" endPattern="\s*" endPattern2="~">    <record id="group" repeat="*">\s*Group{I,o:group}Type.*:{A,o:primitive}contracted\sto\s{A,o:contraction}pattern.*</record>
           </template>  <template id="atombasis" pattern="\s*Atom.*" endPattern=".*" endPattern2="~" repeat="*">    <record>\s*Atom{I,cc:serial}{A,cc:elementType}basis\sset\sgroup\s=>{I,o:group}</record>                                             
           </template>       
       </templateList>
   <transform process="createArray" xpath="." from=".//cml:list[@cmlx:templateRef='group']//cml:scalar[@dictRef='o:group']" />
   <transform process="createArray" xpath="." from=".//cml:list[@cmlx:templateRef='group']//cml:scalar[@dictRef='o:primitive']" />
   <transform process="createArray" xpath="." from=".//cml:list[@cmlx:templateRef='group']//cml:scalar[@dictRef='o:contraction']" />
   <transform process="move" xpath=".//cml:list[@cmlx:templateRef='group']/cml:list/cml:array" to=".//cml:list[@cmlx:templateRef='group']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="moveRelative" xpath=".//cml:list[@cmlx:templateRef='group']" to="../.." />
   <transform process="createArray" xpath="." from=".//cml:module[@cmlx:templateRef='atombasis']//cml:scalar[@dictRef='cc:serial']" />
   <transform process="createArray" xpath="." from=".//cml:module[@cmlx:templateRef='atombasis']//cml:scalar[@dictRef='cc:elementType']" />
   <transform process="createArray" xpath="." from=".//cml:module[@cmlx:templateRef='atombasis']//cml:scalar[@dictRef='o:group']" />
   <transform process="addChild" xpath="." elementName="cml:list" dictRef="atombasis" />
   <transform process="move" xpath=".//cml:module[@cmlx:templateRef='atombasis']//cml:array" to=".//cml:list[@dictRef='atombasis']" />
   <transform process="delete" xpath=".//cml:module" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
