.. _symmetry-d3e34262:

symmetry
========

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
   | id                                | symmetry                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Symmetry information              |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*symm                          |
   |                                   | etry\sgroup\sof\sthe\smolecule.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s                               |
   |                                   | *maximum\snumber\sof\sshells\swhi |
   |                                   | ch\sare\srelated\sby\ssymmetry.\* |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | symmetry.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        symmetry group of the molecule :   d5h
       
        the group has the following generators :
          c5(z)
          c2(x)
          mirror plane sigma(xy)
       
          20 symmetry operations found
       
        there are 8 real representations :   a1'  a2'  e1'  e2'  a1"  a2"  e1"  e2" 
       
        maximum number of shells which are related by symmetry : 10
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="symmetry">    
           <module cmlx:lineCount="8" cmlx:templateRef="symmetry">
             <scalar dataType="xsd:string" dictRef="t:symmetryGroup">d5h</scalar>
             <list cmlx:lineCount="3" cmlx:templateRef="generators">
               <scalar dataType="xsd:string" dictRef="t:generators">c5(z)</scalar>
               <scalar dataType="xsd:string" dictRef="t:generators">c2(x)</scalar>
               <scalar dataType="xsd:string" dictRef="t:generators">mirror plane sigma(xy)</scalar>
             </list>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*symmetry\sgroup\sof\sthe\smolecule\s:{X,t:symmetryGroup}</record>
   <record repeat="2" />
   <templateList>  <template id="generators" pattern="\s*\S+\s*" endPattern="\s*">    <record repeat="*">\s*{X,t:generators}\s*</record>   
           </template>   
       </templateList>
   <record repeat="*" />
   <transform process="createList" xpath=".//cml:module[@cmlx:templateRef='generators']" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
