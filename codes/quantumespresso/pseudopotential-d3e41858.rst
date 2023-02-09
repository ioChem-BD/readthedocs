.. _pseudopotential-d3e41858:

pseudopotential
===============

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
   | *source*                                                                                                                   | QuantumEspresso log                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | pseudopotential                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Pseudopotential section                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*PseudoPot.*for.*read&#92;sfrom&#92;sfile:.\*                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | initialization/pseudopotential.xml                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

        PseudoPot. # 1 for Fe read from file:
        /home/hnguyen/espresso_pseudo/Fe.pbe-sp-van_ak.UPF
        MD5 check sum: 874d5528bf087cea5d785f7b6a7bf583
        Pseudo is Ultrasoft, Zval = 16.0
        Generated by new atomic code, or converted to UPF format
        Using radial grid of  861 points,  6 beta functions with: 
                   l(1) =   0
                   l(2) =   0
                   l(3) =   1
                   l(4) =   1
                   l(5) =   2
                   l(6) =   2
        Q(r) pseudized with  8 coefficients,  rinner =    1.500   1.500   1.500
                                                          1.500   1.500
                                                           
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="pseudopotential">
           <module cmlx:templateRef="pseudopotential">
               <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
               <scalar dataType="xsd:string" dictRef="cc:elementType">Fe</scalar>
               <scalar dataType="xsd:string" dictRef="qex:pseudofile">Fe.pbe-sp-van_ak.UPF</scalar>
               <scalar dataType="xsd:string" dictRef="qex:md5sum">874d5528bf087cea5d785f7b6a7bf583</scalar>
               <scalar dataType="xsd:string" dictRef="qex:pseudopotential">Ultrasoft</scalar>
               <scalar dataType="xsd:double" dictRef="qex:zval">16.0</scalar>
               <scalar dataType="xsd:integer" dictRef="qex:gridpoints">861</scalar>
               <scalar dataType="xsd:integer" dictRef="qex:betafunctions">6</scalar>
               <list cmlx:templateRef="lvalue">
                  <array dataType="xsd:integer" dictRef="cc:serial" size="6">1 2 3 4 5 6</array>
                  <array dataType="xsd:integer" dictRef="cc:value" size="6">0 0 1 1 2 2</array>
               </list>
               <scalar dataType="xsd:integer" dictRef="qex:qrcoeffs">8</scalar>
               <array dataType="xsd:double" dictRef="qex:rinner" size="5">1.500 1.500 1.500 1.500 1.500</array>
            </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record>\s*PseudoPot\.\s*\#{I, cc:serial}for{A,cc:elementType}read\s*from\s*file:.*</record>
   <record>.*/{A,qex:pseudofile}</record>
   <record>\s*MD5\scheck\ssum:{X,qex:md5sum}</record>
   <record>\s*Pseudo\sis{X,qex:pseudopotential},\s*Zval\s={F,qex:zval}</record>
   <record repeat="1" />
   <record>\s*Using\sradial\sgrid\sof{I,qex:gridpoints}points,\s*{I,qex:betafunctions}beta\sfunctions\swith:.*</record>
   <record id="lvalue" repeat="*" makeArray="true">\s*l\({I,cc:serial}\)\s*={I, cc:value}</record>
   <record>\s*Q\(r\)\spseudized\swith{I,qex:qrcoeffs}coefficients,\s*rinner\s={1_5F,qex:rinner}</record>
   <record repeat="*">{1_8F,qex:rinner}</record>
   <transform process="joinArrays" xpath=".//cml:array[@dictRef='qex:rinner']" />
   <transform process="pullup" xpath=".//cml:*[parent::cml:list[not(@cmlx:templateRef='lvalue')]]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
