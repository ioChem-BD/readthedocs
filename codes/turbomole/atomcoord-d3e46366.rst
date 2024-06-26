.. _atomcoord-d3e46366:

atomcoord
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
   | *source*                                                                                                                   | Turbomole log                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | atomcoord                                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Atomic coordinate, charge and isotop information                                                                           |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*&#92;+&#92;-+&#92;+&#92;s*$&#92;s*&#92;|&#92;sAtomic coordinate, charge and isotop                                  |
   |                                                                                                                            | information&#92;s&#92;|&#92;s*$&#92;s*&#92;+&#92;-+&#92;+&#92;s*.*$&#92;s\*                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s*center&#92;sof&#92;snuclear&#92;scharge.\*                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 1                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | atomcoord.xml                                                                                                              |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

                 +--------------------------------------------------+
                 | Atomic coordinate, charge and isotop information |
                 +--------------------------------------------------+


                 atomic coordinates              atom shells charge pseudo isotop
        0.00783626    0.00005587   -0.14130773    n      7    7.000    0     0
        2.70822787    2.70686248   -0.21748978    sc    15   21.000    0     0
        1.04906177   -3.67570357   -0.06247923    sc    15   21.000    0     0
       -3.69812652    0.97687983   -0.15811704    sc    15   21.000    0     0
       -4.32169744   -4.97395025   -4.12476803    c      7    6.000    0     0
       -2.03854015   -4.99235967   -5.60986553    c      7    6.000    0     0
       -1.94573473   -2.68088110   -7.04449314    c      7    6.000    0     0
       -4.16352418   -1.24380528   -6.45186689    c      7    6.000    0     0
       -5.63978287   -2.65384028   -4.64807236    c      7    6.000    0     0
       -7.10154380   -1.42802936   -2.73405978    c      7    6.000    0     0
       -7.26393056   -2.63622666   -0.32420300    c      7    6.000    0     0
       -5.94610521   -4.94964950    0.19813003    c      7    6.000    0     0
       -4.39333236   -6.08095417   -1.68502336    c      7    6.000    0     0
       -2.13479494   -7.32641516   -0.81742441    c      7    6.000    0     0
        0.13112892   -7.47940581   -2.30472823    c      7    6.000    0     0
        0.21937163   -6.13015070   -4.68713150    c      7    6.000    0     0
        2.56075737   -4.97919278   -5.35330149    c      7    6.000    0     0
        2.66696571   -2.68725575   -6.78968876    c      7    6.000    0     0
        0.39522556   -1.44886610   -7.57372926    c      7    6.000    0     0
        0.40821253    1.24551885   -7.67603204    c      7    6.000    0     0
       -1.81344383    2.68257415   -7.06270204    c      7    6.000    0     0
       -4.08771056    1.43989993   -6.35905933    c      7    6.000    0     0
       -5.64383747    2.64894299   -4.47962405    c      7    6.000    0     0
       -7.27838951    1.29799191   -2.76435689    c      7    6.000    0     0
       -7.52176644    2.79214670   -0.43837130    c      7    6.000    0     0
       -7.49492669    1.52167501    2.01462690    c      7    6.000    0     0
       -7.41842688   -1.19395406    2.00155451    c      7    6.000    0     0
       -6.15143656   -2.64516823    3.94271427    c      7    6.000    0     0
       -5.26525934   -4.95190956    2.83002118    c      7    6.000    0     0
       -2.97664829   -6.08927609    3.68137768    c      7    6.000    0     0
       -1.44707676   -7.35406114    1.80941346    c      7    6.000    0     0
        1.26467695   -7.56224823    1.98644747    c      7    6.000    0     0
        2.29015552   -7.68438215   -0.59255010    c      7    6.000    0     0
        4.56247098   -6.26241852   -1.20937045    c      7    6.000    0     0
        4.66499577   -5.00078185   -3.60569803    c      7    6.000    0     0
        6.06211699   -2.69353288   -3.98432827    c      7    6.000    0     0
        4.82287758   -1.27280864   -5.94105106    c      7    6.000    0     0
        4.74770803    1.41739769   -5.88012718    c      7    6.000    0     0
        2.56986315    2.65551757   -6.83796893    c      7    6.000    0     0
        1.69052419    4.97770157   -5.70969303    c      7    6.000    0     0
       -1.02540903    4.98873319   -5.85050220    c      7    6.000    0     0
       -2.48682291    6.12051178   -3.91027922    c      7    6.000    0     0
       -4.84065343    4.93039919   -3.27573889    c      7    6.000    0     0
       -5.91477922    5.00124179   -0.77666451    c      7    6.000    0     0
        4.29242220    4.96190676    4.12561670    c      7    6.000    0     0
        2.01721951    4.97230597    5.63006458    c      7    6.000    0     0
        1.93760651    2.67308065    7.06861042    c      7    6.000    0     0
        4.15962429    1.23022423    6.48650423    c      7    6.000    0     0
        5.60576479    2.62366881    4.66844700    c      7    6.000    0     0
        7.06482187    1.40790286    2.77113366    c      7    6.000    0     0
        7.29768288    2.69868603    0.37141200    c      7    6.000    0     0
        6.17474606    5.15427149   -0.15752410    c      7    6.000    0     0
        4.50756815    6.25096736    1.74934256    c      7    6.000    0     0
        2.20949456    7.40133430    0.86921373    c      7    6.000    0     0
       -0.09098797    7.39253403    2.33855245    c      7    6.000    0     0
       -0.23470596    6.12281285    4.71441331    c      7    6.000    0     0
       -2.59115553    5.00890637    5.41328109    c      7    6.000    0     0
       -2.67896314    2.68444250    6.81863136    c      7    6.000    0     0
       -0.40955882    1.44689696    7.60472952    c      7    6.000    0     0
        1.80409305   -2.68809133    7.09663384    c      7    6.000    0     0
        4.09804739   -1.46689843    6.40295198    c      7    6.000    0     0
        5.66883341   -2.69046837    4.58235132    c      7    6.000    0     0
        7.14844087   -1.28547587    2.78980582    c      7    6.000    0     0
        7.25300004   -2.70452414    0.47472749    c      7    6.000    0     0
        7.27822407   -1.48890765   -1.91783204    c      7    6.000    0     0
        7.29724074    1.22575094   -1.91095589    c      7    6.000    0     0
        6.08015868    2.65846532   -3.85406309    c      7    6.000    0     0
        5.36702160    5.07741168   -2.81840065    c      7    6.000    0     0
        2.98831813    6.14564835   -3.64938938    c      7    6.000    0     0
        1.48860064    7.39486984   -1.78055883    c      7    6.000    0     0
       -1.21907174    7.41409962   -1.92137065    c      7    6.000    0     0
       -2.18836818    7.41757235    0.61812127    c      7    6.000    0     0
       -4.48300482    6.14614658    1.24576191    c      7    6.000    0     0
       -4.66174699    5.00574728    3.67117440    c      7    6.000    0     0
       -6.07311840    2.68405960    4.01123906    c      7    6.000    0     0
       -4.82236915    1.26209301    5.97631540    c      7    6.000    0     0
       -4.77323702   -1.43206109    5.91987268    c      7    6.000    0     0
       -2.58860640   -2.67232259    6.88952988    c      7    6.000    0     0
       -1.70570245   -4.98120195    5.76488552    c      7    6.000    0     0
        1.01741866   -5.00181406    5.90246289    c      7    6.000    0     0
        2.51231412   -6.16356675    3.98540450    c      7    6.000    0     0
        4.85939953   -4.97984086    3.37586440    c      7    6.000    0     0
        5.84155625   -5.00730695    0.82534781    c      7    6.000    0     0
       -0.42107636   -1.24820715    7.69035721    c      7    6.000    0     0


        center of nuclear mass  :    0.00000000    0.00000000    0.00000000

        center of nuclear charge:   -0.00015670   -0.00002130    0.00115983

    

