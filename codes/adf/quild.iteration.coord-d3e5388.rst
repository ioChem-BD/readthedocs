.. _quild.iteration.coord-d3e5388:

quild.iteration.coord
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
   | *source*                                                                                                                   | ADF log                                                                                                                    |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | quild.iteration.coord                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | QUILD iteration geometry                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*New&#92;scoordinates&#92;s&#92;(angs&#92;)&#92;sand&#92;ssteps&#92;safter&#92;sIter&#92;_QUILD.\*                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | .*&#92;d+&#92;s*$&#92;s\*                                                                                                  |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | offset                                                                                                                     | -1                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 2                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | quild/quild.iteration.coord.xml                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. container:: formalpara-title

   **Input**

::

   --------------------------------------------------------
   New coordinates (angs) and steps after Iter_QUILD:     1
   --------------------------------------------------------

        1  C           0.706591105    -3.802679097    -1.608644212         0.003104907    -0.001155176     0.000963408
        2  C          -0.397688600    -3.284155488    -2.331243034         0.002591074    -0.002534765     0.000892041
        3  C           0.577149202    -4.109028971    -0.191056243         0.003278041    -0.000555805     0.001009513
        4  C           2.022733947    -3.303377329    -1.840656780         0.002734255    -0.000061716     0.000647007
        5  C          -0.159039063    -2.342679492    -3.372564243         0.001827564    -0.002672294     0.000458378
        6  C          -1.645568264    -3.198606267    -1.625456336         0.002473038    -0.003992512     0.000945691
        7  C          -0.647653368    -3.963856083     0.539287983         0.002844240    -0.003594060     0.001108382
        8  C           1.847424618    -3.839318529     0.410850464         0.003308111    -0.000150670     0.000739126
        9  C           2.246462173    -2.279165651    -2.801635493         0.001989796    -0.000114794     0.000327887
       10  C           2.729730989    -3.303799576    -0.578310086         0.002779666     0.000434566     0.000625614
       11  C          -1.080787734    -1.278337489    -3.656382772         0.000954457    -0.003481972     0.000099385
       12  C           1.161806731    -1.841714265    -3.606520814         0.001395078    -0.001191453     0.000647465
       13  C          -1.837528049    -3.633303178    -0.242594267         0.002527770    -0.004252727     0.001025274
       14  C          -2.533982316    -2.109544468    -1.899950978         0.001983944    -0.004351447     0.000654388
       15  SC         -0.945178864    -1.588219494     0.239599379         0.003209610    -0.004598579    -0.001507212
       16  C          -0.549868358    -3.468923509     1.933296574         0.002677390    -0.002080965     0.000698831
       17  C           1.928836271    -3.418684715     1.738715598         0.003031582     0.000474481     0.000536877
       18  C           3.262572284    -1.321496355    -2.512107643         0.002257862     0.000333422    -0.001216655
       19  C           3.658546869    -2.282539239    -0.235808302         0.001723876     0.001485618     0.000297999
       20  C          -2.262252855    -1.122786595    -2.894234294         0.001010199    -0.004355499     0.000362293
       21  C          -0.334313223    -0.128330511    -4.074180761         0.000095470    -0.002758412     0.000507290
       22  C           1.051725897    -0.475925650    -4.039138960         0.000397686    -0.001425504     0.000485336
       23  C          -2.882775500    -2.782300566     0.310673862         0.002511599    -0.003921555     0.000917669
       24  C          -3.251832452    -1.801744004    -0.688479068         0.002731051    -0.004055766     0.000868462
       25  C          -2.747703133     0.192184164    -2.658445748        -0.000433118    -0.004761773     0.000121166
       26  C          -0.762676330     1.191723509    -3.744904283        -0.000976006    -0.003217668     0.000650530
       27  C           2.023767030     0.495729567    -3.680510004        -0.000257543    -0.000598340     0.000132333
       28  C          -2.752622551    -2.274591805     1.641492941         0.002233546    -0.003154662     0.000383781
       29  C          -3.608192867    -0.442384691    -0.395369024        -0.005569220    -0.005585740    -0.000962141
       30  C          -1.617408638    -2.651105641     2.451847614         0.002266826    -0.002441121     0.000533496
       31  C           0.738285728    -3.238635539     2.505886270         0.002681907    -0.000034551     0.000068256
       32  C          -3.093302986    -0.919969520     1.958856248         0.001239494    -0.003463271    -0.000149712
       33  C          -1.362523155    -1.563139524     3.367073161         0.001063623    -0.001884796     0.000268655
       34  C           0.986801976    -2.157840969     3.438088258         0.001655618     0.000264682    -0.000102541
       35  C           2.888457339    -2.431859633     2.126950712         0.002146568     0.001454263     0.000248798
       36  C          -3.415537271     0.519941937    -1.419959372        -0.000079451    -0.005004445     0.000566236
       37  C          -2.012687482     1.338010137    -3.080628084        -0.001632459    -0.003984764    -0.000395517
       38  C          -3.787269034     0.015601415     1.028355501         0.000056625    -0.004198118    -0.000448790
       39  C          -3.180816238     1.921432372    -1.151950537        -0.000674475    -0.004996862     0.000559371
       40  SC         -1.048630557     1.501212100    -0.029591764        -0.000807953    -0.001098881     0.004965767
       41  C          -2.241123974     2.405099785    -2.119639552        -0.000909524    -0.004900569     0.000657217
       42  C           0.222897335     2.182890767    -3.492226592        -0.001720753    -0.002566294     0.000976364
       43  C          -3.156493840     2.399244104     0.192213473        -0.002201785    -0.003474232    -0.000187535
       44  C          -1.204039567     3.347816774    -1.765510386        -0.002142160    -0.003695866     0.000157598
       45  C          -2.277790862    -0.505898378     3.066350253        -0.000272585    -0.002691638     0.000665482
       46  C          -0.049995456    -1.277599346     3.840107201         0.000924855    -0.000548385    -0.000294354
       47  C          -1.905183352     0.854779624     3.255985598        -0.001385058    -0.002142744     0.000341107
       48  C          -3.270402530     1.407960985     1.221552911        -0.001187567    -0.003505714    -0.000591436
       49  C          -6.833392346    -0.957248319    -1.160903124         0.007024461     0.017904363    -0.005518933
       50  C          -6.869469677     0.323766014    -0.700379168         0.009965459     0.016843439    -0.001720023
       51  H          -7.259567794    -1.210887727    -2.131207948         0.017293660     0.023795357    -0.011749153
       52  H          -6.378696804    -1.772382528    -0.597203733        -0.011744937     0.012076660     0.001256998
       53  C          -6.310858126     0.780979419     0.520400417        -0.007672733     0.006359307     0.010396332
       54  H          -7.349652302     1.081910000    -1.325528975         0.030191083     0.023991582    -0.009021496
       55  C          -2.153075243     3.383788040     0.587474972        -0.003787747    -0.001751541    -0.000179683
       56  C           2.308080514    -1.665501676     3.207094058         0.001417770     0.001053499     0.000230443
       57  C           3.741642053    -1.833392386     1.157637663         0.002194180     0.001749390     0.000291267
       58  C           2.603534303    -0.287025261     3.368603425         0.000162966     0.001314891    -0.000153361
       59  C           0.278005704     0.082671707     4.114981521        -0.000354394    -0.000355257    -0.000126487
       60  C           0.002603532     3.241112303    -2.524910734        -0.002457242    -0.001425110    -0.000502439
       61  C           1.607636854     1.837040386    -3.464502755        -0.001391507    -0.000998670     0.000222708
       62  C          -1.146997441     3.846555896    -0.369045743        -0.003417412    -0.002346304    -0.000418336
       63  C           1.270012459     3.554273334    -1.946079437        -0.002702808    -0.000428945    -0.000541021
       64  C           2.261040092     2.674962279    -2.483239903        -0.001976697     0.000154801    -0.000403184
       65  C           3.152399070     0.036067129    -2.942421778         0.001369087     0.000449284    -0.001451570
       66  C           1.343783697     3.972258777    -0.616519609        -0.003258648    -0.000400881    -0.000520807
       67  C           3.301414442     2.175763709    -1.653819964        -0.001490114     0.001059025    -0.000551914
       68  C          -2.419214971     1.789842008     2.300925596        -0.001932451    -0.002660684    -0.000184548
       69  C          -1.708165150     2.975952762     1.915182601        -0.003678021    -0.001256541     0.000231295
       70  C           0.155746780     4.105499326     0.170380705        -0.003499791    -0.001910902    -0.000583032
       71  C          -0.385594217     3.198721905     2.430499200        -0.003197141    -0.001470883    -0.000566654
       72  C           0.533121105     3.826014334     1.553575070        -0.003484094    -0.001022565    -0.000548931
       73  C           2.418187011     3.545808803     0.225960889        -0.002922346     0.000616052    -0.000502239
       74  C          -0.647127660     1.142105028     3.826103615        -0.001408359    -0.001167515     0.000120402
       75  C          -5.574617873    -0.011549693     1.434578405        -0.006747330     0.001228987     0.005983427
       76  H          -5.766873324    -1.090182652     1.415862741        -0.013472834     0.002449599     0.003293567
       77  H          -5.526285541     0.381634435     2.456945020         0.001055952    -0.001687468     0.006674266
       78  C           3.821805733     0.869480376    -1.972390673        -0.000564035     0.001355990    -0.000754055
       79  C           3.385994815     2.625888247    -0.262043521        -0.001927101     0.001482610    -0.000507806
       80  SC          2.296651321     0.076477923    -0.108114360        -0.001564540     0.002876440    -0.001143391
       81  C           4.441174208     0.004699177    -0.997531490        -0.001006553     0.001995722    -0.000184881
       82  C           4.007639420    -1.341687703    -1.273332185        -0.000027237     0.001750982     0.000080894
       83  C           4.528688817     0.444544986     0.356817603        -0.000869617     0.002454165    -0.000469925
       84  C           1.915808240     3.480974238     1.581266351        -0.002981493     0.000853281    -0.000378455
       85  C           3.987668950     1.735127437     0.702270703        -0.000236316     0.002800957    -0.000295317
       86  C           2.387852593     2.491170621     2.487485219        -0.002269879     0.001259045    -0.000466110
       87  C           3.442250027     1.643586179     2.036984875        -0.002173380     0.001597123    -0.001237793
       88  C           4.168622681    -0.477187628     1.410275504         0.002100615     0.001910227     0.000408039
       89  C           0.104128025     2.299404013     3.418790740        -0.002359647    -0.000586428    -0.000114852
       90  C           3.551550885     0.285727942     2.470233273        -0.000904963     0.001769912    -0.001173875
       91  C           1.490234225     1.943832343     3.441728668        -0.002028847     0.000499875    -0.000543520
       92  C           1.595977125     0.577125641     3.875717844        -0.000762623     0.000572120    -0.000493354
       93  H          -6.368040460     1.855488076     0.715222053        -0.016808033     0.003822985     0.022269016
       94  N           0.277997613    -0.002442439     0.013715187        -0.003152036    -0.003768902    -0.028710086

       

