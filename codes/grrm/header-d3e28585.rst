.. _header-d3e28585:

header
======

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
   | *source*                                                                                                                   | GRRM log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | header                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Global Reaction Route Mapping.\*                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;*&#92;*&#92;*&#92;*.\*                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 4                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | header.xml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    Global Reaction Route Mapping (GRRM) Program,                           
        Produced by Satoshi Maeda, Yu Harabuchi, Yosuke Sumiya,             
                    Makito Takagi, Kimichi Suzuki, Kanami Sugiyama,         
                    Yuriko Ono, Miho Hatanaka, Yuto Osada,                  
                    Tetsuya Taketsugu, Keiji Morokuma, Koichi Ohno,         
                                     (Version 23, Release: January 23, 2023)
   *************************************************************************
    SADDLE: Saddle-point optimization                                (by SM)
         using the interface with the GAUSSIAN program               (by SM)
   *************************************************************************
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="header">
       <module cmlx:templateRef="header">
          <scalar cmlx:templateRef="program.name" dataType="xsd:string" dictRef="cc:program">GRRM</scalar>
          <module cmlx:templateRef="authors">
             <scalar dataType="xsd:string" dictRef="g:unparsed">Satoshi Maeda, Yu Harabuchi, Yosuke Sumiya,</scalar>
             <scalar dataType="xsd:string" dictRef="g:unparsed">Makito Takagi, Kimichi Suzuki, Kanami Sugiyama,</scalar>
             <scalar dataType="xsd:string" dictRef="g:unparsed">Yuriko Ono, Miho Hatanaka, Yuto Osada,</scalar>
             <scalar dataType="xsd:string" dictRef="g:unparsed">Tetsuya Taketsugu, Keiji Morokuma, Koichi Ohno,</scalar>
          </module>
          <list cmlx:templateRef="program.version">
             <scalar dataType="xsd:integer" dictRef="cc:programVersion">23</scalar>
             <scalar dataType="xsd:string" dictRef="cc:programDate">January 23, 2023</scalar>
          </list>
          <module cmlx:templateRef="run.details">
             <scalar dataType="xsd:string" dictRef="cc:runtype">SADDLE</scalar>
             <scalar dataType="xsd:string" dictRef="g:run.specification">Saddle-point optimization</scalar>
             <list cmlx:templateRef="run.type" />
             <scalar dataType="xsd:string" dictRef="g:programDriver">GAUSSIAN</scalar>
          </module>        
       </module>
   </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <record id="program.name">\s*Global Reaction Route Mapping \({X,cc:program}\).*</record>
   <transform process="pullupSingleton" xpath="./cml:list" />
   <template id="authors" pattern="\s*Produced by.*" endPattern="\s*\(Version.*">  <record id="program.authors" delimiter=",">\s*Produced by {X,g:unparsed}</record>  <record id="program.authors" repeat="*">\s*{X,g:unparsed}</record>  <transform process="pullup" xpath=".//cml:scalar" />
       </template>
   <record id="program.version">\s*\(Version\s*{I,cc:programVersion},\s*Release:\s*{X,cc:programDate}\)</record>
   <transform process="pullup" xpath="./cml:list/cml:list/cml:scalar" />
   <template id="run.details" pattern="\*\*\*\*.*" endPattern="\*\*\*\*.*">  <record id="null" />  <record id="run.type">\s*{X,cc:runtype}:\s*{X,g:run.specification}\s*\(.*</record>  <record id="driver.type">\s*using the interface with the {X,g:programDriver} program.*</record>  <transform process="pullup" xpath="./cml:list/cml:list/cml:scalar" />  <transform process="pullup" xpath="./cml:list/cml:scalar" />
       </template>
   <transform process="pullupSingleton" xpath="./cml:module" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