.. container:: formalpara-title

   **Input**

::

                 +--------------------------------------------------+
                 | Atomic coordinate, charge and isotop information |
                 +--------------------------------------------------+

                       atomic coordinates            atom    charge  isotop
            -1.79267786    1.79292956    0.21711881    c      6.000     0
            -4.64203010    1.72468295    0.02453055    c      6.000     0
            -0.72232011   -0.24797201   -0.93360778    o      8.000     0
            -0.54455624    3.43404491    1.23097559    o      8.000     0
            -5.21620927    1.96641451   -1.97654605    h      1.000     0
            -5.37835338   -0.13077601    0.65353692    h      1.000     0
            -5.45824156    3.26101743    1.17396391    h      1.000     0
             1.10943076   -0.01816375   -0.73154500    h      1.000     0
    
          center of nuclear mass  :   -1.87534367    1.63763387    0.11277683
          center of nuclear charge:   -1.99020725    1.61477345    0.09213276   
    

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="geometry.cycle">
         <module cmlx:lineCount="95" cmlx:templateRef="atomcoord">
             <molecule id="atomcoord">
              <atomArray>
               <atom id="a1" x3="0.00783626" y3="5.587E-5" z3="-0.14130773" elementType="N" />
               <atom id="a2" x3="2.70822787" y3="2.70686248" z3="-0.21748978" elementType="Sc" />
               <atom id="a3" x3="1.04906177" y3="-3.67570357" z3="-0.06247923" elementType="Sc" />
               <atom id="a4" x3="-3.69812652" y3="0.97687983" z3="-0.15811704" elementType="Sc" />
               <atom id="a5" x3="-4.32169744" y3="-4.97395025" z3="-4.12476803" elementType="C" />
               <atom id="a6" x3="-2.03854015" y3="-4.99235967" z3="-5.60986553" elementType="C" />
               <atom id="a7" x3="-1.94573473" y3="-2.6808811" z3="-7.04449314" elementType="C" />
               <atom id="a8" x3="-4.16352418" y3="-1.24380528" z3="-6.45186689" elementType="C" />
               <atom id="a9" x3="-5.63978287" y3="-2.65384028" z3="-4.64807236" elementType="C" />
               <atom id="a10" x3="-7.1015438" y3="-1.42802936" z3="-2.73405978" elementType="C" />
               <atom id="a11" x3="-7.26393056" y3="-2.63622666" z3="-0.324203" elementType="C" />
               <atom id="a12" x3="-5.94610521" y3="-4.9496495" z3="0.19813003" elementType="C" />
               <atom id="a13" x3="-4.39333236" y3="-6.08095417" z3="-1.68502336" elementType="C" />
               <atom id="a14" x3="-2.13479494" y3="-7.32641516" z3="-0.81742441" elementType="C" />
               <atom id="a15" x3="0.13112892" y3="-7.47940581" z3="-2.30472823" elementType="C" />
               <atom id="a16" x3="0.21937163" y3="-6.1301507" z3="-4.6871315" elementType="C" />
               <atom id="a17" x3="2.56075737" y3="-4.97919278" z3="-5.35330149" elementType="C" />
               <atom id="a18" x3="2.66696571" y3="-2.68725575" z3="-6.78968876" elementType="C" />
               <atom id="a19" x3="0.39522556" y3="-1.4488661" z3="-7.57372926" elementType="C" />
               <atom id="a20" x3="0.40821253" y3="1.24551885" z3="-7.67603204" elementType="C" />
               <atom id="a21" x3="-1.81344383" y3="2.68257415" z3="-7.06270204" elementType="C" />
               <atom id="a22" x3="-4.08771056" y3="1.43989993" z3="-6.35905933" elementType="C" />
               <atom id="a23" x3="-5.64383747" y3="2.64894299" z3="-4.47962405" elementType="C" />
               <atom id="a24" x3="-7.27838951" y3="1.29799191" z3="-2.76435689" elementType="C" />
               <atom id="a25" x3="-7.52176644" y3="2.7921467" z3="-0.4383713" elementType="C" />
               <atom id="a26" x3="-7.49492669" y3="1.52167501" z3="2.0146269" elementType="C" />
               <atom id="a27" x3="-7.41842688" y3="-1.19395406" z3="2.00155451" elementType="C" />
               <atom id="a28" x3="-6.15143656" y3="-2.64516823" z3="3.94271427" elementType="C" />
               <atom id="a29" x3="-5.26525934" y3="-4.95190956" z3="2.83002118" elementType="C" />
               <atom id="a30" x3="-2.97664829" y3="-6.08927609" z3="3.68137768" elementType="C" />
               <atom id="a31" x3="-1.44707676" y3="-7.35406114" z3="1.80941346" elementType="C" />
               <atom id="a32" x3="1.26467695" y3="-7.56224823" z3="1.98644747" elementType="C" />
               <atom id="a33" x3="2.29015552" y3="-7.68438215" z3="-0.5925501" elementType="C" />
               <atom id="a34" x3="4.56247098" y3="-6.26241852" z3="-1.20937045" elementType="C" />
               <atom id="a35" x3="4.66499577" y3="-5.00078185" z3="-3.60569803" elementType="C" />
               <atom id="a36" x3="6.06211699" y3="-2.69353288" z3="-3.98432827" elementType="C" />
               <atom id="a37" x3="4.82287758" y3="-1.27280864" z3="-5.94105106" elementType="C" />
               <atom id="a38" x3="4.74770803" y3="1.41739769" z3="-5.88012718" elementType="C" />
               <atom id="a39" x3="2.56986315" y3="2.65551757" z3="-6.83796893" elementType="C" />
               <atom id="a40" x3="1.69052419" y3="4.97770157" z3="-5.70969303" elementType="C" />
               <atom id="a41" x3="-1.02540903" y3="4.98873319" z3="-5.8505022" elementType="C" />
               <atom id="a42" x3="-2.48682291" y3="6.12051178" z3="-3.91027922" elementType="C" />
               <atom id="a43" x3="-4.84065343" y3="4.93039919" z3="-3.27573889" elementType="C" />
               <atom id="a44" x3="-5.91477922" y3="5.00124179" z3="-0.77666451" elementType="C" />
               <atom id="a45" x3="4.2924222" y3="4.96190676" z3="4.1256167" elementType="C" />
               <atom id="a46" x3="2.01721951" y3="4.97230597" z3="5.63006458" elementType="C" />
               <atom id="a47" x3="1.93760651" y3="2.67308065" z3="7.06861042" elementType="C" />
               <atom id="a48" x3="4.15962429" y3="1.23022423" z3="6.48650423" elementType="C" />
               <atom id="a49" x3="5.60576479" y3="2.62366881" z3="4.668447" elementType="C" />
               <atom id="a50" x3="7.06482187" y3="1.40790286" z3="2.77113366" elementType="C" />
               <atom id="a51" x3="7.29768288" y3="2.69868603" z3="0.371412" elementType="C" />
               <atom id="a52" x3="6.17474606" y3="5.15427149" z3="-0.1575241" elementType="C" />
               <atom id="a53" x3="4.50756815" y3="6.25096736" z3="1.74934256" elementType="C" />
               <atom id="a54" x3="2.20949456" y3="7.4013343" z3="0.86921373" elementType="C" />
               <atom id="a55" x3="-0.09098797" y3="7.39253403" z3="2.33855245" elementType="C" />
               <atom id="a56" x3="-0.23470596" y3="6.12281285" z3="4.71441331" elementType="C" />
               <atom id="a57" x3="-2.59115553" y3="5.00890637" z3="5.41328109" elementType="C" />
               <atom id="a58" x3="-2.67896314" y3="2.6844425" z3="6.81863136" elementType="C" />
               <atom id="a59" x3="-0.40955882" y3="1.44689696" z3="7.60472952" elementType="C" />
               <atom id="a60" x3="1.80409305" y3="-2.68809133" z3="7.09663384" elementType="C" />
               <atom id="a61" x3="4.09804739" y3="-1.46689843" z3="6.40295198" elementType="C" />
               <atom id="a62" x3="5.66883341" y3="-2.69046837" z3="4.58235132" elementType="C" />
               <atom id="a63" x3="7.14844087" y3="-1.28547587" z3="2.78980582" elementType="C" />
               <atom id="a64" x3="7.25300004" y3="-2.70452414" z3="0.47472749" elementType="C" />
               <atom id="a65" x3="7.27822407" y3="-1.48890765" z3="-1.91783204" elementType="C" />
               <atom id="a66" x3="7.29724074" y3="1.22575094" z3="-1.91095589" elementType="C" />
               <atom id="a67" x3="6.08015868" y3="2.65846532" z3="-3.85406309" elementType="C" />
               <atom id="a68" x3="5.3670216" y3="5.07741168" z3="-2.81840065" elementType="C" />
               <atom id="a69" x3="2.98831813" y3="6.14564835" z3="-3.64938938" elementType="C" />
               <atom id="a70" x3="1.48860064" y3="7.39486984" z3="-1.78055883" elementType="C" />
               <atom id="a71" x3="-1.21907174" y3="7.41409962" z3="-1.92137065" elementType="C" />
               <atom id="a72" x3="-2.18836818" y3="7.41757235" z3="0.61812127" elementType="C" />
               <atom id="a73" x3="-4.48300482" y3="6.14614658" z3="1.24576191" elementType="C" />
               <atom id="a74" x3="-4.66174699" y3="5.00574728" z3="3.6711744" elementType="C" />
               <atom id="a75" x3="-6.0731184" y3="2.6840596" z3="4.01123906" elementType="C" />
               <atom id="a76" x3="-4.82236915" y3="1.26209301" z3="5.9763154" elementType="C" />
               <atom id="a77" x3="-4.77323702" y3="-1.43206109" z3="5.91987268" elementType="C" />
               <atom id="a78" x3="-2.5886064" y3="-2.67232259" z3="6.88952988" elementType="C" />
               <atom id="a79" x3="-1.70570245" y3="-4.98120195" z3="5.76488552" elementType="C" />
               <atom id="a80" x3="1.01741866" y3="-5.00181406" z3="5.90246289" elementType="C" />
               <atom id="a81" x3="2.51231412" y3="-6.16356675" z3="3.9854045" elementType="C" />
               <atom id="a82" x3="4.85939953" y3="-4.97984086" z3="3.3758644" elementType="C" />
               <atom id="a83" x3="5.84155625" y3="-5.00730695" z3="0.82534781" elementType="C" />
               <atom id="a84" x3="-0.42107636" y3="-1.24820715" z3="7.69035721" elementType="C" />
              </atomArray>
              <formula formalCharge="0" concise="C 80 N 1 Sc 3">
               <atomArray elementType="C N Sc" count="80.0 1.0 3.0" />
              </formula>
              <property dictRef="cml:molmass">
               <scalar dataType="xsd:double" units="unit:dalton">1109.73043</scalar>
              </property>
             </molecule>
             <list cmlx:templateRef="centnuclmass">
              <scalar dataType="xsd:double" dictRef="cc:x3">0.0</scalar>
              <scalar dataType="xsd:double" dictRef="cc:y3">0.0</scalar>
              <scalar dataType="xsd:double" dictRef="cc:z3">0.0</scalar>
             </list>
             <list cmlx:templateRef="centnuclcharge">
              <scalar dataType="xsd:double" dictRef="cc:x3">-1.567E-4</scalar>
              <scalar dataType="xsd:double" dictRef="cc:y3">-2.13E-5</scalar>
              <scalar dataType="xsd:double" dictRef="cc:z3">0.00115983</scalar>
            </list>
        </module>
     </comment>

