.. _restrictedorbitals-d3e37975:

restrictedorbitals
==================

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
   | *source*                          | Turbomole control file            |
   +-----------------------------------+-----------------------------------+
   | id                                | restrictedorbitals                |
   +-----------------------------------+-----------------------------------+
   | name                              | Restricted orbitals sections      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\u0024closed\sshell.\*        |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\u0024.\*                     |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | orbitals/restricted.xml           |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    $closed shells
    a1      1-57                                   ( 2 )
    a2      1-32                                   ( 2 )
    e       1-84                                   ( 2 )
    $scfiterlimit       40     
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="restrictedorbitals">
          <module cmlx:templateRef="restrictedorbitals">
            <array dataType="xsd:string" dictRef="t:label" size="3">a1 a2 e</array>
            <array dataType="xsd:string" dictRef="t:mosrange" size="3">1-57 1-32 1-84</array>
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="1" />
   <record repeat="*" makeArray="true">{A,t:label}{X,t:mosrange}\(.*\).*</record>
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
