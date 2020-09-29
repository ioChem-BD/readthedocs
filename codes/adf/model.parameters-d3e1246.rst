model.parameters
-------------------------------------- 

.. toctree::
   :maxdepth: 5    
      
   /codes/adf/parameters-d3e1253
   /codes/adf/fragment.files-d3e1382
   /codes/adf/solvation-d3e1673

================

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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | model.parameters                  |
   +-----------------------------------+-----------------------------------+
   | name                              | Model parameters section          |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s+M\sO\sD\sE\sL\s               |
   |                                   | +P\sA\sR\sA\sM\sE\sT\sE\sR\sS\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*$\s*={5,}+\s\*                |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*\*{10,}+\s\*                  |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | offset                            | -1                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | adf/init/mod                      |
   |                                   | elparameters/model.parameters.xml |
   +-----------------------------------+-----------------------------------+

**Comment.**

::

    ===============================
    M O D E L   P A R A M E T E R S
    ===============================

    Fragment File(s)
    ----------------
   ...

    SOLVATION
    -------------------------------------------
   ...
       
       

**Template definition.**

.. code:: xml

   <templateList>  <xi:include href="init/modelparameters/parameters.xml" />  <xi:include href="init/modelparameters/fragment.files.xml" />  <xi:include href="init/modelparameters/solvation.xml" />          
       </templateList>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
