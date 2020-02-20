.. _process.info-d3e5936:

process.info
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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | process.info                      |
   +-----------------------------------+-----------------------------------+
   | name                              | Parallel Execution: Process       |
   |                                   | Information                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Parallel\sEx                  |
   |                                   | ecution:\sProcess\sInformation.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\(INPUT\sFILE\)\s\*           |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*\*{20,}+\s+                   |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | process.info.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Parallel Execution: Process Information
    =======================================

    Actual Number of Tasks running:    4
    The Master (kid 0) runs on host maginet-ii190

     Kid Node                   Speed          Task ID   Status
   ------------------------------------------------------------------
       0 maginet-ii190             -1                0
       1 maginet-ii190             -1                1
       2 maginet-ii190             -1                2
       3 maginet-ii190             -1                3
    
    Communication Options:
    ----------------------
    Broadcast:            4
    Gather   :            4
    Combine  :            4    
       

**Input.**

::

    Parallel Execution: Process Information
    ==============================================================================
    Rank   Node Name                              NodeID   MyNodeRank  NodeMaster
       0   maginet-ii205                             0          0          0
       1   maginet-ii205                             0          1         -1
       2   maginet-ii205                             0          2         -1
       3   maginet-ii205                             0          3         -1
       4   maginet-ii205                             0          4         -1
       5   maginet-ii205                             0          5         -1
       6   maginet-ii205                             0          6         -1
       7   maginet-ii205                             0          7         -1
       8   maginet-ii210                             1          0          1
       9   maginet-ii210                             1          1         -1
      10   maginet-ii210                             1          2         -1
      11   maginet-ii210                             1          3         -1
      12   maginet-ii210                             1          4         -1
      13   maginet-ii210                             1          5         -1
      14   maginet-ii210                             1          6         -1
      15   maginet-ii210                             1          7         -1
    ==============================================================================
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="process.info">      
       <module cmlx:lineCount="63" cmlx:templateRef="process.info"> 
             <array dataType="xsd:string" size="4" dictRef="cc:nodeName">maginet-ii190 maginet-ii190 maginet-ii190 maginet-ii190</array> 
         </module>        
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="process.info2">     
       <module cmlx:lineCount="63" cmlx:templateRef="process.info"> 
         <array dataType="xsd:string" size="16" dictRef="cc:nodeName">maginet-ii205 maginet-ii205 maginet-ii205 maginet-ii205 maginet-ii205 maginet-ii205 maginet-ii205 maginet-ii205 maginet-ii210 maginet-ii210 maginet-ii210 maginet-ii210 maginet-ii210 maginet-ii210 maginet-ii210 maginet-ii210</array> 
       </module>      
     </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Kid\sNode.*" endPattern="\s*" offset="2" endOffset="0">    <record repeat="*">\s+\S+\s+{A,cc:nodeName}\s+.*</record>
           </template>  <template pattern="\s*={10,}+\s*$\s*Rank.*" endPattern="\s*={10,}+\s*" endPattern2="~" offset="2" endOffset="0">    <record repeat="*">\s+\S+\s+{A,cc:nodeName}\s+.*</record>
           </template>       
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:nodeName']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
