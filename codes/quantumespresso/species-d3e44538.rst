.. _species-d3e44538:

species
=======

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
   | id                                                                                                                         | species                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Atomic species                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | ^&#92;s*atomic&#92;s+species.\*                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | initialization/atomic-species.xml                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

        atomic species   valence    mass     pseudopotential
           Fe1           16.00    55.84500     Fe( 1.00)
           Fe2           16.00    55.84500     Fe( 1.00)
           O              6.00    15.99990     O ( 1.00)
           H              1.00     1.00790     H ( 1.00)
           
      

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="species">
       <module cmlx:templateRef="species">
           <list cmlx:templateRef="species">
               <array dataType="xsd:string" dictRef="qex:specie" size="4">Fe1 Fe2 O H</array>
               <array dataType="xsd:double" dictRef="x:valelectrons" size="4">16.00 16.00 6.00 1.00</array>
               <array dataType="xsd:double" dictRef="cc:mass" size="4">55.84500 55.84500 15.99990 1.00790</array>
               <array dataType="xsd:string" dictRef="cc:elementType" size="4">Fe Fe O H</array>
               <array dataType="xsd:double" dictRef="qex:pseudopot" size="4">1.00 1.00 1.00 1.00</array>
           </list>
           <map id="speciesToAtomTypeMap">
               <link from="Fe1" to="Fe" />
               <link from="Fe2" to="Fe" />
               <link from="O" to="O" />
               <link from="H" to="H" />
           </map>        
       </module>
      </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <record repeat="1" />
   <record id="species" repeat="*">{A,qex:specie}{F,x:valelectrons}{F,cc:mass}{A,cc:elementType}\({F,qex:pseudopot}\).*</record>
   <transform process="addMap" xpath="." id="speciesToAtomTypeMap" from=".//cml:scalar[@dictRef='qex:specie']" to=".//cml:scalar[@dictRef='cc:elementType']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='qex:specie']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:valelectrons']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:mass']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:elementType']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='qex:pseudopot']" />
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
