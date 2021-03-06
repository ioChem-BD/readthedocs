.. _jobcpu-d3e18437:

jobcpu
======

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
   | id                                | jobcpu                            |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*Job cpu time:.\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Normal termination.\*         |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | jobcpu.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    Job cpu time:  0 days  0 hours  0 minutes 12.7 seconds.
    File lengths (MBytes):  RWF=     12 Int=      0 D2E=      0 Chk=      7 Scr=      1
    Normal termination of Gaussian 03 at Mon Nov 20 14:40:36 2006.
     

**Output text.**

.. code:: xml

   <comment class="example.output" id="jobcpu">
       <module cmlx:templateRef="jobcpu">
         <scalar dictRef="cc:jobtime" dataType="xsd:string">PT12.700S</scalar>
         <scalar dataType="xsd:date" dictRef="cc:jobdatetime.end">2006-11-20T14:40:36Z</scalar>
         <scalar dataType="xsd:string" dictRef="cc:program">Gaussian 03</scalar>
       </module>
     </comment>

**Template definition.**

.. code:: xml

   <record id="jobcpu">\s*Job cpu time:\s*{X,cc:jobtime}</record>
   <record id="files" />
   <record id="date">\s*Normal termination of {X,cc:program} at {X,cc:jobdatetime.end}\.\s*</record>
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:jobtime']" format="DHMS" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:jobdatetime.end']" format="EEE MMM d HH:mm:ss yyyy" />
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:jobdatetime.end']" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:program']" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
