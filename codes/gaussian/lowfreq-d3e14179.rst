.. _lowfreq-d3e14179:

lowfreq
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
   | *source*                          | Gaussian log                      |
   +-----------------------------------+-----------------------------------+
   | id                                | lowfreq                           |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\sLow frequencies.\*             |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | l716.lowfreq.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Low frequencies ---    0.0018    0.0024    0.0026    6.3218    7.5564   17.5412
    Low frequencies ---   55.1764   72.8335  137.6925
     

**Output text.**

.. code:: xml

   <comment class="example.output" id="l716.lowfreq">
       <module cmlx:templateRef="lowfreq">
         <array dataType="xsd:double" size="9" dictRef="g:1716.lowfreq" cmlx:templateRef="lowfreq">0.0018 0.0024 0.0026 6.3218 7.5564 17.5412 55.1764 72.8335 137.6925</array>
       </module>
     </comment>

**Template definition.**

.. code:: xml

   <record id="lowfreq" repeat="*">\sLow frequencies\s\-\-\-{1_6F,g:1716.lowfreq}</record>
   <transform process="joinArrays" xpath="./cml:list/cml:array" />
   <transform process="pullupSingleton" xpath="./cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
