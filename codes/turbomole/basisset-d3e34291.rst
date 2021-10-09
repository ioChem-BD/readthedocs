.. _basisset-d3e34291:

basisset
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
   | id                                | basisset                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Basis set information section     |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s                               |
   |                                   | *\+\-+\+\s*$\s*\|\s*basis\sset\si |
   |                                   | nformation\s*\|\s*$\s*\+\-+\+\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*total\snu                     |
   |                                   | mber\sof\sSCF-basis\sfunctions.\* |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | basisset.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

                 +--------------------------------------------------+
                 |               basis set information              |
                 +--------------------------------------------------+


                 we will work with the  1s 3p 5d  7f  9g ... basis set
                 ...i.e. with spherical basis functions...


      type   atoms  prim   cont   basis
      ---------------------------------------------------------------------------
       c       82     25     15   DZP   [4s2p1d|8s4p1d]
       sc       2     92     45   def2-TZVP   [6s4p4d1f|17s11p7d1f]
      ---------------------------------------------------------------------------
      total:   84   2234   1320
      ---------------------------------------------------------------------------

      total number of primitive shells          :   49
      total number of contracted shells         :  604
      total number of cartesian basis functions : 1416
      total number of SCF-basis functions       : 1320 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="basisset">
           <module cmlx:lineCount="20" cmlx:templateRef="basisset">
               <list cmlx:lineCount="2" cmlx:templateRef="basis">
                  <array dataType="xsd:string" dictRef="cc:atomType" size="2">c sc</array>
                  <array dataType="xsd:integer" dictRef="t:atoms" size="2">82 2</array>
                  <array dataType="xsd:integer" dictRef="t:prim" size="2">25 92</array>
                  <array dataType="xsd:integer" dictRef="t:cont" size="2">15 45</array>
                  <array dataType="xsd:string" dictRef="t:basis" size="2">DZP def2-TZVP</array>
                  <array dataType="xsd:string" dictRef="t:contraction" size="2">[4s2p1d|8s4p1d] [6s4p4d1f|17s11p7d1f]</array>
               </list>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template pattern="\s*type\s*atoms.*" endPattern="\s*total.*" endOffset="0">    <record repeat="2" />    <record repeat="*" makeArray="true" id="basis">{A,cc:atomType}{I,t:atoms}{I,t:prim}{I,t:cont}{A,t:basis}{A,t:contraction}</record>    <record repeat="1" />            
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='basis']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
