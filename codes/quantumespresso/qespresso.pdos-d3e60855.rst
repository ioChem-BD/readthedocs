.. _qespresso.pdos-d3e60855:

qespresso.pdos
==============

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
   | *source*                                                                                                                   | QuantumEspresso PDOS                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | qespresso.pdos                                                                                                             |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | QuantumEspresso PDOS                                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | topTemplate.xml                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   # E (eV)   ldos(E)   pdos(E)    pdos(E)    pdos(E)    pdos(E)    pdos(E)    pdos(E)    pdos(E)   
     -6.275  0.895E-02  0.236E-02  0.383E-03  0.383E-03  0.174E-02  0.174E-02  0.391E-04  0.230E-02
     -6.265  0.844E-02  0.220E-02  0.366E-03  0.366E-03  0.166E-02  0.166E-02  0.380E-04  0.215E-02
     -6.255  0.796E-02  0.206E-02  0.349E-03  0.349E-03  0.158E-02  0.158E-02  0.371E-04  0.201E-02
     -6.245  0.752E-02  0.192E-02  0.334E-03  0.334E-03  0.150E-02  0.150E-02  0.364E-04  0.189E-02
     -6.235  0.710E-02  0.179E-02  0.320E-03  0.320E-03  0.143E-02  0.143E-02  0.357E-04  0.177E-02
     -6.225  0.670E-02  0.167E-02  0.306E-03  0.306E-03  0.136E-02  0.136E-02  0.351E-04  0.165E-02
     -6.215  0.632E-02  0.156E-02  0.293E-03  0.293E-03  0.130E-02  0.130E-02  0.345E-04  0.155E-02
     -6.205  0.598E-02  0.145E-02  0.280E-03  0.280E-03  0.124E-02  0.124E-02  0.339E-04  0.145E-02
     -6.195  0.570E-02  0.137E-02  0.270E-03  0.270E-03  0.119E-02  0.119E-02  0.333E-04  0.137E-02
     -6.185  0.541E-02  0.129E-02  0.259E-03  0.259E-03  0.114E-02  0.114E-02  0.327E-04  0.129E-02
     -6.175  0.510E-02  0.120E-02  0.248E-03  0.248E-03  0.108E-02  0.108E-02  0.319E-04  0.121E-02
     -6.165  0.477E-02  0.111E-02  0.235E-03  0.235E-03  0.102E-02  0.102E-02  0.310E-04  0.112E-02
     -6.155  0.443E-02  0.102E-02  0.221E-03  0.221E-03  0.957E-03  0.957E-03  0.299E-04  0.103E-02
     -6.145  0.408E-02  0.923E-03  0.206E-03  0.206E-03  0.889E-03  0.889E-03  0.286E-04  0.938E-03
     -6.135  0.372E-02  0.829E-03  0.190E-03  0.190E-03  0.817E-03  0.817E-03  0.270E-04  0.847E-03
     -6.125  0.335E-02  0.739E-03  0.173E-03  0.173E-03  0.742E-03  0.742E-03  0.251E-04  0.757E-03
     -6.115  0.298E-02  0.653E-03  0.155E-03  0.155E-03  0.663E-03  0.663E-03  0.229E-04  0.671E-03
     -6.105  0.261E-02  0.573E-03  0.136E-03  0.136E-03  0.580E-03  0.580E-03  0.204E-04  0.588E-03
     -6.095  0.225E-02  0.501E-03  0.116E-03  0.116E-03  0.494E-03  0.494E-03  0.174E-04  0.512E-03
     -6.085  0.193E-02  0.443E-03  0.966E-04  0.966E-04  0.414E-03  0.414E-03  0.145E-04  0.448E-03
     -6.075  0.177E-02  0.414E-03  0.866E-04  0.866E-04  0.375E-03  0.375E-03  0.127E-04  0.418E-03
     -6.065  0.167E-02  0.397E-03  0.802E-04  0.802E-04  0.353E-03  0.353E-03  0.115E-04  0.401E-03
     -6.055  0.162E-02  0.385E-03  0.766E-04  0.766E-04  0.340E-03  0.340E-03  0.108E-04  0.389E-03
     -6.045  0.159E-02  0.379E-03  0.751E-04  0.751E-04  0.333E-03  0.333E-03  0.106E-04  0.383E-03
     -6.035  0.155E-02  0.374E-03  0.721E-04  0.721E-04  0.321E-03  0.321E-03  0.101E-04  0.376E-03
     -6.025  0.146E-02  0.361E-03  0.668E-04  0.668E-04  0.298E-03  0.298E-03  0.918E-05  0.361E-03
     -6.015  0.133E-02  0.335E-03  0.594E-04  0.594E-04  0.267E-03  0.267E-03  0.794E-05  0.333E-03
     -6.005  0.114E-02  0.290E-03  0.502E-04  0.502E-04  0.228E-03  0.228E-03  0.643E-05  0.288E-03
     -5.995  0.969E-03  0.243E-03  0.427E-04  0.427E-04  0.196E-03  0.196E-03  0.525E-05  0.243E-03
     -5.985  0.957E-03  0.239E-03  0.419E-04  0.419E-04  0.194E-03  0.194E-03  0.514E-05  0.240E-03
     -5.975  0.947E-03  0.237E-03  0.411E-04  0.411E-04  0.192E-03  0.192E-03  0.505E-05  0.238E-03
     -5.965  0.938E-03  0.234E-03  0.405E-04  0.405E-04  0.191E-03  0.191E-03  0.498E-05  0.237E-03
     -5.955  0.932E-03  0.233E-03  0.399E-04  0.399E-04  0.190E-03  0.190E-03  0.492E-05  0.236E-03
     -5.945  0.928E-03  0.231E-03  0.394E-04  0.394E-04  0.189E-03  0.189E-03  0.489E-05  0.235E-03
     -5.935  0.926E-03  0.231E-03  0.390E-04  0.390E-04  0.188E-03  0.188E-03  0.487E-05  0.236E-03
     -5.925  0.926E-03  0.231E-03  0.387E-04  0.387E-04  0.188E-03  0.188E-03  0.488E-05  0.236E-03
     -5.915  0.927E-03  0.231E-03  0.385E-04  0.385E-04  0.188E-03  0.188E-03  0.492E-05  0.237E-03
     -5.905  0.931E-03  0.232E-03  0.384E-04  0.384E-04  0.189E-03  0.189E-03  0.498E-05  0.239E-03
     -5.895  0.937E-03  0.234E-03  0.385E-04  0.385E-04  0.190E-03  0.190E-03  0.507E-05  0.241E-03    
       

