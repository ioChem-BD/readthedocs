.. _total.time-d3e25789:

total.time
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
   | *source*                          | MOPAC log                         |
   +-----------------------------------+-----------------------------------+
   | id                                | total.time                        |
   +-----------------------------------+-----------------------------------+
   | name                              | Total job time                    |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*TOTAL\sJOB\sTIME:.\*          |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | job/time.xml                      |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    TOTAL JOB TIME:         24928.18 SECONDS

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="total.time">
           <module cmlx:templateRef="total.time">
               <scalar dataType="xsd:double" dictRef="cc:elapsedtime" units="si:s">24928.18</scalar>
           </module>
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*TOTAL\sJOB\sTIME:\s*{F,cc:elapsedtime}SECONDS</record>
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='cc:elapsedtime']" value="si:s" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
