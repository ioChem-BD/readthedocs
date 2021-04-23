.. _unrestrictedorbitals-d3e38004:

unrestrictedorbitals
====================

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
   | id                                | unrestrictedorbitals              |
   +-----------------------------------+-----------------------------------+
   | name                              | Unrestricted orbitals sections    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\u0024(alpha|beta)\sshells.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\u0024.\*                     |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | orbitals/unrestricted.xml         |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    $alpha shells
    a1      1-57                                   ( 1 )
    a2      1-32                                   ( 1 )
    e       1-84                                   ( 1 )
    $beta shells   
       

**Input.**

::

    $beta shells
    a1      1-57                                   ( 1 )
    a2      1-32                                   ( 1 )
    e       1-84                                   ( 1 )
    $scfiterlimit       50     
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="unrestrictedorbitals">
        <module cmlx:templateRef="unrestrictedorbitals">
            <scalar dataType="xsd:string" dictRef="t:spintype">alpha</scalar>
            <array dataType="xsd:string" dictRef="t:label" size="3">a1 a2 e</array>
            <array dataType="xsd:string" dictRef="t:mosrange" size="3">1-57 1-32 1-84</array>
         </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="unrestrictedorbitals2">   
         <module cmlx:templateRef="unrestrictedorbitals">
            <scalar dataType="xsd:string" dictRef="t:spintype">beta</scalar>
            <array dataType="xsd:string" dictRef="t:label" size="3">a1 a2 e</array>
            <array dataType="xsd:string" dictRef="t:mosrange" size="3">1-57 1-32 1-84</array>
         </module>   
       </comment>

**Template definition.**

.. code:: xml

   <record id="spinType">\s*\u0024{A,t:spintype}\sshells.*</record>
   <record repeat="*" makeArray="true">{A,t:label}{X,t:mosrange}\(.*\).*</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
