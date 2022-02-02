.. _seward.generate-d3e24649:

seward.generate
===============

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image2|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | MOLCAS log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | seward.generate                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | SEWARD module generate section                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*SEWARD&#92;swill&#92;sgenerate:.\*                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*(Integrals|Nuclear&#92;s*Potential).\*                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s\*                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/seward/generate.xml                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                  SEWARD will generate:
                     Multipole Moment integrals up to order  2
                     Kinetic Energy integrals
                     Nuclear Attraction integrals (point charge)
                     One-Electron Hamiltonian integrals
                     Relativistic Douglas-Kroll-Hess integrals:
                       - Parametrization         : EXP
                       - DKH order of Hamiltonian: 2
                       - DKH order of Properties : 0
                            - multipole moment operators
                            - electric potential operators
                            - contact operators
                     Atomic mean-field integrals
                     Cholesky decomposed two-electron repulsion integrals
                      - CD Threshold:   0.10E-05
       
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="seward.generate">      
           <module>
              <list cmlx:templateRef="seward.line">
                 <scalar dataType="xsd:string" dictRef="x:line">Multipole Moment integrals up to order  2</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">Kinetic Energy integrals</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">Nuclear Attraction integrals (point charge)</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">One-Electron Hamiltonian integrals</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">Relativistic Douglas-Kroll-Hess integrals:</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- Parametrization         : EXP</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- DKH order of Hamiltonian: 2</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- DKH order of Properties : 0</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- multipole moment operators</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- electric potential operators</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- contact operators</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">Atomic mean-field integrals</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">Cholesky decomposed two-electron repulsion integrals</scalar>
                 <scalar dataType="xsd:string" dictRef="x:line">- CD Threshold:   0.10E-05</scalar>
              </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record id="seward.line" repeat="*">{X,x:line}</record>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
