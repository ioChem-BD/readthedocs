.. _lattice-d3e31908:

lattice
=======

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
   | *source*                          | QuantumEspresso log               |
   +-----------------------------------+-----------------------------------+
   | id                                | lattice                           |
   +-----------------------------------+-----------------------------------+
   | name                              | Lattice                           |
   +-----------------------------------+-----------------------------------+
   | pattern                           | ^\s*celldm.\*                     |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*b\(3\).\*                     |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | initialization/lattice.xml        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        celldm(1)=  19.332654  celldm(2)=   1.000000  celldm(3)=   2.829039
        celldm(4)=   0.000000  celldm(5)=   0.000000  celldm(6)=  -0.500000

        crystal axes: (cart. coord. in units of alat)
                  a(1) = (   1.000000   0.000000   0.000000 )  
                  a(2) = (  -0.500000   0.866025   0.000000 )  
                  a(3) = (   0.000000   0.000000   2.829039 )  

        reciprocal axes: (cart. coord. in units 2 pi/alat)
                  b(1) = (  1.000000  0.577350  0.000000 )  
                  b(2) = (  0.000000  1.154701  0.000000 )  
                  b(3) = (  0.000000  0.000000  0.353477 )        
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="lattice">
           <module cmlx:templateRef="lattice">                    
                <array dataType="xsd:string" dictRef="cc:lattice" size="3" units="nonsi:angstrom">10.230478 0.000000 0.000000</array>
                <array dataType="xsd:string" dictRef="cc:lattice" size="3" units="nonsi:angstrom">-5.115239 8.859850 0.000000</array>
                <array dataType="xsd:string" dictRef="cc:lattice" size="3" units="nonsi:angstrom">0.000000 0.000000 28.942422</array>       
          </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="*">\s*celldm.*</record>
   <record repeat="2" />
   <record id="lattice" repeat="3">\s*a\(.*\)\s=\s\({1_3X,cc:lattice}\).*</record>
   <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:lattice']" args="operator=multiply operand=$number(//cml:scalar[@dictRef='cc:parameter' and starts-with(text(), 'lattice parameter')]/following-sibling::cml:scalar[@dictRef='cc:value']) format=####0.000000" />
   <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:lattice']" value="nonsi:angstrom" />
   <transform process="pullup" xpath=".//cml:array[@dictRef='cc:lattice']" repeat="1" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
