.. _header-d3e44252:

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
   | *source*                                                                                                                   | QuantumEspresso log                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | header                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Program version                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | ^&#92;s*Program&#92;s*.*starts&#92;son.\*                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .\*                                                                                                                        |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | initialization/header.xml                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    Program PWSCF v.6.1 (svn rev. 13369) starts on 28Sep2017 at 18:37:43 
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="header">
           <module cmlx:templateRef="header">
                <scalar dataType="xsd:string" dictRef="cc:program">QuantumEspresso</scalar>
                <scalar dataType="xsd:string" dictRef="cc:module">PWSCF</scalar>
                <scalar dataType="xsd:string" dictRef="cc:programVersion">6.1</scalar>
                <scalar dataType="xsd:string" dictRef="cc:programSubversion">13369</scalar>
                <scalar dataType="xsd:date" dictRef="cc:rundate">2017-09-28T18:37:43.000+02:00</scalar>
           </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="header1" pattern="\s*Program.*\(svn.*\)\s*starts\s*on.*" endPattern=".*" endPattern2="~">    <record>\s*Program{A,cc:module}\s*v\.{A,cc:programVersion}\s\(svn\srev\.\s{A,cc:programSubversion}\)\sstarts\son{X,x:date}</record>      
           </template>  <template id="header2" pattern="\s*Program.*\s*starts\s*on.*">    <record>\s*Program{A,cc:module}\s*v\.{A,cc:programVersion}\s*starts\son{X,x:date}</record>
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
   <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="cc:program" position="0" />
   <transform process="setValue" xpath="./cml:scalar[@dictRef='cc:program']" value="QuantumEspresso" />
   <transform process="setValue" xpath=".//cml:scalar[@dictRef='x:date']" value="$string(replace(replace(..//cml:scalar[@dictRef='x:date']/text(), 'at  ', 'at 0'), ': ', ':0'))" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='x:date']" format="ddMMMyyyy 'at' HH:mm:ss" />
   <transform process="addAttribute" xpath=".//cml:scalar[@dictRef='cc:programVersion']" name="dataType" value="xsd:string" />
   <transform process="addAttribute" xpath=".//cml:scalar[@dictRef='x:date']" name="dictRef" value="cc:rundate" />
   <transform process="addAttribute" xpath=".//cml:scalar[@dictRef='cc:program']" name="dataType" value="xsd:string" />
   <transform process="delete" xpath=".//cml:module" />
   <transform process="delete" xpath=".//cml:list" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