.. container:: formalpara-title

   **Output text**

.. code:: xml
   :number-lines:

   <comment class="example.output" id="geometry.cycle2">
         <module cmlx:lineCount="16" cmlx:templateRef="atomcoord">
           <module cmlx:templateRef="atomcoord">
               <molecule id="atomcoord">
                  <atomArray>
                     <atom elementType="C" id="a1" x3="-1.79267786" y3="1.79292956" z3="0.21711881" />
                     <atom elementType="C" id="a2" x3="-4.6420301" y3="1.72468295" z3="0.02453055" />
                     <atom elementType="O" id="a3" x3="-0.72232011" y3="-0.24797201" z3="-0.93360778" />
                     <atom elementType="O" id="a4" x3="-0.54455624" y3="3.43404491" z3="1.23097559" />
                     <atom elementType="H" id="a5" x3="-5.21620927" y3="1.96641451" z3="-1.97654605" />
                     <atom elementType="H" id="a6" x3="-5.37835338" y3="-0.13077601" z3="0.65353692" />
                     <atom elementType="H" id="a7" x3="-5.45824156" y3="3.26101743" z3="1.17396391" />
                     <atom elementType="H" id="a8" x3="1.10943076" y3="-0.01816375" z3="-0.731545" />
                  </atomArray>
                  <formula concise="C 2 H 4 O 2">
                     <atomArray count="2 4 2" elementType="C H O" />
                  </formula>
                  <property dictRef="cml:molmass">
                     <scalar units="unit:dalton">56.0202</scalar>
                  </property>
               </molecule>            
               <list cmlx:templateRef="centnuclmass">
                  <scalar dataType="xsd:double" dictRef="cc:x3">-1.87534367</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:y3">1.63763387</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:z3">0.11277683</scalar>
               </list>
               <list cmlx:templateRef="centnuclcharge">
                  <scalar dataType="xsd:double" dictRef="cc:x3">-1.99020725</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:y3">1.61477345</scalar>
                  <scalar dataType="xsd:double" dictRef="cc:z3">0.09213276</scalar>
               </list>
               </module>
           </module>
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml
   :number-lines:

   <templateList>  <template id="withshells" pattern="\s*atomic\s*coordinates\s*atom\s*shells\s*charge\s*pseudo\s*isotop.*" endPattern="~">    <record repeat="1" />    <record id="atom" makeArray="true" repeat="*">{F,cc:x3}{F,cc:y3}{F,cc:z3}{A,cc:atomLabel}{I,t:shells}{F,cc:elementType}{I,t:pseudo}{I,t:isotop}</record>    <record repeat="2" />    <record id="centnuclmass">\s*center of nuclear mass\s*:\s*{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>    <record />    <record id="centnuclcharge">\s*center of nuclear charge:\s*{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>    <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:x3']" args="operator=multiply operand=0.529177" />    <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:y3']" args="operator=multiply operand=0.529177" />    <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:z3']" args="operator=multiply operand=0.529177" />    <transform process="createMolecule" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:array" id="atomcoord" />    <transform process="pullup" xpath=".//cml:list/cml:list/cml:scalar" />    <transform process="pullup" xpath=".//cml:molecule" />    <transform process="delete" xpath=".//cml:atom/cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />  
           </template>  <template id="noshells" pattern="\s*atomic\s*coordinates\s*atom\s*charge\s*isotop.*" endPattern="~">    <record repeat="1" />    <record id="atom" makeArray="true" repeat="*">{F,cc:x3}{F,cc:y3}{F,cc:z3}{A,cc:atomLabel}{F,cc:elementType}{I,t:isotop}</record>    <record repeat="1" />    <record id="centnuclmass">\s*center of nuclear mass\s*:\s*{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>    <record id="centnuclcharge">\s*center of nuclear charge:\s*{F,cc:x3}{F,cc:y3}{F,cc:z3}</record>    <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:x3']" args="operator=multiply operand=0.529177" />    <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:y3']" args="operator=multiply operand=0.529177" />    <transform process="operateArray" xpath=".//cml:array[@dictRef='cc:z3']" args="operator=multiply operand=0.529177" />    <transform process="createMolecule" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:array" id="atomcoord" />    <transform process="pullup" xpath=".//cml:list/cml:list/cml:scalar" />    <transform process="pullup" xpath=".//cml:molecule" />    <transform process="delete" xpath=".//cml:atom/cml:scalar" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />    <transform process="delete" xpath=".//cml:list[count(*)=0]" />     
           </template>
       </templateList>
   <transform process="pullup" xpath=".//cml:molecule" />
   <transform process="pullup" xpath=".//cml:module/cml:list" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
