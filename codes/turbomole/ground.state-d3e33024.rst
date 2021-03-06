.. _ground.state-d3e33024:

ground.state
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
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | ground.state                      |
   +-----------------------------------+-----------------------------------+
   | name                              | Ground state                      |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Ground\sstate.\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\sTotal\senergy.\*               |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | ground.state.xml                  |
   +-----------------------------------+-----------------------------------+

**Input.**

::

                                   Ground state


    Total energy:                           -2746.335418094000 
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="ground.state">
           <module cmlx:lineCount="4" cmlx:templateRef="ground.state">
               <scalar dataType="xsd:double" dictRef="t:groundenergy">-2746.335418094</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="3" />
   <record id="energy">\s*Total\senergy:{F,t:groundenergy}</record>
   <transform process="pullup" repeat="1" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
