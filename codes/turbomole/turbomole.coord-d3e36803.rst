turbomole.coord
=====================================

.. toctree::
   :maxdepth: 5  

   /codes/turbomole/coord-d3e36808
   /codes/turbomole/restrictions-d3e37158

===============

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
   | *source*                          | Turbomole coord file              |
   +-----------------------------------+-----------------------------------+
   | id                                | turbomole.coord                   |
   +-----------------------------------+-----------------------------------+
   | name                              | Turbomole coord file              |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | topTemplate.xml                   |
   +-----------------------------------+-----------------------------------+

**Template definition.**

.. code:: xml

   <templateList id="init">  <xi:include href="geometry.xml" />  <xi:include href="restrictions.xml" />
       </templateList>
   <transform process="delete" xpath="//node()[count(*)!=0]/text()" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
