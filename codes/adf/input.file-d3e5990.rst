.. _input.file-d3e5990:

input.file
==========

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
   | id                                | input.file                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Input file dump                   |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\(INPUT\sFILE\)\s\*           |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*(End Input|end input|END      |
   |                                   | INPUT|End input)\s\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s*$\s*\*{40,}+\s\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | input.file.xml                    |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   (INPUT FILE)

   create W /usr/local/adf2007.01/atomicdata/ZORA/TZP/W.4d
   xc
   lda vwn
   gradients becke perdew
   end
   relativistic scalar zora
   corepotentials t12rel <++
   W 2
   end
   end input

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="input.file">
         <module cmlx:lineCount="13" cmlx:templateRef="input.file">    
           <scalar dataType="xsd:string" dictRef="cc:inputLine">(INPUT FILE)</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine" />
           <scalar dataType="xsd:string" dictRef="cc:inputLine">create W /usr/local/adf2007.01/atomicdata/ZORA/TZP/W.4d</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">xc</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">lda vwn</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">gradients becke perdew</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">end</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">relativistic scalar zora</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">corepotentials t12rel <++</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">W 2</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">end</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine">end input</scalar>
           <scalar dataType="xsd:string" dictRef="cc:inputLine" />
         </module>   
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="*">{X,cc:inputLine}</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
