.. _orbitals-d3e38476:

orbitals
========

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
   | *source*                                                                                                                   | Turbomole log                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | orbitals                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Molecular orbitals                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*mo&#92;soccupation.\*                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*number&#92;sof&#92;soccupied&#92;sorbitals.\*                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | orbitals.xml                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

       mo occupation :
      irrep   mo's   occupied
       a      576      135
    
    number of basis functions   :          576
    number of occupied orbitals :          135
       

.. container:: formalpara-title

   **Input**

::

       mo occupation :
      irrep   mo's   occupied
       a      394       79
       b      389       76
    
    number of basis functions   :          783
    number of occupied orbitals :          155
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="orbitals">
          <module cmlx:lineCount="6" cmlx:templateRef="orbitals">
           <list cmlx:lineCount="1" cmlx:templateRef="mooccupation">
            <array dataType="xsd:string" dictRef="t:irrep" size="1">a</array>
            <array dataType="xsd:integer" dictRef="t:numberofmos" size="1">576</array>
            <array dataType="xsd:integer" dictRef="t:occupiedmos" size="1">135</array>
           </list>
           <scalar dataType="xsd:integer" dictRef="t:basisnumber">576</scalar>
           <scalar dataType="xsd:integer" dictRef="t:occupied">135</scalar>
          </module>     
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output2" id="orbitals">
          <module cmlx:lineCount="7" cmlx:templateRef="orbitals">
           <list cmlx:lineCount="2" cmlx:templateRef="mooccupation">
            <array dataType="xsd:string" dictRef="t:irrep" size="2">a b</array>
            <array dataType="xsd:integer" dictRef="t:numberofmos" size="2">394 389</array>
            <array dataType="xsd:integer" dictRef="t:occupiedmos" size="2">79 76</array>
           </list>
           <scalar dataType="xsd:integer" dictRef="t:basisnumber">783</scalar>
           <scalar dataType="xsd:integer" dictRef="t:occupied">155</scalar>
        </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="2" />
   <record id="mooccupation" repeat="*" makeArray="true">{A,t:irrep}{I,t:numberofmos}{I,t:occupiedmos}</record>
   <record repeat="1" />
   <record>\s*number\sof\sbasis\sfunctions\s*:{I,t:basisnumber}</record>
   <record>\s*number\sof\soccupied\sorbitals\s*:{I,t:occupied}</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
