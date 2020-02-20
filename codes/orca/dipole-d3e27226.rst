.. _dipole-d3e27226:

dipole
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
   | *source*                          | Orca log                          |
   +-----------------------------------+-----------------------------------+
   | id                                | dipole                            |
   +-----------------------------------+-----------------------------------+
   | name                              | Dipole moment                     |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*-+\                           |
   |                                   | s*$\s*DIPOLE\sMOMENT\s*$\s*-+\s\* |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*Magnitude.*$\s\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | dipole.xml                        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   -------------
   DIPOLE MOMENT
   -------------
                                   X             Y             Z
   Electronic contribution:     -2.73052      -4.20537       0.24659
   Nuclear contribution   :      3.48724       4.50131      -0.28886
                           -----------------------------------------
   Total Dipole Moment    :      0.75672       0.29593      -0.04226
                           -----------------------------------------
   Magnitude (a.u.)       :      0.81363
   Magnitude (Debye)      :      2.06808

       

**Output text.**

.. code:: xml

   <comment class="example.output" id="dipole">
           <module cmlx:templateRef="dipole">
             <array dataType="xsd:double" dictRef="cc:dipole" size="9">3.48724 -2.73052 0.75672 4.50131 -4.20537 0.29593 -0.28886 0.24659 -0.04226</array>
             <scalar dataType="xsd:double" dictRef="o:magnitude" units="nonsi2:au">0.81363</scalar>
             <scalar dataType="xsd:double" dictRef="o:magnitude" units="nonsi2:debye">2.06808</scalar>
          </module>  
       </comment>

**Template definition.**

.. code:: xml

   <record repeat="4" />
   <record>\s*Electronic\scontribution\s*:{F,o:electronicX}{F,o:electronicY}{F,o:electronicZ}</record>
   <record>\s*Nuclear\scontribution\s*:{F,o:nuclearX}{F,o:nuclearY}{F,o:nuclearZ}</record>
   <record repeat="1" />
   <record>\s*Total\sDipole\sMoment\s*:{F,o:totaldipoleX}{F,o:totaldipoleY}{F,o:totaldipoleZ}</record>
   <record repeat="1" />
   <record>\s*Magnitude.*:{F,o:magnitude}</record>
   <record>\s*Magnitude.*:{F,o:magnitude}</record>
   <transform process="addUnits" xpath="(.//cml:scalar[@dictRef='o:magnitude'])[1]" value="nonsi2:au" />
   <transform process="addUnits" xpath="(.//cml:scalar[@dictRef='o:magnitude'])[2]" value="nonsi2:debye" />
   <transform process="moveRelative" xpath=".//cml:list[child::cml:scalar[@dictRef='o:nuclearX']]" to="../.." position="1" />
   <transform process="createArray" xpath="." from=".//cml:scalar[ends-with(@dictRef,'X')]" />
   <transform process="createArray" xpath="." from=".//cml:scalar[ends-with(@dictRef,'Y')]" />
   <transform process="createArray" xpath="." from=".//cml:scalar[ends-with(@dictRef,'Z')]" />
   <transform process="joinArrays" xpath="." from=".//cml:array" />
   <transform process="addAttribute" xpath=".//cml:array" name="dictRef" value="cc:dipole" />
   <transform process="move" xpath=".//cml:array" to="." />
   <transform process="move" xpath=".//cml:scalar" to="." />
   <transform process="delete" xpath=".//cml:list" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
