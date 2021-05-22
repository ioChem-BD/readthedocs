.. _finalization-d3e19767:

finalization
============

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
   | *source*                          | GronOR cml                        |
   +-----------------------------------+-----------------------------------+
   | id                                | finalization                      |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | finalization.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Total execution wall clock time on master                 237.217

    Completion of run   21/04/28  16:07:31
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="finalization">
           <module dictRef="cc:finalization">
               <propertyList>
                   <property dictRef="cc:jobdatetime.end">
                       <scalar dataType="xsd:string">21/04/28  16:07:31</scalar>
                   </property>
                   <property dictRef="cc:wallTime">
                       <scalar dataType="xsd:double" units="si:s">237.217</scalar>
                   </property>
               </propertyList>
           </module>
       </comment>

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
