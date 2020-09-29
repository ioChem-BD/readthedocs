.. _timing-d3e5279:

timing
======

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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | timing                            |
   +-----------------------------------+-----------------------------------+
   | name                              | Timing statistics resume          |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Timing\sStatistics.\*         |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .                                 |
   |                                   | *\.{5,}+(\s+\S+\s*){6}.*$\s*$\s\* |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 2                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | statistics/timing.xml             |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    =================
    Timing Statistics
    =================
     
    Total Used :                     CPU=        0.32      System=        0.16     Elapsed=        1.05
    
     Calls  Section                     ( Mean, Percentage )
    ---------------------------------------------------------------------------------------------------
        2          ................      0.00    0.00             0.00    0.00             0.00    0.00
        1  EXIT PROCEDURE .........      0.75  100.00             0.16  100.00             0.99  100.00
        
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="timing">
          <module cmlx:lineCount="11" cmlx:templateRef="timing">
           <scalar dataType="xsd:double" dictRef="cc:cputime">0.32</scalar>
           <scalar dataType="xsd:double" dictRef="cc:systemtime">0.16</scalar>
           <scalar dataType="xsd:double" dictRef="cc:elapsedtime">1.05</scalar>
          </module>  
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Total\s+Used\s+:.*" endPattern=".*" endOffset="0">    <record>\s*Total\s+Used\s+:\s+CPU={F,cc:cputime}System={F,cc:systemtime}Elapsed={F,cc:elapsedtime}</record>    <transform process="pullup" repeat="3" xpath=".//cml:scalar" />
           </template>
           
       </templateList>
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
