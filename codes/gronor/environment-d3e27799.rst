.. _environment-d3e27799:

environment
===========

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
   | *source*                                                                                                                   | GronOR cml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | environment                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | environment.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

      
    
    GronOR: Non-Orthogonal Configuration Interaction

    Version 21.00 under active development

    T. P. Straatsma                                 C. de Graaf                     R. Broer
                                                    A. Sanchez                      R. K. Kathir

    National Center for Computational Sciences      Quantum Chemistry Group         Department of Theoretical Chemistry
    Oak Ridge National Laboratory                   University Rovira i Virgili     University of Groningen
    Oak Ridge, Tennessee, USA                       Tarragona, Spain                Groningen, the Netherlands

    Based on GNOME written by R. Broer-Braam, J. Th. van Montfort, and B. Vunderink

    Please cite the following reference when publishing results obtained using GronOR:

    T. P. Straatsma, R. Broer, S. Faraji,R. W. A. Havenith, L. E. Aguilar Suarez, R. K. Kathir, M. Wibowo, and C.de Graaf
    "GronOR: Massively parallel and GPU-accelerated non-orthogonal configuration interaction for large molecular systems"
    Journal of Chemical Physics, 152 (2020), https://doi.org/10.1063/1.5141358



    User                                                      CPU count                                       24

    Host                        maginet206                    Number of nodes                                  1
    Date                        21/04/28                      Number of resource sets                          7
    Time                        16:03:34                      Number of resource sets per node                 7
                                                              Number of GPUs per resource set                  2
                                                              Number of MPI ranks                              7
                                                              Number of MPI ranks per node                     7
                                                              Number of MPI ranks per resource set             1
                                                              Number of rank assignment cycles                 1
                                                              Number of OPENMP threads                         0
                                                              Available memory on device                      13.468 GB
                                                              Total memory on device                          15.752 GB

    Command argument            /home/qq/coen/gronor/build/bin/gronor
    Current working directory   /scratch/242470.1.mag20.q
                                                              
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="environment">
           <module dictRef="cc:environment" id="environment">
               <parameterList>
                   <parameter dictRef="cc:program">
                       <scalar dataType="xsd:string">GronOR</scalar>
                   </parameter>
                   <parameter dictRef="cc:programVersion">
                       <scalar dataType="xsd:string">21.00</scalar>
                   </parameter>
                   <parameter dictRef="cc:programSubversion">
                       <scalar dataType="xsd:string">under active development</scalar>
                   </parameter>
                   <parameter dictRef="cc:executable">
                       <scalar dataType="xsd:string">/home/qq/coen/gronor/build/bin/gronor</scalar>
                   </parameter>
                   <parameter dictRef="cc:hostName">
                       <scalar dataType="xsd:string">maginet206</scalar>
                   </parameter>
                   <parameter dictRef="cc:numProc">
                       <scalar dataType="xsd:integer">24</scalar>
                   </parameter>
                   <parameter dictRef="gr:numProcGPU">
                       <scalar dataType="xsd:integer">2</scalar>
                   </parameter>
                   <parameter dictRef="gr:numRanks">
                       <scalar dataType="xsd:integer">1</scalar>
                   </parameter>
                   <parameter dictRef="gr:numAccRanks">
                       <scalar dataType="xsd:integer">6</scalar>
                   </parameter>
                   <parameter dictRef="gr:taskSize">
                       <scalar dataType="xsd:integer">20</scalar>
                   </parameter>
                   <parameter dictRef="cc:runDate">
                       <scalar dataType="xsd:string">21/04/28  16:03:34</scalar>
                   </parameter>
               </parameterList>
           </module> 
       </comment>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
