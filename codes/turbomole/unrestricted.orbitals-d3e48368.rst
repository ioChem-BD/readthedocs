.. _unrestricted.orbitals-d3e48368:

unrestricted.orbitals
=====================

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
   | id                                                                                                                         | unrestricted.orbitals                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Molecular orbitals (unrestricted)                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*orbitals.*alpha&#92;s*will&#92;sbe&#92;swritten&#92;sto&#92;sfile.\*                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | molecularorbitals/unrestricted.orbitals.xml                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    
    orbitals $uhfmo_beta  will be written to file beta

    orbitals $uhfmo_alpha  will be written to file alpha
    
    alpha: 

       irrep                 63a         64a         65a         66a         67a   
    eigenvalues H         -0.49206    -0.47710    -0.47522    -0.46259    -0.31546
               eV         -13.3897    -12.9827    -12.9315    -12.5879     -8.5841
    occupation              1.0000      1.0000      1.0000      1.0000      1.0000 

       irrep                 68a         69a         70a         71a         72a   
    eigenvalues H         -0.25890    -0.23783    -0.23147    -0.22590    -0.20882
               eV          -7.0451     -6.4718     -6.2987     -6.1471     -5.6825

       irrep                 60b         61b         62b         63b         64b   
    eigenvalues H         -0.52996    -0.52637    -0.51482    -0.50284    -0.46411
               eV         -14.4209    -14.3233    -14.0092    -13.6830    -12.6291
    occupation              1.0000      1.0000      1.0000      1.0000      1.0000 

       irrep                 65b         66b         67b         68b         69b   
    eigenvalues H         -0.30300    -0.29055    -0.26751    -0.24147    -0.23338
               eV          -8.2451     -7.9064     -7.2794     -6.5707     -6.3506
    
    beta:  

       irrep                 62a         63a         64a         65a         66a   
    eigenvalues H         -0.51352    -0.49114    -0.46482    -0.45774    -0.45288
               eV         -13.9738    -13.3647    -12.6486    -12.4559    -12.3237
    occupation              1.0000      1.0000      1.0000      1.0000      1.0000 

       irrep                 67a         68a         69a         70a         71a   
    eigenvalues H         -0.26560    -0.25724    -0.23314    -0.22690    -0.21424
               eV          -7.2275     -6.9999     -6.3441     -6.1743     -5.8299

       irrep                 59b         60b         61b         62b         63b   
    eigenvalues H         -0.53728    -0.51864    -0.51707    -0.50687    -0.45798
               eV         -14.6202    -14.1131    -14.0702    -13.7928    -12.4623
    occupation              1.0000      1.0000      1.0000      1.0000      1.0000 

       irrep                 64b         65b         66b         67b         68b   
    eigenvalues H         -0.36363    -0.29633    -0.26535    -0.26378    -0.23723
               eV          -9.8950     -8.0635     -7.2206     -7.1778     -6.4555
                                                 

       

.. warning::

   Current template has input comments defined but it's output is missing, please notify software developers.

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="unrestricted.orbitals.alpha" pattern="\s*alpha.*" endPattern="\s*beta.*" endOffset="0">    <templateList>      <xi:include href="orbital.line.xml" />
               </templateList>    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='cc:irrep']" />    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='t:eigen']" />    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='t:orbitalenergy']" />    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='cc:occupation']" />    <transform process="pullup" xpath=".//cml:array" repeat="3" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:module[count(*)=0]" />    <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="t:spin" value="alpha" />
               
           </template>  <template id="unrestricted.orbitals.beta" pattern="\s*beta.*" endPattern="~">    <templateList>      <xi:include href="orbital.line.xml" />
               </templateList>    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='cc:irrep']" />    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='t:eigen']" />    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='t:orbitalenergy']" />    <transform process="joinArrays" xpath="." from=".//cml:array[@dictRef='cc:occupation']" />    <transform process="pullup" xpath=".//cml:array" repeat="3" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:module[count(*)=0]" />    <transform process="addChild" xpath="." elementName="cml:scalar" dictRef="t:spin" value="beta" />
           </template>
       </templateList>
   <transform process="addUnits" xpath=".//cml:array[@dictRef='t:orbitalenergy']" value="nonsi:electronvolt" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