.. container:: formalpara-title

   **Output text**

.. code:: xml

   <comment class="example.output" name="quild.iteration.coord">
          <module cmlx:lineCount="99" cmlx:templateRef="quild.iteration.coord">
           <scalar dataType="xsd:integer" dictRef="a:quildIteration">1</scalar>
           <molecule id="quild">
            <atomArray>
             <atom id="a1" elementType="C" x3="0.706591105" y3="-3.802679097" z3="-1.608644212">
              <scalar dataType="xsd:integer" dictRef="c:serial">1</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a2" elementType="C" x3="-0.3976886" y3="-3.284155488" z3="-2.331243034">
              <scalar dataType="xsd:integer" dictRef="c:serial">2</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a3" elementType="C" x3="0.577149202" y3="-4.109028971" z3="-0.191056243">
              <scalar dataType="xsd:integer" dictRef="c:serial">3</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a4" elementType="C" x3="2.022733947" y3="-3.303377329" z3="-1.84065678">
              <scalar dataType="xsd:integer" dictRef="c:serial">4</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a5" elementType="C" x3="-0.159039063" y3="-2.342679492" z3="-3.372564243">
              <scalar dataType="xsd:integer" dictRef="c:serial">5</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a6" elementType="C" x3="-1.645568264" y3="-3.198606267" z3="-1.625456336">
              <scalar dataType="xsd:integer" dictRef="c:serial">6</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a7" elementType="C" x3="-0.647653368" y3="-3.963856083" z3="0.539287983">
              <scalar dataType="xsd:integer" dictRef="c:serial">7</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a8" elementType="C" x3="1.847424618" y3="-3.839318529" z3="0.410850464">
              <scalar dataType="xsd:integer" dictRef="c:serial">8</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a9" elementType="C" x3="2.246462173" y3="-2.279165651" z3="-2.801635493">
              <scalar dataType="xsd:integer" dictRef="c:serial">9</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a10" elementType="C" x3="2.729730989" y3="-3.303799576" z3="-0.578310086">
              <scalar dataType="xsd:integer" dictRef="c:serial">10</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a11" elementType="C" x3="-1.080787734" y3="-1.278337489" z3="-3.656382772">
              <scalar dataType="xsd:integer" dictRef="c:serial">11</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a12" elementType="C" x3="1.161806731" y3="-1.841714265" z3="-3.606520814">
              <scalar dataType="xsd:integer" dictRef="c:serial">12</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a13" elementType="C" x3="-1.837528049" y3="-3.633303178" z3="-0.242594267">
              <scalar dataType="xsd:integer" dictRef="c:serial">13</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a14" elementType="C" x3="-2.533982316" y3="-2.109544468" z3="-1.899950978">
              <scalar dataType="xsd:integer" dictRef="c:serial">14</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a15" elementType="Sc" x3="-0.945178864" y3="-1.588219494" z3="0.239599379">
              <scalar dataType="xsd:integer" dictRef="c:serial">15</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">21</scalar>
             </atom>
             <atom id="a16" elementType="C" x3="-0.549868358" y3="-3.468923509" z3="1.933296574">
              <scalar dataType="xsd:integer" dictRef="c:serial">16</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a17" elementType="C" x3="1.928836271" y3="-3.418684715" z3="1.738715598">
              <scalar dataType="xsd:integer" dictRef="c:serial">17</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a18" elementType="C" x3="3.262572284" y3="-1.321496355" z3="-2.512107643">
              <scalar dataType="xsd:integer" dictRef="c:serial">18</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a19" elementType="C" x3="3.658546869" y3="-2.282539239" z3="-0.235808302">
              <scalar dataType="xsd:integer" dictRef="c:serial">19</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a20" elementType="C" x3="-2.262252855" y3="-1.122786595" z3="-2.894234294">
              <scalar dataType="xsd:integer" dictRef="c:serial">20</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a21" elementType="C" x3="-0.334313223" y3="-0.128330511" z3="-4.074180761">
              <scalar dataType="xsd:integer" dictRef="c:serial">21</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a22" elementType="C" x3="1.051725897" y3="-0.47592565" z3="-4.03913896">
              <scalar dataType="xsd:integer" dictRef="c:serial">22</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a23" elementType="C" x3="-2.8827755" y3="-2.782300566" z3="0.310673862">
              <scalar dataType="xsd:integer" dictRef="c:serial">23</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a24" elementType="C" x3="-3.251832452" y3="-1.801744004" z3="-0.688479068">
              <scalar dataType="xsd:integer" dictRef="c:serial">24</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a25" elementType="C" x3="-2.747703133" y3="0.192184164" z3="-2.658445748">
              <scalar dataType="xsd:integer" dictRef="c:serial">25</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a26" elementType="C" x3="-0.76267633" y3="1.191723509" z3="-3.744904283">
              <scalar dataType="xsd:integer" dictRef="c:serial">26</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a27" elementType="C" x3="2.02376703" y3="0.495729567" z3="-3.680510004">
              <scalar dataType="xsd:integer" dictRef="c:serial">27</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a28" elementType="C" x3="-2.752622551" y3="-2.274591805" z3="1.641492941">
              <scalar dataType="xsd:integer" dictRef="c:serial">28</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a29" elementType="C" x3="-3.608192867" y3="-0.442384691" z3="-0.395369024">
              <scalar dataType="xsd:integer" dictRef="c:serial">29</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a30" elementType="C" x3="-1.617408638" y3="-2.651105641" z3="2.451847614">
              <scalar dataType="xsd:integer" dictRef="c:serial">30</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a31" elementType="C" x3="0.738285728" y3="-3.238635539" z3="2.50588627">
              <scalar dataType="xsd:integer" dictRef="c:serial">31</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a32" elementType="C" x3="-3.093302986" y3="-0.91996952" z3="1.958856248">
              <scalar dataType="xsd:integer" dictRef="c:serial">32</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a33" elementType="C" x3="-1.362523155" y3="-1.563139524" z3="3.367073161">
              <scalar dataType="xsd:integer" dictRef="c:serial">33</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a34" elementType="C" x3="0.986801976" y3="-2.157840969" z3="3.438088258">
              <scalar dataType="xsd:integer" dictRef="c:serial">34</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a35" elementType="C" x3="2.888457339" y3="-2.431859633" z3="2.126950712">
              <scalar dataType="xsd:integer" dictRef="c:serial">35</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a36" elementType="C" x3="-3.415537271" y3="0.519941937" z3="-1.419959372">
              <scalar dataType="xsd:integer" dictRef="c:serial">36</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a37" elementType="C" x3="-2.012687482" y3="1.338010137" z3="-3.080628084">
              <scalar dataType="xsd:integer" dictRef="c:serial">37</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a38" elementType="C" x3="-3.787269034" y3="0.015601415" z3="1.028355501">
              <scalar dataType="xsd:integer" dictRef="c:serial">38</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a39" elementType="C" x3="-3.180816238" y3="1.921432372" z3="-1.151950537">
              <scalar dataType="xsd:integer" dictRef="c:serial">39</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a40" elementType="Sc" x3="-1.048630557" y3="1.5012121" z3="-0.029591764">
              <scalar dataType="xsd:integer" dictRef="c:serial">40</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">21</scalar>
             </atom>
             <atom id="a41" elementType="C" x3="-2.241123974" y3="2.405099785" z3="-2.119639552">
              <scalar dataType="xsd:integer" dictRef="c:serial">41</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a42" elementType="C" x3="0.222897335" y3="2.182890767" z3="-3.492226592">
              <scalar dataType="xsd:integer" dictRef="c:serial">42</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a43" elementType="C" x3="-3.15649384" y3="2.399244104" z3="0.192213473">
              <scalar dataType="xsd:integer" dictRef="c:serial">43</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a44" elementType="C" x3="-1.204039567" y3="3.347816774" z3="-1.765510386">
              <scalar dataType="xsd:integer" dictRef="c:serial">44</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a45" elementType="C" x3="-2.277790862" y3="-0.505898378" z3="3.066350253">
              <scalar dataType="xsd:integer" dictRef="c:serial">45</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a46" elementType="C" x3="-0.049995456" y3="-1.277599346" z3="3.840107201">
              <scalar dataType="xsd:integer" dictRef="c:serial">46</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a47" elementType="C" x3="-1.905183352" y3="0.854779624" z3="3.255985598">
              <scalar dataType="xsd:integer" dictRef="c:serial">47</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a48" elementType="C" x3="-3.27040253" y3="1.407960985" z3="1.221552911">
              <scalar dataType="xsd:integer" dictRef="c:serial">48</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a49" elementType="C" x3="-6.833392346" y3="-0.957248319" z3="-1.160903124">
              <scalar dataType="xsd:integer" dictRef="c:serial">49</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a50" elementType="C" x3="-6.869469677" y3="0.323766014" z3="-0.700379168">
              <scalar dataType="xsd:integer" dictRef="c:serial">50</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a51" elementType="H" x3="-7.259567794" y3="-1.210887727" z3="-2.131207948">
              <scalar dataType="xsd:integer" dictRef="c:serial">51</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
             </atom>
             <atom id="a52" elementType="H" x3="-6.378696804" y3="-1.772382528" z3="-0.597203733">
              <scalar dataType="xsd:integer" dictRef="c:serial">52</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
             </atom>
             <atom id="a53" elementType="C" x3="-6.310858126" y3="0.780979419" z3="0.520400417">
              <scalar dataType="xsd:integer" dictRef="c:serial">53</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a54" elementType="H" x3="-7.349652302" y3="1.08191" z3="-1.325528975">
              <scalar dataType="xsd:integer" dictRef="c:serial">54</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
             </atom>
             <atom id="a55" elementType="C" x3="-2.153075243" y3="3.38378804" z3="0.587474972">
              <scalar dataType="xsd:integer" dictRef="c:serial">55</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a56" elementType="C" x3="2.308080514" y3="-1.665501676" z3="3.207094058">
              <scalar dataType="xsd:integer" dictRef="c:serial">56</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a57" elementType="C" x3="3.741642053" y3="-1.833392386" z3="1.157637663">
              <scalar dataType="xsd:integer" dictRef="c:serial">57</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a58" elementType="C" x3="2.603534303" y3="-0.287025261" z3="3.368603425">
              <scalar dataType="xsd:integer" dictRef="c:serial">58</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a59" elementType="C" x3="0.278005704" y3="0.082671707" z3="4.114981521">
              <scalar dataType="xsd:integer" dictRef="c:serial">59</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a60" elementType="C" x3="0.002603532" y3="3.241112303" z3="-2.524910734">
              <scalar dataType="xsd:integer" dictRef="c:serial">60</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a61" elementType="C" x3="1.607636854" y3="1.837040386" z3="-3.464502755">
              <scalar dataType="xsd:integer" dictRef="c:serial">61</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a62" elementType="C" x3="-1.146997441" y3="3.846555896" z3="-0.369045743">
              <scalar dataType="xsd:integer" dictRef="c:serial">62</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a63" elementType="C" x3="1.270012459" y3="3.554273334" z3="-1.946079437">
              <scalar dataType="xsd:integer" dictRef="c:serial">63</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a64" elementType="C" x3="2.261040092" y3="2.674962279" z3="-2.483239903">
              <scalar dataType="xsd:integer" dictRef="c:serial">64</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a65" elementType="C" x3="3.15239907" y3="0.036067129" z3="-2.942421778">
              <scalar dataType="xsd:integer" dictRef="c:serial">65</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a66" elementType="C" x3="1.343783697" y3="3.972258777" z3="-0.616519609">
              <scalar dataType="xsd:integer" dictRef="c:serial">66</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a67" elementType="C" x3="3.301414442" y3="2.175763709" z3="-1.653819964">
              <scalar dataType="xsd:integer" dictRef="c:serial">67</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a68" elementType="C" x3="-2.419214971" y3="1.789842008" z3="2.300925596">
              <scalar dataType="xsd:integer" dictRef="c:serial">68</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a69" elementType="C" x3="-1.70816515" y3="2.975952762" z3="1.915182601">
              <scalar dataType="xsd:integer" dictRef="c:serial">69</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a70" elementType="C" x3="0.15574678" y3="4.105499326" z3="0.170380705">
              <scalar dataType="xsd:integer" dictRef="c:serial">70</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a71" elementType="C" x3="-0.385594217" y3="3.198721905" z3="2.4304992">
              <scalar dataType="xsd:integer" dictRef="c:serial">71</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a72" elementType="C" x3="0.533121105" y3="3.826014334" z3="1.55357507">
              <scalar dataType="xsd:integer" dictRef="c:serial">72</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a73" elementType="C" x3="2.418187011" y3="3.545808803" z3="0.225960889">
              <scalar dataType="xsd:integer" dictRef="c:serial">73</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a74" elementType="C" x3="-0.64712766" y3="1.142105028" z3="3.826103615">
              <scalar dataType="xsd:integer" dictRef="c:serial">74</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a75" elementType="C" x3="-5.574617873" y3="-0.011549693" z3="1.434578405">
              <scalar dataType="xsd:integer" dictRef="c:serial">75</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a76" elementType="H" x3="-5.766873324" y3="-1.090182652" z3="1.415862741">
              <scalar dataType="xsd:integer" dictRef="c:serial">76</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
             </atom>
             <atom id="a77" elementType="H" x3="-5.526285541" y3="0.381634435" z3="2.45694502">
              <scalar dataType="xsd:integer" dictRef="c:serial">77</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
             </atom>
             <atom id="a78" elementType="C" x3="3.821805733" y3="0.869480376" z3="-1.972390673">
              <scalar dataType="xsd:integer" dictRef="c:serial">78</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a79" elementType="C" x3="3.385994815" y3="2.625888247" z3="-0.262043521">
              <scalar dataType="xsd:integer" dictRef="c:serial">79</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a80" elementType="Sc" x3="2.296651321" y3="0.076477923" z3="-0.10811436">
              <scalar dataType="xsd:integer" dictRef="c:serial">80</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">21</scalar>
             </atom>
             <atom id="a81" elementType="C" x3="4.441174208" y3="0.004699177" z3="-0.99753149">
              <scalar dataType="xsd:integer" dictRef="c:serial">81</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a82" elementType="C" x3="4.00763942" y3="-1.341687703" z3="-1.273332185">
              <scalar dataType="xsd:integer" dictRef="c:serial">82</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a83" elementType="C" x3="4.528688817" y3="0.444544986" z3="0.356817603">
              <scalar dataType="xsd:integer" dictRef="c:serial">83</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a84" elementType="C" x3="1.91580824" y3="3.480974238" z3="1.581266351">
              <scalar dataType="xsd:integer" dictRef="c:serial">84</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a85" elementType="C" x3="3.98766895" y3="1.735127437" z3="0.702270703">
              <scalar dataType="xsd:integer" dictRef="c:serial">85</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a86" elementType="C" x3="2.387852593" y3="2.491170621" z3="2.487485219">
              <scalar dataType="xsd:integer" dictRef="c:serial">86</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a87" elementType="C" x3="3.442250027" y3="1.643586179" z3="2.036984875">
              <scalar dataType="xsd:integer" dictRef="c:serial">87</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a88" elementType="C" x3="4.168622681" y3="-0.477187628" z3="1.410275504">
              <scalar dataType="xsd:integer" dictRef="c:serial">88</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a89" elementType="C" x3="0.104128025" y3="2.299404013" z3="3.41879074">
              <scalar dataType="xsd:integer" dictRef="c:serial">89</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a90" elementType="C" x3="3.551550885" y3="0.285727942" z3="2.470233273">
              <scalar dataType="xsd:integer" dictRef="c:serial">90</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a91" elementType="C" x3="1.490234225" y3="1.943832343" z3="3.441728668">
              <scalar dataType="xsd:integer" dictRef="c:serial">91</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a92" elementType="C" x3="1.595977125" y3="0.577125641" z3="3.875717844">
              <scalar dataType="xsd:integer" dictRef="c:serial">92</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">6</scalar>
             </atom>
             <atom id="a93" elementType="H" x3="-6.36804046" y3="1.855488076" z3="0.715222053">
              <scalar dataType="xsd:integer" dictRef="c:serial">93</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">1</scalar>
             </atom>
             <atom id="a94" elementType="N" x3="0.277997613" y3="-0.002442439" z3="0.013715187">
              <scalar dataType="xsd:integer" dictRef="c:serial">94</scalar>
              <scalar dataType="xsd:integer" dictRef="cc:atomicNumber">7</scalar>
             </atom>
            </atomArray>
            <formula formalCharge="0" concise="C 84 H 6 N 1 Sc 3">
             <atomArray elementType="C H N Sc" count="84.0 6.0 1.0 3.0" />
            </formula>
            <bondArray>
             <bond atomRefs2="a1 a2" id="a1_a2" order="D" />
             <bond atomRefs2="a1 a3" id="a1_a3" order="S" />
             <bond atomRefs2="a1 a4" id="a1_a4" order="S" />
             <bond atomRefs2="a2 a5" id="a2_a5" order="S" />
             <bond atomRefs2="a2 a6" id="a2_a6" order="S" />
             <bond atomRefs2="a3 a7" id="a3_a7" order="S" />
             <bond atomRefs2="a3 a8" id="a3_a8" order="D" />
             <bond atomRefs2="a4 a9" id="a4_a9" order="S" />
             <bond atomRefs2="a4 a10" id="a4_a10" order="D" />
             <bond atomRefs2="a5 a11" id="a5_a11" order="D" />
             <bond atomRefs2="a5 a12" id="a5_a12" order="S" />
             <bond atomRefs2="a6 a13" id="a6_a13" order="S" />
             <bond atomRefs2="a6 a14" id="a6_a14" order="S" />
             <bond atomRefs2="a6 a15" id="a6_a15" order="S" />
             <bond atomRefs2="a7 a13" id="a7_a13" order="S" />
             <bond atomRefs2="a7 a15" id="a7_a15" order="S" />
             <bond atomRefs2="a7 a16" id="a7_a16" order="S" />
             <bond atomRefs2="a8 a10" id="a8_a10" order="S" />
             <bond atomRefs2="a8 a17" id="a8_a17" order="S" />
             <bond atomRefs2="a9 a12" id="a9_a12" order="D" />
             <bond atomRefs2="a9 a18" id="a9_a18" order="S" />
             <bond atomRefs2="a10 a19" id="a10_a19" order="S" />
             <bond atomRefs2="a11 a20" id="a11_a20" order="S" />
             <bond atomRefs2="a11 a21" id="a11_a21" order="S" />
             <bond atomRefs2="a12 a22" id="a12_a22" order="S" />
             <bond atomRefs2="a13 a15" id="a13_a15" order="S" />
             <bond atomRefs2="a13 a23" id="a13_a23" order="S" />
             <bond atomRefs2="a14 a20" id="a14_a20" order="D" />
             <bond atomRefs2="a14 a24" id="a14_a24" order="S" />
             <bond atomRefs2="a15 a16" id="a15_a16" order="S" />
             <bond atomRefs2="a15 a23" id="a15_a23" order="S" />
             <bond atomRefs2="a15 a24" id="a15_a24" order="S" />
             <bond atomRefs2="a15 a28" id="a15_a28" order="S" />
             <bond atomRefs2="a15 a30" id="a15_a30" order="S" />
             <bond atomRefs2="a15 a40" id="a15_a40" order="S" />
             <bond atomRefs2="a15 a94" id="a15_a94" order="S" />
             <bond atomRefs2="a16 a30" id="a16_a30" order="S" />
             <bond atomRefs2="a16 a31" id="a16_a31" order="S" />
             <bond atomRefs2="a17 a31" id="a17_a31" order="S" />
             <bond atomRefs2="a17 a35" id="a17_a35" order="D" />
             <bond atomRefs2="a18 a65" id="a18_a65" order="D" />
             <bond atomRefs2="a18 a82" id="a18_a82" order="S" />
             <bond atomRefs2="a19 a57" id="a19_a57" order="D" />
             <bond atomRefs2="a19 a82" id="a19_a82" order="S" />
             <bond atomRefs2="a20 a25" id="a20_a25" order="S" />
             <bond atomRefs2="a21 a22" id="a21_a22" order="D" />
             <bond atomRefs2="a21 a26" id="a21_a26" order="S" />
             <bond atomRefs2="a22 a27" id="a22_a27" order="S" />
             <bond atomRefs2="a23 a24" id="a23_a24" order="S" />
             <bond atomRefs2="a23 a28" id="a23_a28" order="S" />
             <bond atomRefs2="a24 a29" id="a24_a29" order="S" />
             <bond atomRefs2="a25 a36" id="a25_a36" order="D" />
             <bond atomRefs2="a25 a37" id="a25_a37" order="S" />
             <bond atomRefs2="a26 a37" id="a26_a37" order="D" />
             <bond atomRefs2="a26 a42" id="a26_a42" order="S" />
             <bond atomRefs2="a27 a61" id="a27_a61" order="D" />
             <bond atomRefs2="a27 a65" id="a27_a65" order="S" />
             <bond atomRefs2="a28 a30" id="a28_a30" order="S" />
             <bond atomRefs2="a28 a32" id="a28_a32" order="S" />
             <bond atomRefs2="a29 a36" id="a29_a36" order="S" />
             <bond atomRefs2="a29 a38" id="a29_a38" order="D" />
             <bond atomRefs2="a30 a33" id="a30_a33" order="S" />
             <bond atomRefs2="a31 a34" id="a31_a34" order="D" />
             <bond atomRefs2="a32 a38" id="a32_a38" order="S" />
             <bond atomRefs2="a32 a45" id="a32_a45" order="D" />
             <bond atomRefs2="a33 a45" id="a33_a45" order="S" />
             <bond atomRefs2="a33 a46" id="a33_a46" order="D" />
             <bond atomRefs2="a34 a46" id="a34_a46" order="S" />
             <bond atomRefs2="a34 a56" id="a34_a56" order="S" />
             <bond atomRefs2="a35 a56" id="a35_a56" order="S" />
             <bond atomRefs2="a35 a57" id="a35_a57" order="S" />
             <bond atomRefs2="a36 a39" id="a36_a39" order="S" />
             <bond atomRefs2="a37 a41" id="a37_a41" order="S" />
             <bond atomRefs2="a38 a48" id="a38_a48" order="S" />
             <bond atomRefs2="a39 a40" id="a39_a40" order="S" />
             <bond atomRefs2="a39 a41" id="a39_a41" order="S" />
             <bond atomRefs2="a39 a43" id="a39_a43" order="S" />
             <bond atomRefs2="a40 a41" id="a40_a41" order="S" />
             <bond atomRefs2="a40 a43" id="a40_a43" order="S" />
             <bond atomRefs2="a40 a44" id="a40_a44" order="S" />
             <bond atomRefs2="a40 a48" id="a40_a48" order="S" />
             <bond atomRefs2="a40 a55" id="a40_a55" order="S" />
             <bond atomRefs2="a40 a62" id="a40_a62" order="S" />
             <bond atomRefs2="a40 a69" id="a40_a69" order="S" />
             <bond atomRefs2="a40 a94" id="a40_a94" order="S" />
             <bond atomRefs2="a41 a44" id="a41_a44" order="S" />
             <bond atomRefs2="a42 a60" id="a42_a60" order="D" />
             <bond atomRefs2="a42 a61" id="a42_a61" order="S" />
             <bond atomRefs2="a43 a48" id="a43_a48" order="S" />
             <bond atomRefs2="a43 a55" id="a43_a55" order="S" />
             <bond atomRefs2="a44 a60" id="a44_a60" order="S" />
             <bond atomRefs2="a44 a62" id="a44_a62" order="S" />
             <bond atomRefs2="a45 a47" id="a45_a47" order="S" />
             <bond atomRefs2="a46 a59" id="a46_a59" order="S" />
             <bond atomRefs2="a47 a68" id="a47_a68" order="D" />
             <bond atomRefs2="a47 a74" id="a47_a74" order="S" />
             <bond atomRefs2="a48 a68" id="a48_a68" order="S" />
             <bond atomRefs2="a49 a50" id="a49_a50" order="D" />
             <bond atomRefs2="a49 a51" id="a49_a51" order="S" />
             <bond atomRefs2="a49 a52" id="a49_a52" order="S" />
             <bond atomRefs2="a50 a53" id="a50_a53" order="S" />
             <bond atomRefs2="a50 a54" id="a50_a54" order="S" />
             <bond atomRefs2="a53 a75" id="a53_a75" order="D" />
             <bond atomRefs2="a53 a93" id="a53_a93" order="S" />
             <bond atomRefs2="a55 a62" id="a55_a62" order="S" />
             <bond atomRefs2="a55 a69" id="a55_a69" order="S" />
             <bond atomRefs2="a56 a58" id="a56_a58" order="D" />
             <bond atomRefs2="a57 a88" id="a57_a88" order="S" />
             <bond atomRefs2="a58 a90" id="a58_a90" order="S" />
             <bond atomRefs2="a58 a92" id="a58_a92" order="S" />
             <bond atomRefs2="a59 a74" id="a59_a74" order="D" />
             <bond atomRefs2="a59 a92" id="a59_a92" order="S" />
             <bond atomRefs2="a60 a63" id="a60_a63" order="S" />
             <bond atomRefs2="a61 a64" id="a61_a64" order="S" />
             <bond atomRefs2="a62 a70" id="a62_a70" order="S" />
             <bond atomRefs2="a63 a64" id="a63_a64" order="S" />
             <bond atomRefs2="a63 a66" id="a63_a66" order="D" />
             <bond atomRefs2="a64 a67" id="a64_a67" order="D" />
             <bond atomRefs2="a65 a78" id="a65_a78" order="S" />
             <bond atomRefs2="a66 a70" id="a66_a70" order="S" />
             <bond atomRefs2="a66 a73" id="a66_a73" order="S" />
             <bond atomRefs2="a67 a78" id="a67_a78" order="S" />
             <bond atomRefs2="a67 a79" id="a67_a79" order="S" />
             <bond atomRefs2="a68 a69" id="a68_a69" order="S" />
             <bond atomRefs2="a69 a71" id="a69_a71" order="S" />
             <bond atomRefs2="a70 a72" id="a70_a72" order="D" />
             <bond atomRefs2="a71 a72" id="a71_a72" order="S" />
             <bond atomRefs2="a71 a89" id="a71_a89" order="D" />
             <bond atomRefs2="a72 a84" id="a72_a84" order="S" />
             <bond atomRefs2="a73 a79" id="a73_a79" order="D" />
             <bond atomRefs2="a73 a84" id="a73_a84" order="S" />
             <bond atomRefs2="a74 a89" id="a74_a89" order="S" />
             <bond atomRefs2="a75 a76" id="a75_a76" order="S" />
             <bond atomRefs2="a75 a77" id="a75_a77" order="S" />
             <bond atomRefs2="a78 a80" id="a78_a80" order="S" />
             <bond atomRefs2="a78 a81" id="a78_a81" order="S" />
             <bond atomRefs2="a79 a85" id="a79_a85" order="S" />
             <bond atomRefs2="a80 a81" id="a80_a81" order="S" />
             <bond atomRefs2="a80 a82" id="a80_a82" order="S" />
             <bond atomRefs2="a80 a83" id="a80_a83" order="S" />
             <bond atomRefs2="a80 a85" id="a80_a85" order="S" />
             <bond atomRefs2="a80 a88" id="a80_a88" order="S" />
             <bond atomRefs2="a80 a94" id="a80_a94" order="S" />
             <bond atomRefs2="a81 a82" id="a81_a82" order="S" />
             <bond atomRefs2="a81 a83" id="a81_a83" order="S" />
             <bond atomRefs2="a83 a85" id="a83_a85" order="S" />
             <bond atomRefs2="a83 a88" id="a83_a88" order="S" />
             <bond atomRefs2="a84 a86" id="a84_a86" order="D" />
             <bond atomRefs2="a85 a87" id="a85_a87" order="S" />
             <bond atomRefs2="a86 a87" id="a86_a87" order="S" />
             <bond atomRefs2="a86 a91" id="a86_a91" order="S" />
             <bond atomRefs2="a87 a90" id="a87_a90" order="D" />
             <bond atomRefs2="a88 a90" id="a88_a90" order="S" />
             <bond atomRefs2="a89 a91" id="a89_a91" order="S" />
             <bond atomRefs2="a91 a92" id="a91_a92" order="D" />
            </bondArray>
            <property dictRef="cml:molmass">
             <scalar dataType="xsd:double" units="unit:dalton">1163.8208699999998</scalar>
            </property>
           </molecule>
          </module> 
       </comment>

.. container:: formalpara-title

   **Template definition**

.. code:: xml

   <record repeat="1" />
   <record>\s*New\scoordinates\s\(angs\)\sand\ssteps\safter\sIter\_QUILD\:{I,a:quildIteration}</record>
   <record repeat="2" />
   <record id="atom" makeArray="true" repeat="*">{I,c:serial}{A,cc:elementType}{F,cc:x3}{F,cc:y3}{F,cc:z3}.*</record>
   <transform process="pullup" repeat="1" xpath=".//cml:scalar[@dictRef='a:quildIteration']" />
   <transform process="createMolecule" xpath=".//cml:list[@cmlx:templateRef='atom']/cml:array" id="quild" />
   <transform process="pullup" repeat="1" xpath=".//cml:molecule" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image1| image:: ../../imgs/Total.png
.. |image2| image:: ../../imgs/None.png
