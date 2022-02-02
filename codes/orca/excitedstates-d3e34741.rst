.. _excitedstates-d3e34741:

excitedstates
=============

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
   | *source*                                                                                                                   | Orca log                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | excitedstates                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | TDDFT Excited States                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*-{20,}&#92;s*$&#92;s*(TD-DFT.*|CIS-)EXCITED&#92;sSTATES.\*                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*$&#92;s*-{10,}                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | &#92;s*&#92;*{20,}&#92;s\*                                                                                                 |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern3                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | tddft/excitedstates.xml                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   ------------------------------------
   TD-DFT/TDA EXCITED STATES (SINGLETS)
   ------------------------------------

   the weight of the individual excitations are printed if larger than 0.01

   STATE  1:  E=   0.135814 au      3.696 eV    29807.7 cm**-1
       57a ->  62a  :     0.016564 (c=  0.12870193)
       60a ->  61a  :     0.917371 (c=  0.95779498)

   STATE  2:  E=   0.138685 au      3.774 eV    30437.9 cm**-1
       59a ->  61a  :     0.974818 (c= -0.98732887)
       59a ->  64a  :     0.017463 (c= -0.13214855)

   STATE  3:  E=   0.156161 au      4.249 eV    34273.5 cm**-1
       54a ->  61a  :     0.851979 (c= -0.92302726)
       54a ->  64a  :     0.021450 (c=  0.14645710)
       55a ->  61a  :     0.013888 (c=  0.11784878)
       56a ->  61a  :     0.102625 (c=  0.32035122)

   STATE  4:  E=   0.160383 au      4.364 eV    35199.9 cm**-1
       57a ->  61a  :     0.653589 (c=  0.80844850)
       60a ->  62a  :     0.314558 (c= -0.56085490)

   STATE  5:  E=   0.169963 au      4.625 eV    37302.5 cm**-1
       53a ->  61a  :     0.013704 (c=  0.11706288)
       54a ->  63a  :     0.018771 (c=  0.13700731)
       54a ->  65a  :     0.011145 (c=  0.10556849)
       58a ->  61a  :     0.904224 (c= -0.95090670)
       60a ->  64a  :     0.012155 (c= -0.11025148)

   STATE  6:  E=   0.172859 au      4.704 eV    37938.2 cm**-1
       57a ->  61a  :     0.315042 (c= -0.56128582)
       57a ->  64a  :     0.029119 (c=  0.17064165)
       60a ->  62a  :     0.607288 (c= -0.77928707)

   STATE  7:  E=   0.177259 au      4.823 eV    38903.8 cm**-1
       54a ->  61a  :     0.072841 (c=  0.26989101)
       55a ->  61a  :     0.693316 (c=  0.83265604)
       56a ->  61a  :     0.223679 (c=  0.47294757)

   STATE  8:  E=   0.177700 au      4.835 eV    39000.6 cm**-1
       54a ->  61a  :     0.045550 (c=  0.21342458)
       55a ->  61a  :     0.278073 (c= -0.52732671)
       56a ->  61a  :     0.660293 (c=  0.81258442)

   STATE  9:  E=   0.181688 au      4.944 eV    39875.8 cm**-1
       58a ->  63a  :     0.013631 (c=  0.11675201)
       60a ->  63a  :     0.954494 (c=  0.97698222)
       60a ->  65a  :     0.024787 (c=  0.15743778)

   STATE 10:  E=   0.192380 au      5.235 eV    42222.5 cm**-1
       53a ->  61a  :     0.636636 (c= -0.79789464)
       60a ->  64a  :     0.292660 (c= -0.54098073)


   -----------------------------   
       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" id="excitedstates">
           <module cmlx:templateRef="excitedstates"> 
              <scalar dataType="xsd:string" dictRef="o:type">SINGLET</scalar>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">1</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.135814</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="2">57 60</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="2">62 61</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="2">0.016564 0.917371</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="2">0.12870193 0.95779498</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">2</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.138685</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="2">59 59</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="2">61 64</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="2">0.974818 0.017463</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="2">-0.98732887 -0.13214855</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">3</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.156161</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="4">54 54 55 56</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="4">a a a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="4">61 64 61 61</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="4">a a a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="4">0.851979 0.021450 0.013888 0.102625</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="4">-0.92302726 0.14645710 0.11784878 0.32035122</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">4</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.160383</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="2">57 60</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="2">61 62</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="2">0.653589 0.314558</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="2">0.80844850 -0.56085490</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">5</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.169963</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="5">53 54 54 58 60</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="5">a a a a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="5">61 63 65 61 64</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="5">a a a a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="5">0.013704 0.018771 0.011145 0.904224 0.012155</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="5">0.11706288 0.13700731 0.10556849 -0.95090670 -0.11025148</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">6</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.172859</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="3">57 57 60</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="3">61 64 62</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="3">0.315042 0.029119 0.607288</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="3">-0.56128582 0.17064165 -0.77928707</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">7</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.177259</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="3">54 55 56</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="3">61 61 61</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="3">0.072841 0.693316 0.223679</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="3">0.26989101 0.83265604 0.47294757</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">8</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.177700</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="3">54 55 56</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="3">61 61 61</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="3">0.045550 0.278073 0.660293</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="3">0.21342458 -0.52732671 0.81258442</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">9</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.181688</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="3">58 60 60</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="3">63 63 65</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="3">a a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="3">0.013631 0.954494 0.024787</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="3">0.11675201 0.97698222 0.15743778</array>
              </module>
              <module cmlx:templateRef="root">
                 <scalar dataType="xsd:integer" dictRef="o:serial">10</scalar>
                 <scalar dataType="xsd:double" dictRef="o:totalEnergy" units="nonsi:hartree">0.192380</scalar>
                 <array dataType="xsd:integer" dictRef="o:occOrbitalNumber" size="2">53 60</array>
                 <array dataType="xsd:string" dictRef="o:occOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:integer" dictRef="o:virtOrbitalNumber" size="2">61 64</array>
                 <array dataType="xsd:string" dictRef="o:virtOrbitalLabel" size="2">a a</array>
                 <array dataType="xsd:double" dictRef="o:occEnergy" size="2">0.636636 0.292660</array>
                 <array dataType="xsd:double" dictRef="o:coeff" size="2">-0.79789464 -0.54098073</array>
              </module>
           </module>         
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record />
   <record>.*\sEXCITED\sSTATES\s\({X,o:type}S\).*</record>
   <transform process="pullup" xpath=".//cml:scalar" />
   <templateList>  <template id="root" pattern="\s*STATE.*" endPattern="\s*" endPattern2="~" repeat="*">    <record>\s*STATE{I,o:serial}:\s*E={F,o:totalEnergy}.*</record>    <record repeat="*" makeArray="true">{I,o:occOrbitalNumber}{A,o:occOrbitalLabel}->{I,o:virtOrbitalNumber}{A,o:virtOrbitalLabel}:{F,o:occEnergy}\(c={F,o:coeff}\)</record>    <record repeat="*" makeArray="true">{I,o:occOrbitalNumber}{A,o:occOrbitalLabel}->{I,o:virtOrbitalNumber}{A,o:virtOrbitalLabel}:{F,o:occEnergy}\s*</record>
           </template>   
       </templateList>
   <transform process="pullup" xpath=".//cml:array" />
   <transform process="pullup" xpath=".//cml:scalar[not(@dictRef='o:type')]" repeat="2" />
   <transform process="delete" xpath=".//cml:list" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='o:totalEnergy']" value="nonsi:hartree" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
