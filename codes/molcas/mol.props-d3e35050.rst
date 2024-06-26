.. _mol.props-d3e35050:

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
   | pattern4                                                                                                                   | &#92;s*0-th&#92;scartesian&#92;smoments.\*                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern5                                                                                                                   | &#92;s*1-st&#92;scartesian&#92;smoments.\*                                                                                 |
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

   **Input**

::

   ++    Molecular properties:
         ---------------------
    


          0-th cartesian moments: origin at (  0.00000000,  0.00000000,  0.00000000)
         ----------------------------------------------------------------------------
    Total electronic           -88.00000000
    Total nuclear               88.00000000
    Total                       -0.00000000


          1-st cartesian moments: origin at (  0.00000000,  0.00000000,  0.00000000)
         ----------------------------------------------------------------------------
    Component                             X               Y               Z
    Total electronic             0.01935730     -0.01851873      0.00294087
    Total nuclear               -0.00307906      0.00260417     -0.00329434
    Total                        0.01627824     -0.01591456     -0.00035347
         ----------------------------------------------------------------------------
         Total                   0.04137515     -0.04045077     -0.00089842   Debye


          2-nd cartesian moments: origin at ( -0.00003628,  0.00003036, -0.00004257)
         ----------------------------------------------------------------------------
    Component                            XX              XY              XZ              YY              YZ              ZZ
    Total electronic          -831.88832118      0.50024847     -0.08433525   -831.93739411      0.02514024    -52.93756282
    Total nuclear              773.04612795     -0.48360531      0.08395606    773.09369915     -0.02343185      0.00001626
    Total                      -58.84219323      0.01664316     -0.00037919    -58.84369496      0.00170839    -52.93754655



         Cartesian  2-pole moment: origin at ( -0.00003628,  0.00003036, -0.00004257)
         ----------------------------------------------------------------------------
    Component                            XX              XY              XZ              YY              YZ              ZZ
    Total electronic          -389.45084272      0.75037270     -0.12650288   -389.52445211      0.03771036    778.97529483
    Total nuclear              386.49927024     -0.72540796      0.12593409    386.57062704     -0.03514778   -773.06989728
    Total                       -2.95157247      0.02496474     -0.00056879     -2.95382507      0.00256258      5.90539754

   --
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

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

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="mol.props2">
           <module cmlx:templateRef="mol.props">
               <scalar dataType="xsd:double" dictRef="cc:charge">-0.00000000</scalar>
               <list cmlx:templateRef="dipole">
                   <array dataType="xsd:double" dictRef="m:dipole" size="3">0.04137515 -0.04045077 -0.00089842</array>
                   <array dataType="xsd:double" dictRef="m:operatororig" size="3">0.00000000 0.00000000 0.00000000</array>
               </list>
               <list cmlx:templateRef="quadrupole">
                   <array dataType="xsd:double" dictRef="m:quadvalue" size="6">-58.84219323 0.01664316 -0.00037919 -58.84369496 0.00170839 -52.93754655</array>
                   <array dataType="xsd:double" dictRef="m:operatororig" size="3">-0.00003628 0.00003036 -0.00004257</array>
                   <array dataType="xsd:double" dictRef="m:quadtracevalue" size="6">-2.95157247 0.02496474 -0.00056879 -2.95382507 0.00256258 5.90539754</array>
               </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="charge" name="Charge" pattern="\s*Charge.*" endPattern=".*[0-9]\s*" endOffset="1">    <record />    <record>\s*={F,cc:charge}</record>
           </template>  <template id="charge" name="Charge" pattern="\s*0-th\scartesian\smoments.*" endPattern="\s*" endOffset="1">    <record repeat="3" />    <record>\s*Total\s*{F,cc:charge}</record>
           </template>  <template id="dipole" name="Dipole/Quadripole moment" pattern="\s*Dipole\sMoment.*" endPattern="\s*" endPattern2="~">    <record />    <record>\s*Origin\sof\sthe\soperator\s\(Ang\)=\s*{3F,m:operatororig}</record>    <record id="dipole">\s*X={E,m:dipole}Y={E,m:dipole}Z={E,m:dipole}Total={E,m:total}</record>    <record />    <record>\s*Origin\sof\sthe\soperator\s\(Ang\)=\s*{3F,m:operatororig}</record>    <record id="quadrupole">\s*XX={E,m:quadvalue}XY={E,m:quadvalue}XZ={E,m:quadvalue}YY={E,m:quadvalue}</record>    <record id="quadrupole">\s*YZ={E,m:quadvalue}ZZ={E,m:quadvalue}</record>    <record />    <record id="quadrupole">\s*XX={E,m:quadtracevalue}XY={E,m:quadtracevalue}XZ={E,m:quadtracevalue}YY={E,m:quadtracevalue}</record>    <record id="quadrupole">\s*YZ={E,m:quadtracevalue}ZZ={E,m:quadtracevalue}</record>
           </template>  <template id="dipole2" name="dipole2" pattern="\s*1-st\scartesian\smoments.*" endPattern="\s*" endPattern2="~">    <record>\s*1-st\scartesian\smoments:\s*origin\s*at\s*\S\s{F,m:operatororig}\,{F,m:operatororig}\,{F,m:operatororig}.*</record>    <record repeat="6" />    <record id="dipole">\s*Total{E,m:dipole}{E,m:dipole}{E,m:dipole}\s*Debye.*</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:operatororig']" />
           </template>  <template id="quadrupole2" name="quadrupole2" pattern="\s*2-nd\scartesian\smoments.*" endPattern="\s*" endPattern2="~">    <record>\s*2-nd\scartesian\smoments:\sorigin\sat\s*\S\s{F,m:operatororig}\,{F,m:operatororig}\,{F,m:operatororig}.*</record>    <record repeat="4" />    <record id="quadrupole">\s*Total\s*{E,m:quadvalue}{E,m:quadvalue}{E,m:quadvalue}{E,m:quadvalue}{E,m:quadvalue}{E,m:quadvalue}</record>    <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:operatororig']" />
           </template>  <template id="quadrupole3" name="quadrupole3" pattern="\s*Cartesian\s*2-pole\smoment.*" endPattern="\s*" endPattern2="~">    <record repeat="5" />    <record id="quadrupole">\s*Total\s*{E,m:quadtracevalue}{E,m:quadtracevalue}{E,m:quadtracevalue}{E,m:quadtracevalue}{E,m:quadtracevalue}{E,m:quadtracevalue}</record>
           </template>  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:dipole']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:quadvalue']" />  <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='m:quadtracevalue']" />  <transform process="move" xpath="(.//cml:array[@dictRef='m:operatororig'])[1]" to=".//cml:list[@cmlx:templateRef='dipole']" />  <transform process="move" xpath="(.//cml:array[@dictRef='m:operatororig'])[2]" to="(.//cml:list[@cmlx:templateRef='quadrupole'])[1]" />  <transform process="move" xpath=".//cml:array[@dictRef='m:quadtracevalue']" to="(.//cml:list[@cmlx:templateRef='quadrupole'])[1]" />  <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='dipole' or @cmlx:templateRef='quadrupole']/cml:list/*" />  <transform process="pullup" xpath=".//cml:scalar[@dictRef='cc:charge']" repeat="2" />  <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='dipole']" repeat="1" />  <transform process="pullup" xpath=".//cml:list[@cmlx:templateRef='quadrupole']" repeat="1" />  <transform process="delete" xpath=".//cml:list[count(*) = 0]" />  <transform process="delete" xpath=".//cml:list[count(*) = 0]" />  <transform process="delete" xpath=".//cml:module[count(*) = 0]" /> 

       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
