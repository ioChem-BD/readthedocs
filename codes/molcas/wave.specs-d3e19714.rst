.. _wave.specs-d3e19714:

wave.specs
==========

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
   | id                                | wave.specs                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Wave function specifications      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | .*W                               |
   |                                   | ave\sfunction\sspecifications:.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\-\-\s\*                      |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*$((?!Number).)\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/wave.specs.xml            |
   +-----------------------------------+-----------------------------------+

**Input.**

::

      
   ++       Wave function specifications:
         Wave function specifications:
         -----------------------------

         Number of closed shell electrons          14
         Number of electrons in active shells       4
         Max number of holes in RAS1 space          0
         Max nr of electrons in RAS3 space          0
         Number of inactive orbitals                7
         Number of active orbitals                  4
         Number of secondary orbitals             105
         Spin quantum number                      0.0
         State symmetry                             1

   --
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="wave.specs">
            <module cmlx:templateRef="wave.specs">
               <scalar dataType="xsd:integer" dictRef="m:closedelec">14</scalar>
               <scalar dataType="xsd:integer" dictRef="m:activeelec">4</scalar>
               <scalar dataType="xsd:integer" dictRef="m:ras1holes">0</scalar>
               <scalar dataType="xsd:integer" dictRef="m:ras3holes">0</scalar>
               <scalar dataType="xsd:integer" dictRef="m:inactiveorbitals">7</scalar>
               <scalar dataType="xsd:integer" dictRef="m:activeorbitals">4</scalar>
               <scalar dataType="xsd:integer" dictRef="m:secondaryorbitals">105</scalar>
               <scalar dataType="xsd:double" dictRef="m:spinquantumnum">0.0</scalar>
               <scalar dataType="xsd:integer" dictRef="m:statesymm">1</scalar>
            </module>    
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*Number\sof\sclosed\sshell\selectrons.*" endPattern=".*" endPattern2="~">    <record>\s*Number\sof\sclosed\sshell\selectrons{I,m:closedelec}</record>
           </template>  <template pattern="\s*Number\sof\selectrons\sin\sactive\sshells.*" endPattern=".*" endPattern2="~">    <record>\s*Number\sof\selectrons\sin\sactive\sshells{I,m:activeelec}</record>
           </template>  <template pattern="\s*Max\snumber\sof\sholes\sin\sRAS1\sspace.*" endPattern=".*" endPattern2="~">    <record>\s*Max\snumber\sof\sholes\sin\sRAS1\sspace{I,m:ras1holes}</record>
           </template>  <template pattern="\s*Max\s(nr|number)\sof\selectrons\sin\sRAS3\sspace.*" endPattern=".*" endPattern2="~">    <record>\s*Max\s(nr|number)\sof\selectrons\sin\sRAS3\sspace{I,m:ras3holes}</record>
           </template>  <template pattern="\s*Number\sof\sinactive\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Number\sof\sinactive\sorbitals{I,m:inactiveorbitals}</record>
           </template>  <template pattern="\s*Number\sof\sactive\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Number\sof\sactive\sorbitals{I,m:activeorbitals}</record>
           </template>  <template pattern="\s*Number\sof\ssecondary\sorbitals.*" endPattern=".*" endPattern2="~">    <record>\s*Number\sof\ssecondary\sorbitals{I,m:secondaryorbitals}</record>        
           </template>  <template pattern="\s*Spin\squantum\snumber.*" endPattern=".*" endPattern2="~">    <record>\s*Spin\squantum\snumber{F,m:spinquantumnum}</record>       
           </template>  <template pattern="\s*State\ssymmetry.*" endPattern=".*" endPattern2="~">    <record>\s*State\ssymmetry{I,m:statesymm}</record>        
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" repeat="2" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
