.. _molcas.input-d3e42189:

molcas.input
============

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
   | *source*                                                                                                                   | MOLCAS input                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | molcas.input                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | MOLCAS input                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

**Comment.**

::

   > DO WHILE

    &SEWARD &END
   Symmetry
    Y XYZ
   Basis set
   C.ano-s...4s3p1d.
   C   0.73915685  0.00000000 -0.19129462  Angstrom
   End of Basis
   Basis set
   H.ano-s...2s1p.
   H1  1.37322192  0.00000000  0.69209432  Angstrom
   H2  0.99210112  0.87816821 -0.78047182  Angstrom
   End of Basis
   End of Input

    &RASSCF &END
   Nactel
    6 0 0
   Inactive
    2 0 3 1
   RAS2
    3 1 2 1
   End of Input

    &CASPT2 &END
   End of Input

    &SLAPAF &END
   End of Input

   > END DO

    &MCKINLEY &END
   End of Input
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="molcas.input">
         <module id="molcas.input">
            <module cmlx:templateRef="basis">
               <array delimiter="|" dictRef="m:basis1" size="7">C|ano-s|||4s3p1d||</array>
               <list>
                  <scalar dataType="xsd:string" dictRef="m:label">C</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:x3">0.73915685</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:y3">0.00000000</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:z3">-0.19129462</scalar>
               </list>
            </module>
            <module cmlx:templateRef="basis">
               <array delimiter="|" dictRef="m:basis1" size="7">H|ano-s|||2s1p||</array>
               <list>
                  <scalar dataType="xsd:string" dictRef="m:label">H1</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:x3">1.37322192</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:y3">0.00000000</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:z3">0.69209432</scalar>
               </list>
               <list>
                  <scalar dataType="xsd:string" dictRef="m:label">H2</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:x3">0.99210112</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:y3">0.87816821</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:z3">-0.78047182</scalar>
               </list>
            </module>
            <map id="atomTypeLabels">
               <link from="C" to="C" />
               <link from="C" to="C" />
               <link from="H1" to="H" />
               <link from="H2" to="H" />
               <link from="H2" to="H" />
            </map>
            <module dictRef="unprocessed">
               <scalar dataType="xsd:string" dictRef="m:inputline">> DO WHILE</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline" />
               <scalar dataType="xsd:string" dictRef="m:inputline">&SEWARD &END</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">Symmetry</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">Y XYZ</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">End of Input</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline" />
               <scalar dataType="xsd:string" dictRef="m:inputline">&RASSCF &END</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">Nactel</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">6 0 0</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">Inactive</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">2 0 3 1</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">RAS2</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">3 1 2 1</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">End of Input</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline" />
               <scalar dataType="xsd:string" dictRef="m:inputline">&CASPT2 &END</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">End of Input</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline" />
               <scalar dataType="xsd:string" dictRef="m:inputline">&SLAPAF &END</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">End of Input</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline" />
               <scalar dataType="xsd:string" dictRef="m:inputline">> END DO</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline" />
               <scalar dataType="xsd:string" dictRef="m:inputline">&MCKINLEY &END</scalar>
               <scalar dataType="xsd:string" dictRef="m:inputline">End of Input</scalar>
            </module>
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="basis" name="Basis set" pattern="\s*(?i)BASIS\s*SET\s*" endPattern="\s*(?i)END\s*OF\s*BASIS.*\s*" endOffset="1" repeat="*">    <record />    <record>{X,m:basisline}</record>    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis1" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[1])" />    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis2" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[2])" />    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis3" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[3])" />    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis4" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[4])" />    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis5" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[5])" />    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis6" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[6])" />    <transform process="addChild" id="test" xpath="." elementName="cml:scalar" dictRef="m:basis7" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[7])" />    <template pattern=".*" endPattern=".*" endPattern2="~" repeat="*">      <record>{A,m:label}{F,cc:x3}{F,cc:y3}{F,cc:z3}{X,x:units}.*</record>      <transform process="addChild" id="atomType" xpath="." elementName="cml:scalar" dictRef="atomType" value="$string((//cml:scalar[@dictRef='m:basis1'])[last()])" />      <transform process="addChild" id="atomLabel" xpath="." elementName="cml:scalar" dictRef="atomLabel" value="$string((//cml:scalar[@dictRef='m:label'])[last()])" />
               </template>    <transform process="pullup" xpath=".//cml:list[cml:scalar[@dictRef='m:label']]" repeat="2" />    <transform process="addChild" id="atomType" xpath="." elementName="cml:scalar" dictRef="cc:elementType" value="$string((tokenize(.//cml:scalar[@dictRef='m:basisline'],'\.'))[1])" />    <transform process="delete" xpath=".//cml:scalar[@dictRef='m:basisline']" />    <transform process="createArray" delimiter="|" xpath="." from=".//cml:scalar[starts-with(@dictRef,'m:basis')]" />    <transform process="pullup" xpath=".//cml:list/cml:list" />    <transform process="delete" xpath=".//cml:list[count(*) = 0]" />    <transform process="delete" xpath=".//cml:scalar[not(text())]" />
           </template>  <transform process="addMap" xpath="." id="atomTypeLabels" from=".//cml:scalar[@dictRef='atomLabel']" to=".//cml:scalar[@dictRef='atomType']" />  <transform process="delete" xpath=".//cml:scalar[@id='atomType']" />  <transform process="delete" xpath=".//cml:scalar[@id='atomLabel']" />  <template id="xfield" name="Xfield integrals" pattern="\s*(?i)XFIELD\s*INTEGRALS.*" endPattern="\s*" endPattern2="\s*[a-zA-Z].*">    <record />    <record>{I,x:linecount}</record>    <record repeat="*" makeArray="true">{F,m:xfiecol1}{F,m:xfiecol2}{F,m:xfiecol3}{F,m:xfiecol4}{F,m:xfiecol5}{F,m:xfiecol6}{F,m:xfiecol7}</record>    <transform process="pullup" xpath=".//cml:scalar" />    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list" />
           </template>  <template id="keyword" name="One line value keywords" pattern="\s*(?i)\s*(UHF|TS|KSDFT).*" endPattern=".*" endPattern2="~">    <record repeat="*">{X,m:keyword}</record>                               
           </template>  <template pattern=".*" endPattern="~" repeat="*" endOffset="0">    <record repeat="*">{X,m:inputline}</record>
           </template>  <transform process="move" xpath=".//cml:scalar[@dictRef='m:keyword']" to="." />  <transform process="delete" xpath=".//cml:module[@cmlx:templateRef='keyword']" />  <transform process="addChild" xpath="." elementName="cml:module" dictRef="unprocessed" />  <transform process="move" xpath=".//cml:scalar[@dictRef='m:inputline']" to=".//cml:module[@dictRef='unprocessed']" />  <transform process="delete" xpath=".//cml:list[count(*) = 0]" />  <transform process="delete" xpath=".//cml:module[count(*) = 0]" />
           
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
