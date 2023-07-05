.. _mol.props-d3e35021:

mol.props
=========

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
   | id                                                                                                                         | mol.props                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Molecular properties                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*(?:&#92;+&#92;+)?&#92;s*Molecular&#92;s[Pp]roperties:.\*                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern2                                                                                                                   | &#92;s*Charge.\*                                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern3                                                                                                                   | &#92;s*Dipole&#92;sMoment.\*                                                                                               |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;-&#92;-&#92;s\*                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | modules/properties/mol.props.xml                                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   ++    Molecular properties:
         ---------------------
    
         Charge (e):
                         =   -0.0000
         Dipole Moment (Debye):
         Origin of the operator (Ang)=    0.0000    0.0000    0.0000
                        X=    0.0000               Y=    0.0000               Z=    0.0000           Total=    0.0000
         Quadrupole Moment (Debye*Ang):
         Origin of the operator (Ang)=    0.0000    0.0000    0.0000
                       XX=  -92.8211              XY=    0.0000              XZ=    0.0000              YY= -101.7054
                       YZ=    0.0000              ZZ= -128.7810
         In traceless form (Debye*Ang)
                       XX=   22.4221              XY=    0.0000              XZ=    0.0000              YY=    9.0956
                       YZ=    0.0000              ZZ=  -31.5177
   --  
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="mol.props">
            <module cmlx:templateRef="mol.props">
              <scalar dataType="xsd:double" dictRef="cc:charge">-0.0000</scalar>
              <list cmlx:templateRef="dipole">
                 <array dataType="xsd:double" dictRef="m:dipole" size="3">0.0000 0.0000 0.0000</array>
                 <scalar dataType="xsd:double" dictRef="m:total">0.0000</scalar>
                 <array dataType="xsd:double" dictRef="m:operatororig" size="3">0.0000 0.0000 0.0000</array>
              </list>
              <list cmlx:templateRef="quadrupole">
                 <array dataType="xsd:double" dictRef="m:quadvalue" size="6">-92.8211 0.0000 0.0000 -101.7054 0.0000 -128.7810</array>
                 <array dataType="xsd:double" dictRef="m:operatororig" size="3">0.0000 0.0000 0.0000</array>
                 <array dataType="xsd:double" dictRef="m:quadtracevalue" size="6">22.4221 0.0000 0.0000 9.0956 0.0000 -31.5177</array>
              </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <templateList>  <template id="charge" name="Charge" pattern="\s*Charge.*" endPattern=".*[0-9]\s*" endOffset="1">    <record />    <record>\s*={F,cc:charge}</record>
           </template>  <template id="dipole" name="Dipole/Quadripole moment" pattern="\s*Dipole\sMoment.*" endPattern="\s*" endPattern2="~">    <record />    <record>\s*Origin\sof\sthe\soperator\s\(Ang\)=\s*{3F,m:operatororig}</record>    <record id="dipole">\s*X={E,m:dipole}Y={E,m:dipole}Z={E,m:dipole}Total={E,m:total}</record>    <record />    <record>\s*Origin\sof\sthe\soperator\s\(Ang\)=\s*{3F,m:operatororig}</record>    <record id="quadrupole">\s*XX={E,m:quadvalue}XY={E,m:quadvalue}XZ={E,m:quadvalue}YY={E,m:quadvalue}</record>    <record id="quadrupole">\s*YZ={E,m:quadvalue}ZZ={E,m:quadvalue}</record>    <record />    <record id="quadrupole">\s*XX={E,m:quadtracevalue}XY={E,m:quadtracevalue}XZ={E,m:quadtracevalue}YY={E,m:quadtracevalue}</record>    <record id="quadrupole">\s*YZ={E,m:quadtracevalue}ZZ={E,m:quadtracevalue}</record>       
           </template>  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:dipole']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:quadvalue']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:quadtracevalue']" />  <transform process="move" xpath="(.//cml:array[@dictRef='m:operatororig'])[1]" to=".//cml:list[@cmlx:templateRef='dipole']" />  <transform process="move" xpath="(.//cml:array[@dictRef='m:operatororig'])[2]" to="(.//cml:list[@cmlx:templateRef='quadrupole'])[1]" />  <transform process="move" xpath=".//cml:array[@dictRef='m:quadtracevalue']" to="(.//cml:list[@cmlx:templateRef='quadrupole'])[1]" />  <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='dipole' or @cmlx:templateRef='quadrupole']/cml:list/*" />  <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:charge']" repeat="2" />  <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='dipole']" repeat="1" />  <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='quadrupole']" repeat="1" />  <transform process="delete" xpath=".//cml:list[count(*) = 0]" />  <transform process="delete" xpath=".//cml:list[count(*) = 0]" />  <transform process="delete" xpath=".//cml:module[count(*) = 0]" />

       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
