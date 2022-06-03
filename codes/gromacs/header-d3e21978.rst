.. _header-d3e21978:

header
======

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
   | *source*                                                                                                                   | GROMACS log                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | header                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | GROMACS header                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Log&#92;sfile&#92;sopened&#92;son.\*                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*GROMACS:.*VERSION.\*                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern3                                                                                                                   | .*GROMACS&#92;s*-&#92;s*gmx.\*                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*GROMACS&#92;sis&#92;sfree&#92;ssoftware.\*                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 4                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | header.xml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   Log file opened on Mon Mar  9 11:10:22 2020
   Host: node2178  pid: 24169  rank ID: 0  number of ranks:  1
   GROMACS:    gmx mdrun, VERSION 5.0.2

   GROMACS is written by:
   Emile Apol         Rossen Apostolov   Herman J.C. Berendsen Par Bjelkmar       
   Aldert van Buuren  Rudi van Drunen    Anton Feenstra     Sebastian Fritsch  
   Gerrit Groenhof    Christoph Junghans Peter Kasson       Carsten Kutzner    
   Per Larsson        Justin A. Lemkul   Magnus Lundborg    Pieter Meulenhoff  
   Erik Marklund      Teemu Murtola      Szilard Pall       Sander Pronk       
   Roland Schulz      Alexey Shvetsov    Michael Shirts     Alfons Sijbers     
   Peter Tieleman     Christian Wennberg Maarten Wolf       
   and the project leaders:
   Mark Abraham, Berk Hess, Erik Lindahl, and David van der Spoel

   Copyright (c) 1991-2000, University of Groningen, The Netherlands.
   Copyright (c) 2001-2014, The GROMACS development team at
   Uppsala University, Stockholm University and
   the Royal Institute of Technology, Sweden.
   check out http://www.gromacs.org for more information.

   GROMACS is free software; you can redistribute it and/or modify it   
       

.. container:: formalpara-title

   **Input**

::

                         :-) GROMACS - gmx mdrun, 2021.5 (-:

                               GROMACS is written by:
        Andrey Alekseenko              Emile Apol              Rossen Apostolov     
            Paul Bauer           Herman J.C. Berendsen           Par Bjelkmar       
          Christian Blau           Viacheslav Bolnykh             Kevin Boyd        
        Aldert van Buuren           Rudi van Drunen             Anton Feenstra      
       Gilles Gouaillardet             Alan Gray               Gerrit Groenhof      
          Anca Hamuraru            Vincent Hindriksen          M. Eric Irrgang      
         Aleksei Iupinov           Christoph Junghans             Joe Jordan        
       Dimitrios Karkoulis            Peter Kasson                Jiri Kraus        
         Carsten Kutzner              Per Larsson              Justin A. Lemkul     
          Viveca Lindahl            Magnus Lundborg             Erik Marklund       
           Pascal Merz             Pieter Meulenhoff            Teemu Murtola       
           Szilard Pall               Sander Pronk              Roland Schulz       
          Michael Shirts            Alexey Shvetsov             Alfons Sijbers      
          Peter Tieleman              Jon Vincent              Teemu Virolainen     
        Christian Wennberg            Maarten Wolf              Artem Zhmurov       
                              and the project leaders:
           Mark Abraham, Berk Hess, Erik Lindahl, and David van der Spoel

   Copyright (c) 1991-2000, University of Groningen, The Netherlands.
   Copyright (c) 2001-2019, The GROMACS development team at
   Uppsala University, Stockholm University and
   the Royal Institute of Technology, Sweden.
   check out http://www.gromacs.org for more information.

   GROMACS is free software; you can redistribute it and/or modify it    
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="header">   
           <module cmlx:templateRef="header">
              <module cmlx:templateRef="rundate">
                  <scalar dataType="xsd:date" dictRef="cc:runDate">2020-03-09T11:10:22.000+01:00</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:hostName">node2178</scalar>
                  <scalar dataType="xsd:integer" dictRef="gm:numRanks">1</scalar>
               </module>
               <module cmlx:templateRef="program">
                  <scalar dataType="xsd:string" dictRef="cc:program">GROMACS</scalar>
                  <scalar dataType="xsd:string" dictRef="cc:programVersion">5.0.2</scalar>
               </module>
               <module cmlx:templateRef="authors">
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">GROMACS is written by:</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Emile Apol         Rossen Apostolov   Herman J.C. Berendsen Par Bjelkmar</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Aldert van Buuren  Rudi van Drunen    Anton Feenstra     Sebastian Fritsch</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Gerrit Groenhof    Christoph Junghans Peter Kasson       Carsten Kutzner</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Per Larsson        Justin A. Lemkul   Magnus Lundborg    Pieter Meulenhoff</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Erik Marklund      Teemu Murtola      Szilard Pall       Sander Pronk</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Roland Schulz      Alexey Shvetsov    Michael Shirts     Alfons Sijbers</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Peter Tieleman     Christian Wennberg Maarten Wolf</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">and the project leaders:</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:unparsed">Mark Abraham, Berk Hess, Erik Lindahl, and David van der Spoel</scalar>
               </module>
               <module cmlx:templateRef="legal">
                  <scalar dataType="xsd:string" dictRef="gm:legal">Copyright (c) 1991-2000, University of Groningen, The Netherlands.</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:legal">Copyright (c) 2001-2014, The GROMACS development team at</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:legal">Uppsala University, Stockholm University and</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:legal">the Royal Institute of Technology, Sweden.</scalar>
                  <scalar dataType="xsd:string" dictRef="gm:legal">check out http://www.gromacs.org for more information.</scalar>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="rundate" pattern="\s*Log\sfile\sopened\son.*" endPattern="\s*.*GROMACS.*" endOffset="0">    <record>\s*Log\sfile\sopened\son{X,cc:runDate}</record>    <record>\s*Host:{A,cc:hostName}.*number\sof\sranks:{I,gm:numRanks}</record>    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:runDate']" format="E MMM  d HH:mm:ss yyyy" />    <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:runDate']" format="E MMM dd HH:mm:ss yyyy" />    <transform process="pullup" xpath=".//cml:list/cml:list/cml:scalar" />                                  
           </template>  <template id="program" pattern="\s*GROMACS.*VERSION.*" endPattern=".*" endOffset="0">    <record>{A,cc:program}:.*,\s*VERSION{A,cc:programVersion}</record>    <transform process="pullup" xpath=".//cml:scalar" />  
           </template>  <template id="program" pattern=".*GROMACS\s*-\s*gmx.*" endPattern=".*" endOffset="0">    <record>.*\s+{A,cc:program}\s+-.*,\s*(?:VERSION)?\s+{A,cc:programVersion}.*</record>    <transform process="pullup" xpath=".//cml:scalar" />    
           </template>  <template id="authors" name="AUTHORS" pattern="\s*GROMACS\sis\swritten\sby.*" endPattern="\s*" repeat="*">    <record repeat="*">{X,gm:unparsed}</record>
           </template>  <template id="legal" pattern="\s*Copyright.*" endPattern=".*$\s*" endOffset="1">    <record repeat="*">{X,gm:legal}</record>
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:scalar" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
