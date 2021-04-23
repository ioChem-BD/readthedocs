.. _module.header-d3e19159:

module.header
=============

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
   | id                                | module.header                     |
   +-----------------------------------+-----------------------------------+
   | name                              | Module header                     |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*(\(\)){20,}\s                 |
   |                                   | *$\s*MOLCAS\sexecuting\smodule.\* |
   +-----------------------------------+-----------------------------------+
   | pattern2                          | \\s*---\s*Start\s*Module.\*       |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s\*                             |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*---\s\*                       |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/module.header.xml         |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()
                                     MOLCAS executing module SEWARD with 400 MB of memory                                  
                                                 at 14:02:49 Mon May 30 2011                                               
   ()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()()

       

**Input.**

::

   --- Start Module: slapaf at Wed Jan 20 21:04:10 2016
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="module.header">
           <module cmlx:templateRef="module.header">
               <scalar dataType="xsd:string" dictRef="m:module">SEWARD</scalar>
               <scalar dataType="xsd:string" dictRef="cc:runDate">14:02:49 Mon May 30 2011</scalar>
           </module> 
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="">
           <module cmlx:templateRef="module.header">
               <scalar dataType="xsd:string" dictRef="m:module">slapaf</scalar>
               <scalar dataType="xsd:string" dictRef="cc:runDate">Wed Jan 20 21:04:10 2016</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*(\(\)){20,}\s*$\s*MOLCAS\sexecuting\smodule.*" endPattern="~">    <record />    <record>\s*MOLCAS\sexecuting\smodule{X,m:module}with.*</record>    <record>\s*at\s*{X,cc:runDate}</record>
                   
           </template>  <template pattern="\s*---\s*Start.*" endPattern="~">    <record>\s*---\s*Start\s*Module:{A,m:module}at{X,cc:runDate}</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="1" />
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
