orbitalenergies
-------------------------------------- 

.. toctree::
   :maxdepth: 5    
      
   /codes/turbomole/restricted.orbitals-d3e48242
   /codes/turbomole/unrestricted.orbitals-d3e48368

===============

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
   | id                                                                                                                         | orbitalenergies                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Molecular orbitals                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*orbitals.*will&#92;sbe&#92;swritten&#92;sto&#92;sfile.\*                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*IRREP.*|&#92;s*&#92;=+.*|&#92;s*&#92;WS&#92;*S&#92;W.\*                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s*$&#92;s*$&#92;s\*                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | molecularorbitals/molecular.orbitals.xml                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Comment**

::

    orbitals $scfmo  will be written to file mos

       irrep                 18ag        19ag        20ag        21ag        22ag  
    eigenvalues H         -0.59748    -0.57961    -0.54752    -0.54279    -0.45030
               eV         -16.2584    -15.7721    -14.8988    -14.7703    -12.2535
    occupation              2.0000      2.0000      2.0000      2.0000      2.0000 

       irrep                 23ag        24ag        25ag        26ag        27ag  
    eigenvalues H         -0.24507    -0.23232    -0.17908    -0.13662    -0.11917
               eV          -6.6687     -6.3217     -4.8729     -3.7178     -3.2427
   ...
       

.. container:: formalpara-title

   **Comment**

::

    
    orbitals $uhfmo_beta  will be written to file beta

    orbitals $uhfmo_alpha  will be written to file alpha
    
    alpha: 

       irrep                 63a         64a         65a         66a         67a   
    eigenvalues H         -0.49206    -0.47710    -0.47522    -0.46259    -0.31546
               eV         -13.3897    -12.9827    -12.9315    -12.5879     -8.5841
    occupation              1.0000      1.0000      1.0000      1.0000      1.0000 

   ... 
    
    beta:  

       irrep                 62a         63a         64a         65a         66a   
    eigenvalues H         -0.51352    -0.49114    -0.46482    -0.45774    -0.45288
               eV         -13.9738    -13.3647    -12.6486    -12.4559    -12.3237
    occupation              1.0000      1.0000      1.0000      1.0000      1.0000 

   ...
       

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <xi:include href="molecularorbitals/restricted.orbitals.xml" />  <xi:include href="molecularorbitals/unrestricted.orbitals.xml" />
       </templateList>
   <transform process="pullup" xpath="./cml:module/cml:module" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
