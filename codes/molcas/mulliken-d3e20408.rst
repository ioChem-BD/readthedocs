.. _mulliken-d3e20408:

mulliken
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
   | *source*                          | MOLCAS log                        |
   +-----------------------------------+-----------------------------------+
   | id                                | mulliken                          |
   +-----------------------------------+-----------------------------------+
   | name                              | Mulliken section                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Mulliken\                     |
   |                                   | s(spin\s)?population\sAnalysis.\* |
   +-----------------------------------+-----------------------------------+
   | pattern2                          | \\s*Mulliken\scharges\sper\scent  |
   |                                   | er\sand\sbasis\sfunction\stype.\* |
   +-----------------------------------+-----------------------------------+
   | pattern3                          | \\s*Mulliken\scharges\sper\scentr |
   |                                   | e\sand\sbasis\sfunction\stype\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Total                         |
   |                                   | .*[a-zA-Z].*$.*$\s*((?!Total).)\* |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*\-\-\s\*                      |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | modules/mulliken/mulliken.xml     |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

         Mulliken spin population Analysis for root number: 1
         ---------------------------------------------------
               
         
         Mulliken spin population per center and basis function type
         ---------------------------------------------------
    
                  NI      O1      O2      O3      N1      N2      N3      N4      H1      H2      H3      H4  
         1s     0.0000  0.0000  0.0000  0.0000  0.0000  0.0000  0.0000  0.0000  0.0007  0.0008  0.0001  0.0001
         2s     0.0000  0.0039  0.0004  0.0004  0.0016  0.0076  0.0023  0.0038 -0.0001 -0.0001 -0.0001  0.0000
         2px    0.0000  0.0000  0.0006  0.0009  0.0053  0.0102  0.0000  0.0000  0.0000  0.0000  0.0000  0.0000 
         ...
         Total electronic spin=    2.000000
       

**Comment.**

::

         Mulliken population Analysis for root number: 1
         -----------------------------------------------
    
    
         Mulliken charges per center and basis function type
         ---------------------------------------------------
       
                  NI      O1      O2      O3      N1      N2      N3      N4      H1      H2      H3      H4  
         1s     2.0000  1.9999  1.9999  1.9999  1.9995  1.9997  1.9994  1.9995  0.4561  0.4383  0.4917  0.4675
         2s     2.0000  1.7951  1.7842  1.7536  1.5053  1.6854  1.4693  1.5481  0.1113  0.0864  0.1101  0.0884
         2px    2.0000  1.3616  1.9376  1.9929  1.7571  1.5823  1.2592  1.2697  0.0000  0.0000  0.0000  0.0000
         2pz    2.0000  2.0015  1.3465  1.3185  1.2384  1.2549  1.7401  1.6762  0.0000  0.0000  0.0000  0.0000
         2py    2.0000  1.7052  1.7718  1.7470  1.2960  1.3519  1.2639  1.2803  0.0000  0.0000  0.0000  0.0000
         3s     1.9995 -0.0248 -0.0138 -0.0137 -0.0224 -0.0252 -0.0178 -0.0191  0.0000  0.0000  0.0000  0.0000
         3px    1.9987 -0.0217 -0.0019 -0.0024  0.0130  0.0167 -0.0034  0.0018  0.0000  0.0000  0.0000  0.0000
         ...
         Total electronic charge=   96.000000
    
         Total            charge=    2.000000
       

**Template definition.**

.. code:: xml

   <xi:include href="mulliken.header.xml" />
   <xi:include href="mulliken.charges.xml" />
   <xi:include href="mulliken.spin.xml" />
   <transform process="addChild" xpath="." elementName="cml:module" dictRef="mulliken.header" />
   <transform process="addAttribute" xpath=".//cml:module[@dictRef='mulliken.header']" name="cmlx:templateRef" value="mulliken.header" />
   <transform process="addChild" id="root" xpath="./cml:module[@dictRef='mulliken.header' and count(*) = 0]" elementName="cml:scalar" dictRef="m:rootnumber" value="$string((preceding::cml:module[@cmlx:templateRef='caspt2.root'])[last()]//cml:scalar/text())" />
   <transform process="delete" xpath=".//cml:scalar[@dictRef='m:rootnumber' and not(text())]/parent::cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
