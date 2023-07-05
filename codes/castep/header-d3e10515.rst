.. _header-d3e10515:

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
   | *source*                                                                                                                   | CASTEP log                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | header                                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | CASTEP header                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*Job&#92;sstarted&#92;son&#92;shost.\*                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*License&#92;scheckout&#92;sof.*$.\*                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;sInfo:.\*                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | &#92;sReading&#92;scontinuation&#92;sdata.\*                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | header.xml                                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

    Job started on host XXXXX
    at Mon Mar 14 20:34:42 2022

    +-------------------------------------------------+
    |                                                 |
    |      CCC   AA    SSS  TTTTT  EEEEE  PPPP        |
    |     C     A  A  S       T    E      P   P       |
    |     C     AAAA   SS     T    EEE    PPPP        |
    |     C     A  A     S    T    E      P           |
    |      CCC  A  A  SSS     T    EEEEE  P           |
    |                                                 |
    +-------------------------------------------------+
    |                                                 |
    | Materials Studio CASTEP version 2021 HF1        |
    | Ab Initio Total Energy Program                  |
    |                                                 |
    | Authors:                                        |
    | M. Segall, M. Probert, C. Pickard, P. Hasnip,   |
    | S. Clark, K. Refson, J. R. Yates, M. Payne      |
    |                                                 |
    | Contributors:                                   |
    | P. Lindan, P. Haynes, J. White, V. Milman,      |
    | N. Govind, M. Gibson, P. Tulip, V. Cocula,      |
    | B. Montanari, D. Quigley, M. Glover,            |
    | L. Bernasconi, A. Perlov, M. Plummer,           |
    | E. McNellis, J. Meyer, J. Gale, D. Jochym       |
    | J. Aarons, B. Walker, R. Gillen, D. Jones       |
    | T. Green, I. J. Bush, C. J. Armstrong,          |
    | E. J. Higgins, E. L. Brown, M. S. McFly,        |
    | J. Wilkins, B-C. Shih, P. J. P. Byrne,          |
    | R. J. Maurer, J. C. Womack, J. Dziedzic,        |
    | A. Bartok-Partay, L. LeBlanc                    |
    |                                                 |
    | Copyright (c) 2000 - 2021                       |
    |                                                 |
    | Please cite                                     |
    |                                                 |
    |     "First principles methods using CASTEP"     |
    |                                                 |
    |         Zeitschrift fuer Kristallographie       |
    |           220(5-6) pp. 567-570 (2005)           |
    |                                                 |
    | S. J. Clark, M. D. Segall, C. J. Pickard,       |
    | P. J. Hasnip, M. J. Probert, K. Refson,         |
    | M. C. Payne                                     |
    |                                                 |
    |       in all publications arising from          |
    |              your use of CASTEP                 |
    |                                                 |
    +-------------------------------------------------+
    |                                                 |
    |              http://www.castep.org              |
    |                                                 |
    +-------------------------------------------------+


    This version was compiled for x86_64-XXXXXX on May 11 2021
    Code version:    cXXXXXXXd
    Intel(R) Math Kernel Library Version 2019.0.4
    Fundamental constants values: CODATA 2014

   License checkout of MS_castep successful    
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="header">   
         <module cmlx:templateRef="header">
            <module cmlx:templateRef="program">
               <scalar dataType="xsd:string" dictRef="cc:program">CASTEP</scalar>
               <scalar dataType="xsd:string" dictRef="cc:programVersion">2021 HF1</scalar>
            </module>
            <module cmlx:templateRef="authors">
               <scalar dataType="xsd:string" dictRef="ca:unparsed">M. Segall, M. Probert, C. Pickard, P. Hasnip,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">S. Clark, K. Refson, J. R. Yates, M. Payne</scalar>
            </module>
            <module cmlx:templateRef="contributors">
               <scalar dataType="xsd:string" dictRef="ca:unparsed">P. Lindan, P. Haynes, J. White, V. Milman,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">N. Govind, M. Gibson, P. Tulip, V. Cocula,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">B. Montanari, D. Quigley, M. Glover,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">L. Bernasconi, A. Perlov, M. Plummer,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">E. McNellis, J. Meyer, J. Gale, D. Jochym</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">J. Aarons, B. Walker, R. Gillen, D. Jones</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">T. Green, I. J. Bush, C. J. Armstrong,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">E. J. Higgins, E. L. Brown, M. S. McFly,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">J. Wilkins, B-C. Shih, P. J. P. Byrne,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">R. J. Maurer, J. C. Womack, J. Dziedzic,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:unparsed">A. Bartok-Partay, L. LeBlanc</scalar>
            </module>
            <module cmlx:templateRef="legal">
               <scalar dataType="xsd:string" dictRef="ca:legal">Please cite</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal" />
               <scalar dataType="xsd:string" dictRef="ca:legal">"First principles methods using CASTEP"</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal" />
               <scalar dataType="xsd:string" dictRef="ca:legal">Zeitschrift fuer Kristallographie</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal">220(5-6) pp. 567-570 (2005)</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal" />
               <scalar dataType="xsd:string" dictRef="ca:legal">S. J. Clark, M. D. Segall, C. J. Pickard,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal">P. J. Hasnip, M. J. Probert, K. Refson,</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal">M. C. Payne</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal" />
               <scalar dataType="xsd:string" dictRef="ca:legal">in all publications arising from</scalar>
               <scalar dataType="xsd:string" dictRef="ca:legal">your use of CASTEP</scalar>
            </module>
            <module cmlx:templateRef="compilation">
               <scalar dataType="xsd:string" dictRef="cc:programFlavour">x86_64-XXXXXX</scalar>
               <scalar dataType="xsd:date" dictRef="cc:compileDate">2021-05-11T00:00:00.000</scalar>
               <scalar dataType="xsd:string" dictRef="ca:compilation">cXXXXXXXd</scalar>
            </module>
         </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="1" />
   <record>\s*at\s*{X,cc:runDate}</record>
   <templateList>  <template id="program" pattern="\s*\|\s*Materials\sStudio.*" endPattern=".*">    <record>\s*\|\s*Materials\s*Studio\s*{A,cc:program}version{X,cc:programVersion}\s*\|.*</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="2" />   
           </template>  <template id="authors" pattern="\s*\|\s*Authors:.*" endPattern="\s*\|\s*\|.*">    <record repeat="1" />    <record repeat="*">\s*\|{X,ca:unparsed}\s*\|.*</record>    <transform process="pullup" xpath=".//cml:scalar" />         
           </template>  <template id="contributors" pattern="\s*\|\s*Contributors:.*" endPattern="\s*\|\s*\|.*">    <record repeat="1" />    <record repeat="*">\s*\|{X,ca:unparsed}\s*\|.*</record>    <transform process="pullup" xpath=".//cml:scalar" />       
           </template>  <template id="legal" pattern="\s*\|\s*Please\scite.*" endPattern="\s*\|\s*your\suse\sof\sCASTEP.*" endOffset="1">    <record repeat="*">\s*\|{X,ca:legal}\s*\|.*</record>    <transform process="pullup" xpath=".//cml:scalar" />        
           </template>  <template id="compilation" pattern="\s*This\sversion\swas\scompiled\sfor.*" endPattern="\s*">    <record>\s*This\sversion\swas\scompiled\sfor{X,cc:programFlavour}on{X,cc:compileDate}</record>    <record>\s*Code\sversion:{X,ca:compilation}</record>    <transform process="move" xpath=".//cml:scalar" to="." />           
           </template>   
       </templateList>
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:runDate']" format="E MMM d HH:mm:ss yyyy" />
   <transform process="createDate" xpath=".//cml:scalar[@dictRef='cc:compileDate']" format="MMM d yyyy" />
   <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:runDate']" repeat="2" />
   <transform process="delete" xpath=".//cml:list" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Partial.png
