.. _adf.frequencyanalysis-d3e9464:

adf.frequencyanalysis
=====================

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
   | *source*                                                                                                                   | AMS ADF log                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | adf.frequencyanalysis                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Frequency analysis                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s+&#92;*&#92;s+F&#92;sR&#92;sE&#92;sQ&#92;sU&#92;sE&#92;sN&#92;sC.\*                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*&#92;d*&#92;s*$&#92;s&#92;*{20,}.*$(&#92;s*|&#92;s*LOGFILE.*)                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 2                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | adf/frequencyanalysis.xml                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Comment**

::

                                        ******************************************
                                        *  F R E Q U E N C Y    A N A L Y S I S  *
                                        ******************************************
   ...



    List of All Frequencies:


    Intensities
    ===========

                  Frequency       Dipole Strength        Absorption Intensity (degeneracy not counted)
                    cm-1           1e-40 esu2 cm2          km/mole
                 ----------          ----------          ----------
                 -28.256192           39.676107           -0.281009
                  45.405798           70.141843            0.798301
                  54.750200          154.864558            2.125278
                 100.940099          135.844174            3.437026
                 118.700499           83.850608            2.494806
                 121.007136           78.677577            2.386382
                 169.723900          147.801795            6.287830
                 175.522184           32.572762            1.433061
                 184.419714           28.453475            1.315288
                 211.159563            0.892712            0.047250
                 212.913244            0.111568            0.005954
                 224.315297            3.541865            0.199145
                 258.149623            0.210207            0.013602
                 262.776833            0.020431            0.001346
                 279.266385           13.682438            0.957768
       
   ...  
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="intensities">
           <module cmlx:templateRef="adf.frequencyanalysis">             
              <module cmlx:templateRef="intensities">
                 <array dataType="xsd:double" dictRef="cc:frequency" units="nonsi:cm-1" size="15">-28.256192 45.405798 54.7502 100.940099 118.700499 121.007136 169.7239 175.522184 184.419714 211.159563 212.913244 224.315297 258.149623 262.776833 279.266385</array>
                 <array dataType="xsd:double" dictRef="cc:dipole" units="nonsi2:1e-40.esu2.cm2" size="15">39.676107 70.141843 154.864558 135.844174 83.850608 78.677577 147.801795 32.572762 28.453475 0.892712 0.111568 3.541865 0.210207 0.020431 13.682438</array>
                 <array dataType="xsd:double" dictRef="cc:absortion" units="nonsi2:km.mole-1" size="15">-0.281009 0.798301 2.125278 3.437026 2.494806 2.386382 6.28783 1.433061 1.315288 0.04725 0.005954 0.199145 0.013602 0.001346 0.957768</array>
              </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="intensities" name="Vibrational frequencies intensity" pattern="\s*List\sof\sAll\sFrequencies:\s*" endPattern="(\s*[\d\.-]+\s*){3}$\s*" endPattern2="~" endOffset="1" repeat="*">    <record repeat="9" />    <record repeat="*" makeArray="true">{F,cc:frequency}{F,cc:dipole}{F,cc:absortion}</record>    <transform process="pullup" xpath=".//cml:array" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:frequency']" value="nonsi:cm-1" />    <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:dipole']" value="nonsi2:1e-40.esu2.cm2" />    <transform process="addUnits" xpath=".//cml:array[@dictRef='cc:absortion']" value="nonsi2:km.mole-1" />
           </template>
       </templateList>

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
