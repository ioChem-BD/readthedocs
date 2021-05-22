.. _program.end-d3e36329:

program.end
===========

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
   | id                                | program.end                       |
   +-----------------------------------+-----------------------------------+
   | name                              | Program end time                  |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*\w\w                          |
   |                                   | \w\w-\w\w-\w\w\s\d\d:\d\d:\d\d.\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | .\*                               |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | program.end.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

           2011-12-16 00:41:13.113
       

.. warning::

   Current template has input comments defined but it's output is
   missing, please notify software developers.

**Template definition.**

.. code:: xml

   <record id="runtime">{X,cc:dateEnd}</record>
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:dateEnd']" format="yyyy-MM-dd HH:mm:ss.SSS" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
