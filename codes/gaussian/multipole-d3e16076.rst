.. _multipole-d3e16076:

multipole
=========

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
   | *source*                                                                                                                   | Gaussian log                                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | multipole                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | multipole                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Dipole moment.\*                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | (&#92;s*N&#92;-N=.*)                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | l601/l601.multipole.xml                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    Dipole moment (field-independent basis, Debye):
       X=     0.0000    Y=     0.0000    Z=     0.0000  Tot=     0.0000
    Quadrupole moment (field-independent basis, Debye-Ang):
      XX=    -8.3036   YY=    -8.3036   ZZ=    -8.3036
      XY=     0.0000   XZ=     0.0000   YZ=     0.0000
    Traceless Quadrupole moment (field-independent basis, Debye-Ang):
      XX=     0.0000   YY=     0.0000   ZZ=     0.0000
      XY=     0.0000   XZ=     0.0000   YZ=     0.0000
    Octapole moment (field-independent basis, Debye-Ang**2):
     XXX=     0.0000  YYY=     0.0000  ZZZ=     0.0000  XYY=     0.0000
     XXY=     0.0000  XXZ=     0.0000  XZZ=     0.0000  YZZ=     0.0000
     YYZ=     0.0000  XYZ=    -0.7195
    Hexadecapole moment (field-independent basis, Debye-Ang**3):
    XXXX=   -16.2252 YYYY=   -16.2252 ZZZZ=   -16.2252 XXXY=     0.0000
    XXXZ=     0.0000 YYYX=     0.0000 YYYZ=     0.0000 ZZZX=     0.0000
    ZZZY=     0.0000 XXYY=    -4.9297 XXZZ=    -4.9297 YYZZ=    -4.9297
    XXYZ=     0.0000 YYXZ=     0.0000 ZZXY=     0.0000
     N-N= 1.339525332293D+01 E-N=-1.198300348205D+02  KE= 4.007106437468D+01
     

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="l601.multipole">
       <module cmlx:templateRef="multipole">
         <array dataType="xsd:double" size="3" dictRef="cc:dipole">0.0 0.0 0.0</array>
         <scalar dataType="xsd:double" dictRef="x:dipole">0.0</scalar>
         <array dataType="xsd:double" size="3" dictRef="cc:quadrupole">-8.3036 -8.3036 -8.3036</array>
         <array dataType="xsd:double" size="3" dictRef="cc:quadrupole">0.0 0.0 0.0</array>
         <array dataType="xsd:double" size="6" dictRef="cc:quadrupole">0.0 0.0 0.0 0.0 0.0 0.0</array>
         <array dataType="xsd:double" size="10" dictRef="cc:octapole">0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 0.0 -0.7195</array>
         <array dataType="xsd:double" size="15" dictRef="cc:hexadecapole">-16.2252 -16.2252 -16.2252 0.0 0.0 0.0 0.0 0.0 0.0 -4.9297 -4.9297 -4.9297 0.0 0.0 0.0</array>
       </module>
    </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <record id="dipoletype">\s*Dipole moment \({X,g:dipoletype}\):\s*</record>
   <record id="dipole">\s*X={F,x:d}Y={F,x:d}Z={F,x:d}Tot={F,x:dipole}\s*</record>
   <record id="quadrupoletype">\s*Quadrupole moment \({X,g:quadpoletype}\):\s*</record>
   <record id="quadrupol">\s*XX={F,x:q}YY={F,x:q}ZZ={F,x:q}\s*</record>
   <record id="xy">\s*XY={F,x:qb}XZ={F,x:qb}YZ={F,x:qb}\s*</record>
   <record id="quadrupoletypea">\s*Traceless Quadrupole moment \({X,g:quadpoletype}\):\s*</record>
   <record id="xx">\s*XX={F,x:qq}YY={F,x:qq}ZZ={F,x:qq}\s*</record>
   <record id="xya">\s*XY={F,x:qq}XZ={F,x:qq}YZ={F,x:qq}\s*</record>
   <record id="octapoletype">\s*Octapole moment \({X,g:octapoletype}\):\s*</record>
   <record id="xxx">\s*XXX={F,x:o}YYY={F,x:o}ZZZ={F,x:o}XYY={F,x:o}\s*</record>
   <record id="xxy">\s*XXY={F,x:o}XXZ={F,x:o}XZZ={F,x:o}YZZ={F,x:o}\s*</record>
   <record id="yyz">\s*YYZ={F,x:o}XYZ={F,x:o}\s*</record>
   <record id="hexadecapoletype">\s*Hexadecapole moment \({X,g:hexadecapoletype}\):\s*</record>
   <record id="xxxx">\s*XXXX={F,x:h}YYYY={F,x:h}ZZZZ={F,x:h}XXXY={F,x:h}\s*</record>
   <record id="xxxz">\s*XXXZ={F,x:h}YYYX={F,x:h}YYYZ={F,x:h}ZZZX={F,x:h}\s*</record>
   <record id="zzzy">\s*ZZZY={F,x:h}XXYY={F,x:h}XXZZ={F,x:h}YYZZ={F,x:h}\s*</record>
   <record id="xxyz">\s*XXYZ={F,x:h}YYXZ={F,x:h}ZZXY={F,x:h}\s*</record>
   <record repeat="*" id="xzz" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:d']" dictRef="cc:dipole" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:q']" dictRef="cc:quadrupole" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:qb']" dictRef="cc:quadrupole" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:qq']" dictRef="cc:quadrupole" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:o']" dictRef="cc:octapole" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:h']" dictRef="cc:hexadecapole" />
   <transform process="delete" xpath=".//cml:scalar[contains(@dictRef,'type')]" />
   <transform process="pullup" xpath=".//cml:scalar | .//cml:array" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
