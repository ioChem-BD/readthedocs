.. _geometry-d3e25153:

geometry
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
   | *source*                          | MOPAC log                         |
   +-----------------------------------+-----------------------------------+
   | id                                | geometry                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Cartesian Coordinates             |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*CARTESIAN\sCOORDINATES.\*     |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Empirical\s*Formula.\*        |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*$\s*$\s\*                     |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | atomiccoordinates.xml             |
   +-----------------------------------+-----------------------------------+

**Input.**

::

                                CARTESIAN COORDINATES

      1    C       -4.374598305     2.688732629     1.251130091
      2    C       -5.092724453     3.683249302     0.425878871
      3    C       -6.471282903     3.691879674     0.356170876
      4    C       -7.330541146     2.837499652     1.233383342
      5    C       -6.546466024     1.752175053     2.134695421
      6    C       -5.058520354     1.736674464     1.980132375
      7    C       -3.146588734     2.345471392     0.555689153
      8    C       -2.967412654     3.247627856    -0.624015350
      9    C       -4.291530172     3.929989962    -0.760299282
   ...

              Empirical Formula: C510 H498 N66 O172  =  1246 atoms
       

**Input.**

::

             CARTESIAN COORDINATES 

       NO.       ATOM         X         Y         Z

        1         C       -4.1918    2.5617    1.3518
        2         C       -4.8544    3.5730    0.5005
        3         C       -6.2295    3.6275    0.3952
        4         C       -7.1393    2.8094    1.2560
        5         C       -6.4160    1.7058    2.1856
        6         C       -4.9260    1.6393    2.0699
        7         C       -2.9585    2.1717    0.6912
        8         C       -2.7186    3.0577   -0.4900
        9         C       -4.0147    3.7838   -0.6656
   ...


       

**Output text.**

.. code:: xml

   <comment class="example.output" id="geometry">
         <module cmlx:templateRef="geometry">
             <molecule id="molecule">
                <atomArray>
                   <atom elementType="C" id="a1" x3="0.3745983" y3="2.68873263" z3="1.25113009">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">1</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-4</scalar>
                   </atom>
                   <atom elementType="C" id="a2" x3="0.09272445" y3="3.6832493" z3="0.42587887">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">2</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-5</scalar>
                   </atom>
                   <atom elementType="C" id="a3" x3="0.4712829" y3="3.69187967" z3="0.35617088">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">3</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-6</scalar>
                   </atom>
                   <atom elementType="C" id="a4" x3="0.33054115" y3="2.83749965" z3="1.23338334">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">4</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-7</scalar>
                   </atom>
                   <atom elementType="C" id="a5" x3="0.54646602" y3="1.75217505" z3="2.13469542">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">5</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-6</scalar>
                   </atom>
                   <atom elementType="C" id="a6" x3="0.05852035" y3="1.73667446" z3="1.98013238">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">6</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-5</scalar>
                   </atom>
                   <atom elementType="C" id="a7" x3="0.14658873" y3="2.34547139" z3="0.55568915">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">7</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-3</scalar>
                   </atom>
                   <atom elementType="C" id="a8" x3="0.96741265" y3="3.24762786" z3="-0.62401535">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">8</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-2</scalar>
                   </atom>
                   <atom elementType="C" id="a9" x3="0.29153017" y3="3.92998996" z3="-0.76029928">
                      <scalar dataType="xsd:integer" dictRef="cc:serial">9</scalar>
                      <scalar dataType="xsd:integer" dictRef="g:atomicType">-4</scalar>
                   </atom>
                 </atomArray>
           </molecule>     
         </module>
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="*">((?!\s*1).*)</record>
   <record name="molecule" repeat="*">{I,cc:serial}{A,cc:elementType}{F,cc:x3}\*?{F,cc:y3}\*?{F,cc:z3}</record>
   <transform process="delete" xpath="//cml:list[child::cml:scalar[@dictRef='cc:elementType' and text() = 'Tv']]" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:serial']" dictRef="cc:serial" dataType="xsd:integer" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:elementType']" dictRef="cc:elementType" dataType="xsd:string" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:x3']" dictRef="cc:x3" dataType="xsd:double" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:y3']" dictRef="cc:y3" dataType="xsd:double" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:z3']" dictRef="cc:z3" dataType="xsd:double" />
   <transform process="createMolecule" xpath=".//cml:list/cml:array" id="molecule" />
   <transform process="pullup" xpath=".//cml:molecule" repeat="2" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:molecule//cml:scalar[@dictRef='cc:serial']" />
   <transform process="delete" xpath=".//cml:molecule//cml:scalar[@dictRef='cc:atomicNumber']" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
