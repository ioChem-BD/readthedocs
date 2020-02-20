.. _kpoints-d3e30811:

kpoints
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
   | id                                | kpoints                           |
   +-----------------------------------+-----------------------------------+
   | name                              | kpoints                           |
   +-----------------------------------+-----------------------------------+
   | pattern                           | ^\s+number of k points=.\*        |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s{1,4}\S+.\*                |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*$\s*Dense\s*grid.\*           |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | kpoints.xml                       |
   +-----------------------------------+-----------------------------------+

**Input.**

::

        number of k points=     4  gaussian smearing, width (Ry)=  0.0200
                          cart. coord. in units 2pi/alat
           k(    1) = (   0.0000000   0.0000000   0.0000000), wk =   0.2500000
           k(    2) = (   0.0000000  -0.5773503   0.0000000), wk =   0.2500000
           k(    3) = (   0.5000000  -0.2886751   0.0000000), wk =   0.2500000
           k(    4) = (  -0.5000000  -0.2886751   0.0000000), wk =   0.2500000

                          cryst. coord.
           k(    1) = (   0.0000000   0.0000000   0.0000000), wk =   0.2500000
           k(    2) = (   0.0000000  -0.5000000   0.0000000), wk =   0.2500000
           k(    3) = (   0.5000000  -0.5000000   0.0000000), wk =   0.2500000
           k(    4) = (  -0.5000000   0.0000000   0.0000000), wk =   0.2500000

        Dense  grid:  1711295 G-vectors     FFT dimensions: ( 120, 120, 320)
        
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="kpoints">         
           <module cmlx:templateRef="kpoints">
               <matrix cols="3" dataType="xsd:double" dictRef="qex:kpointlist.cartesian" rows="4">0.0000000 0.0000000 0.0000000 0.0000000 -0.5773503 0.0000000 0.5000000 -0.2886751 0.0000000 -0.5000000 -0.2886751 0.0000000</matrix>
               <matrix cols="3" dataType="xsd:double" dictRef="qex:kpointlist" rows="4">0.0000000 0.0000000 0.0000000 0.0000000 -0.5000000 0.0000000 0.5000000 -0.5000000 0.0000000 -0.5000000 0.0000000 0.0000000</matrix>
               <array dataType="xsd:double" dictRef="qex:kpointweight" size="4">0.2500000 0.2500000 0.2500000 0.2500000</array>
           </module>     
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="2" />
   <record id="kpoints.cartesian" repeat="*">\s*k\({I,cc:serial}\)\s=\s\({3F,x:coords}\),\s*wk\s*={F,qex:kpointweight}</record>
   <record repeat="2" />
   <record id="kpoints.crystal" repeat="*">\s*k\({I,cc:serial}\)\s=\s\({3F,x:coords}\),\s*wk\s*={F,qex:kpointweight}</record>
   <transform process="createMatrix" xpath="." from=".//cml:list[@cmlx:templateRef='kpoints.cartesian']/cml:list/cml:array" dictRef="qex:kpointlist.cartesian" />
   <transform process="createMatrix" xpath="." from=".//cml:list[@cmlx:templateRef='kpoints.crystal']/cml:list/cml:array" dictRef="qex:kpointlist" />
   <transform process="createArray" xpath="." from=".//cml:list[@cmlx:templateRef='kpoints.crystal']/cml:list/cml:scalar[@dictRef='qex:kpointweight']" />
   <transform process="pullup" xpath=".//cml:matrix" repeat="2" />
   <transform process="pullup" xpath=".//cml:array" repeat="2" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='cc:serial']" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='qex:kpointweight']" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />
   <transform process="delete" xpath=".//cml:list[count(*) = 0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