.. container:: formalpara-title

   **Input**

::

      # E (eV)  ldosup(E)  ldosdw(E) pdosup(E)  pdosdw(E)  pdosup(E)  pdosdw(E)  pdosup(E)  pdosdw(E)  pdosup(E)  pdosdw(E)  pdosup(E)  pdosdw(E) 
      4.547  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00  0.000E+00
      4.557  0.441E-09  0.000E+00  0.868E-10  0.000E+00  0.733E-10  0.000E+00  0.103E-09  0.000E+00  0.926E-10  0.000E+00  0.853E-10  0.000E+00
      4.567  0.353E-08  0.000E+00  0.694E-09  0.000E+00  0.586E-09  0.000E+00  0.824E-09  0.000E+00  0.741E-09  0.000E+00  0.683E-09  0.000E+00
      4.577  0.119E-07  0.000E+00  0.234E-08  0.000E+00  0.198E-08  0.000E+00  0.278E-08  0.000E+00  0.250E-08  0.000E+00  0.230E-08  0.000E+00
      4.587  0.282E-07  0.000E+00  0.555E-08  0.000E+00  0.469E-08  0.000E+00  0.659E-08  0.000E+00  0.593E-08  0.000E+00  0.546E-08  0.000E+00
      4.597  0.551E-07  0.000E+00  0.108E-07  0.000E+00  0.916E-08  0.000E+00  0.129E-07  0.000E+00  0.116E-07  0.000E+00  0.107E-07  0.000E+00
      4.607  0.952E-07  0.000E+00  0.187E-07  0.000E+00  0.158E-07  0.000E+00  0.222E-07  0.000E+00  0.200E-07  0.000E+00  0.184E-07  0.000E+00
      4.617  0.151E-06  0.000E+00  0.298E-07  0.000E+00  0.251E-07  0.000E+00  0.353E-07  0.000E+00  0.318E-07  0.000E+00  0.293E-07  0.000E+00
       

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="qespresso.pdos">
           <module id="qespresso.pdos">
               <list cmlx:templateRef="orbitalf">
                 <array dataType="xsd:double" dictRef="qex:eenergy" size="39">-6.275 -6.265 -6.255 -6.245 -6.235 -6.225 -6.215 -6.205 -6.195 -6.185 -6.175 -6.165 -6.155 -6.145 -6.135 -6.125 -6.115 -6.105 -6.095 -6.085 -6.075 -6.065 -6.055 -6.045 -6.035 -6.025 -6.015 -6.005 -5.995 -5.985 -5.975 -5.965 -5.955 -5.945 -5.935 -5.925 -5.915 -5.905 -5.895</array>
                 <array dataType="xsd:double" dictRef="qex:ldos" size="39">0.895E-02 0.844E-02 0.796E-02 0.752E-02 0.710E-02 0.670E-02 0.632E-02 0.598E-02 0.570E-02 0.541E-02 0.510E-02 0.477E-02 0.443E-02 0.408E-02 0.372E-02 0.335E-02 0.298E-02 0.261E-02 0.225E-02 0.193E-02 0.177E-02 0.167E-02 0.162E-02 0.159E-02 0.155E-02 0.146E-02 0.133E-02 0.114E-02 0.969E-03 0.957E-03 0.947E-03 0.938E-03 0.932E-03 0.928E-03 0.926E-03 0.926E-03 0.927E-03 0.931E-03 0.937E-03</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fz3" size="39">0.236E-02 0.220E-02 0.206E-02 0.192E-02 0.179E-02 0.167E-02 0.156E-02 0.145E-02 0.137E-02 0.129E-02 0.120E-02 0.111E-02 0.102E-02 0.923E-03 0.829E-03 0.739E-03 0.653E-03 0.573E-03 0.501E-03 0.443E-03 0.414E-03 0.397E-03 0.385E-03 0.379E-03 0.374E-03 0.361E-03 0.335E-03 0.290E-03 0.243E-03 0.239E-03 0.237E-03 0.234E-03 0.233E-03 0.231E-03 0.231E-03 0.231E-03 0.231E-03 0.232E-03 0.234E-03</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fz2x" size="39">0.383E-03 0.366E-03 0.349E-03 0.334E-03 0.320E-03 0.306E-03 0.293E-03 0.280E-03 0.270E-03 0.259E-03 0.248E-03 0.235E-03 0.221E-03 0.206E-03 0.190E-03 0.173E-03 0.155E-03 0.136E-03 0.116E-03 0.966E-04 0.866E-04 0.802E-04 0.766E-04 0.751E-04 0.721E-04 0.668E-04 0.594E-04 0.502E-04 0.427E-04 0.419E-04 0.411E-04 0.405E-04 0.399E-04 0.394E-04 0.390E-04 0.387E-04 0.385E-04 0.384E-04 0.385E-04</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fz2y" size="39">0.383E-03 0.366E-03 0.349E-03 0.334E-03 0.320E-03 0.306E-03 0.293E-03 0.280E-03 0.270E-03 0.259E-03 0.248E-03 0.235E-03 0.221E-03 0.206E-03 0.190E-03 0.173E-03 0.155E-03 0.136E-03 0.116E-03 0.966E-04 0.866E-04 0.802E-04 0.766E-04 0.751E-04 0.721E-04 0.668E-04 0.594E-04 0.502E-04 0.427E-04 0.419E-04 0.411E-04 0.405E-04 0.399E-04 0.394E-04 0.390E-04 0.387E-04 0.385E-04 0.384E-04 0.385E-04</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fz2.x2.y2" size="39">0.174E-02 0.166E-02 0.158E-02 0.150E-02 0.143E-02 0.136E-02 0.130E-02 0.124E-02 0.119E-02 0.114E-02 0.108E-02 0.102E-02 0.957E-03 0.889E-03 0.817E-03 0.742E-03 0.663E-03 0.580E-03 0.494E-03 0.414E-03 0.375E-03 0.353E-03 0.340E-03 0.333E-03 0.321E-03 0.298E-03 0.267E-03 0.228E-03 0.196E-03 0.194E-03 0.192E-03 0.191E-03 0.190E-03 0.189E-03 0.188E-03 0.188E-03 0.188E-03 0.189E-03 0.190E-03</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fzxy" size="39">0.174E-02 0.166E-02 0.158E-02 0.150E-02 0.143E-02 0.136E-02 0.130E-02 0.124E-02 0.119E-02 0.114E-02 0.108E-02 0.102E-02 0.957E-03 0.889E-03 0.817E-03 0.742E-03 0.663E-03 0.580E-03 0.494E-03 0.414E-03 0.375E-03 0.353E-03 0.340E-03 0.333E-03 0.321E-03 0.298E-03 0.267E-03 0.228E-03 0.196E-03 0.194E-03 0.192E-03 0.191E-03 0.190E-03 0.189E-03 0.188E-03 0.188E-03 0.188E-03 0.189E-03 0.190E-03</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fx.x2.3ys" size="39">0.391E-04 0.380E-04 0.371E-04 0.364E-04 0.357E-04 0.351E-04 0.345E-04 0.339E-04 0.333E-04 0.327E-04 0.319E-04 0.310E-04 0.299E-04 0.286E-04 0.270E-04 0.251E-04 0.229E-04 0.204E-04 0.174E-04 0.145E-04 0.127E-04 0.115E-04 0.108E-04 0.106E-04 0.101E-04 0.918E-05 0.794E-05 0.643E-05 0.525E-05 0.514E-05 0.505E-05 0.498E-05 0.492E-05 0.489E-05 0.487E-05 0.488E-05 0.492E-05 0.498E-05 0.507E-05</array>
                 <array dataType="xsd:double" dictRef="qex:pdos.fy.3x2.ys" size="39">0.230E-02 0.215E-02 0.201E-02 0.189E-02 0.177E-02 0.165E-02 0.155E-02 0.145E-02 0.137E-02 0.129E-02 0.121E-02 0.112E-02 0.103E-02 0.938E-03 0.847E-03 0.757E-03 0.671E-03 0.588E-03 0.512E-03 0.448E-03 0.418E-03 0.401E-03 0.389E-03 0.383E-03 0.376E-03 0.361E-03 0.333E-03 0.288E-03 0.243E-03 0.240E-03 0.238E-03 0.237E-03 0.236E-03 0.235E-03 0.236E-03 0.236E-03 0.237E-03 0.239E-03 0.241E-03</array>
               </list>
           </module>     
       </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="qespresso.pdos2">
           <module id="qespresso.pdos">
               <list cmlx:templateRef="orbitaldspin">
                   <array dataType="xsd:double" dictRef="qex:eenergy" size="8">4.547 4.557 4.567 4.577 4.587 4.597 4.607 4.617</array>
                   <array dataType="xsd:double" dictRef="qex:ldos.up" size="8">0.000E+00 0.441E-09 0.353E-08 0.119E-07 0.282E-07 0.551E-07 0.952E-07 0.151E-06</array>
                   <array dataType="xsd:double" dictRef="qex:ldos.down" size="8">0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dz2.up" size="8">0.000E+00 0.868E-10 0.694E-09 0.234E-08 0.555E-08 0.108E-07 0.187E-07 0.298E-07</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dz2.down" size="8">0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dzx.up" size="8">0.000E+00 0.733E-10 0.586E-09 0.198E-08 0.469E-08 0.916E-08 0.158E-07 0.251E-07</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dzx.down" size="8">0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dzy.up" size="8">0.000E+00 0.103E-09 0.824E-09 0.278E-08 0.659E-08 0.129E-07 0.222E-07 0.353E-07</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dzy.down" size="8">0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dx2.y2.up" size="8">0.000E+00 0.926E-10 0.741E-09 0.250E-08 0.593E-08 0.116E-07 0.200E-07 0.318E-07</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dx2.y2.down" size="8">0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dxy.up" size="8">0.000E+00 0.853E-10 0.683E-09 0.230E-08 0.546E-08 0.107E-07 0.184E-07 0.293E-07</array>
                   <array dataType="xsd:double" dictRef="qex:pdos.dxy.down" size="8">0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00 0.000E+00</array>           
               </list>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="orbitalf" pattern="\s*#\s+E\s+\(eV\)\s+ldos\(E\)(\s+pdos\(E\)){7}\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitalf" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos}{E,qex:pdos.fz3}{E,qex:pdos.fz2x}{E,qex:pdos.fz2y}{E,qex:pdos.fz2.x2.y2}{E,qex:pdos.fzxy}{E,qex:pdos.fx.x2.3ys}{E,qex:pdos.fy.3x2.ys}</record>
           </template>  <template id="orbitalfspin" pattern="\s*#\s+E\s+\(eV\)\s+ldosup\(E\)\s+ldosdw\(E\)(\s+pdosup\(E\)\s+pdosdw\(E\)){7}\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitalfspin" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos.up}{E,qex:ldos.down}{E,qex:pdos.fz3.up}{E,qex:pdos.fz3.down}{E,qex:pdos.fz2x.up}{E,qex:pdos.fz2x.down}{E,qex:pdos.fz2y.up}{E,qex:pdos.fz2y.down}{E,qex:pdos.fz2.x2.y2.up}{E,qex:pdos.fz2.x2.y2.down}{E,qex:pdos.fzxy.up}{E,qex:pdos.fzxy.down}{E,qex:pdos.fx.x2.3ys.up}{E,qex:pdos.fx.x2.3ys.down}{E,qex:pdos.fy.3x2.ys.up}{E,qex:pdos.fy.3x2.ys.down}</record>
           </template>  <template id="orbitald" pattern="\s*#\s+E\s+\(eV\)\s+ldos\(E\)(\s+pdos\(E\)){5}\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitald" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos}{E,qex:pdos.dz2}{E,qex:pdos.dzx}{E,qex:pdos.dzy}{E,qex:pdos.dx2.y2}{E,qex:pdos.dxy}</record>
           </template>  <template id="orbitaldspin" pattern="\s*#\s+E\s+\(eV\)\s+ldosup\(E\)\s+ldosdw\(E\)(\s+pdosup\(E\)\s+pdosdw\(E\)){5}\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitaldspin" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos.up}{E,qex:ldos.down}{E,qex:pdos.dz2.up}{E,qex:pdos.dz2.down}{E,qex:pdos.dzx.up}{E,qex:pdos.dzx.down}{E,qex:pdos.dzy.up}{E,qex:pdos.dzy.down}{E,qex:pdos.dx2.y2.up}{E,qex:pdos.dx2.y2.down}{E,qex:pdos.dxy.up}{E,qex:pdos.dxy.down}</record>          
           </template>  <template id="orbitalp" pattern="\s*#\s+E\s+\(eV\)\s+ldos\(E\)(\s+pdos\(E\)){3}\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitalp" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos}{E,qex:pdos.pz}{E,qex:pdos.px}{E,qex:pdos.py}</record>
           </template>  <template id="orbitalpspin" pattern="\s*#\s+E\s+\(eV\)\s+ldosup\(E\)\s+ldosdw\(E\)(\s+pdosup\(E\)\s+pdosdw\(E\)){3}\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitalpspin" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos.up}{E,qex:ldos.down}{E,qex:pdos.pz.up}{E,qex:pdos.pz.down}{E,qex:pdos.px.up}{E,qex:pdos.px.down}{E,qex:pdos.py.up}{E,qex:pdos.py.down}</record>
           </template>  <template id="orbitals" pattern="\s*#\s+E\s+\(eV\)\s+ldos\(E\)(\s+pdos\(E\))\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitals" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos}{E,qex:pdos.s}</record>
           </template>  <template id="orbitalsspin" pattern="\s*#\s+E\s+\(eV\)\s+ldosup\(E\)\s+ldosdw\(E\)(\s+pdosup\(E\)\s+pdosdw\(E\))\s*" endPattern="~" endOffset="1">    <record />    <record id="orbitalsspin" repeat="*" makeArray="true">{F,qex:eenergy}{E,qex:ldos.up}{E,qex:ldos.down}{E,qex:pdos.s.up}{E,qex:pdos.s.down}</record>
           </template>           
       </templateList>
   <transform process="pullup" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/Total.png
