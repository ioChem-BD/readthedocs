.. _entering-d3e6726:

entering
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
   | *source*                          | Gaussian log                      |
   +-----------------------------------+-----------------------------------+
   | id                                | entering                          |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Entering Gaussian             |
   |                                   | System.*Link\s*0=.\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .*Initial command\:.*$.\*         |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 2                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | l0.entering.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Entering Gaussian System, Link 0=/usr/local/gaussian/g03/g03
    Initial command:
    /usr/local/gaussian/g03/l1.exe /tmp/webmo/1/Gau-28330.inp -scrdir=/tmp/webmo/1/
     

**Output text.**

.. code:: xml

   <comment class="example.output" id="entering">
       <module cmlx:templateRef="entering">
         <scalar dataType="xsd:string" dictRef="g:link0">/usr/local/gaussian/g03/g03</scalar>
         <array dataType="xsd:string" size="3" dictRef="g:command">/usr/local/gaussian/g03/l1.exe /tmp/webmo/1/Gau-28330.inp -scrdir=/tmp/webmo/1/</array>
       </module>
     </comment>

**Template definition.**

.. code:: xml

   <record id="enter">\s*Entering Gaussian System,\s*Link 0={X,g:link0}\s*</record>
   <record />
   <record id="command">{1_5A,g:command}</record>
   <transform process="pullup" xpath=".//cml:scalar | .//cml:array" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
