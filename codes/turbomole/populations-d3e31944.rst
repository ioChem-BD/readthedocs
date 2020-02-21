.. _populations-d3e31944:

populations
===========

.. table:: Implementation level

   +-----------------------------------+-----------------------------------+
   | Type                              | Status                            |
   +===================================+===================================+
   | CML extraction template           | |image0|                          |
   +-----------------------------------+-----------------------------------+
   | HTML5 representation              | |image1|                          |
   +-----------------------------------+-----------------------------------+

.. table:: Template attributes

   +-----------------------------------+-----------------------------------+
   | Attribute                         | Value                             |
   +===================================+===================================+
   | *source*                          | Turbomole log                     |
   +-----------------------------------+-----------------------------------+
   | id                                | populations                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | \\s*atom\s*charge.\*              |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*\w.*$\s\*                     |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 1                                 |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | population/populations.xml        |
   +-----------------------------------+-----------------------------------+

**Input.**

::

    atom      charge    n(s)      n(p)      n(d)      n(f)      n(g)
      1c     -0.05111   3.23232   2.77390   0.04488
      2c      0.05267   3.24420   2.65701   0.04612
      3c     -0.04145   3.22136   2.77473   0.04535
      4c     -0.05618   3.23473   2.77618   0.04528
      5c     -0.03783   3.22845   2.76448   0.04491
      6c      0.01836   3.25271   2.68472   0.04422
      7c     -0.01972   3.23112   2.74372   0.04488
      8c     -0.02691   3.22806   2.75448   0.04437
      9c      0.00406   3.24437   2.70298   0.04860
     10c     -0.01023   3.24625   2.71758   0.04640
     11c     -0.01023   3.24625   2.71758   0.04640
     12c     -0.05618   3.23473   2.77618   0.04528
     13c     -0.05111   3.23232   2.77390   0.04488
     14c      0.05267   3.24420   2.65701   0.04612
     15c     -0.04145   3.22136   2.77473   0.04535
     16c     -0.06107   3.25312   2.76244   0.04551
     17c     -0.00220   3.26197   2.69741   0.04282
     18c     -0.00220   3.26197   2.69741   0.04282
     19c      0.01836   3.25271   2.68472   0.04422
     20c     -0.03783   3.22845   2.76448   0.04491
     21c     -0.01972   3.23112   2.74372   0.04488
     22c     -0.11931   3.29464   2.77667   0.04800
     23c      0.13552   3.32267   2.48978   0.05204
     24c     -0.11931   3.29464   2.77667   0.04800
     25c     -0.11931   3.29464   2.77667   0.04800
     26c     -0.01023   3.24625   2.71758   0.04640
     27c     -0.02691   3.22806   2.75448   0.04437
     28c      0.00406   3.24437   2.70298   0.04860
     29c     -0.01023   3.24625   2.71758   0.04640
     30c     -0.05111   3.23232   2.77390   0.04488
     31c      0.05267   3.24420   2.65701   0.04612
     32c     -0.04145   3.22136   2.77473   0.04535
     33c     -0.05618   3.23473   2.77618   0.04528
     34c     -0.01023   3.24625   2.71758   0.04640
     35c      0.00406   3.24437   2.70298   0.04860
     36c     -0.01023   3.24625   2.71758   0.04640
     37c     -0.02691   3.22806   2.75448   0.04437
     38c     -0.04145   3.22136   2.77473   0.04535
     39c     -0.05111   3.23232   2.77390   0.04488
     40c      0.05267   3.24420   2.65701   0.04612
     41c     -0.05618   3.23473   2.77618   0.04528
     42c     -0.05618   3.23473   2.77618   0.04528
     43c      0.05267   3.24420   2.65701   0.04612
     44c     -0.04145   3.22136   2.77473   0.04535
     45c     -0.05111   3.23232   2.77390   0.04488
     46c     -0.05618   3.23473   2.77618   0.04528
     47c      0.05267   3.24420   2.65701   0.04612
     48c     -0.04145   3.22136   2.77473   0.04535
     49c     -0.05111   3.23232   2.77390   0.04488
     50c     -0.03783   3.22845   2.76448   0.04491
     51c      0.01836   3.25271   2.68472   0.04422
     52c     -0.01972   3.23112   2.74372   0.04488
     53c      0.03807   3.20095   2.71311   0.04787
     54c     -0.05619   3.22690   2.78163   0.04766
     55c     -0.06107   3.25312   2.76244   0.04551
     56c     -0.00220   3.26197   2.69741   0.04282
     57c     -0.00220   3.26197   2.69741   0.04282
     58c     -0.06107   3.25312   2.76244   0.04551
     59c     -0.03783   3.22845   2.76448   0.04491
     60c     -0.01972   3.23112   2.74372   0.04488
     61c      0.01836   3.25271   2.68472   0.04422
     62c     -0.01479   3.28840   2.67578   0.05061
     63c     -0.01479   3.28840   2.67578   0.05061
     64c     -0.01479   3.28840   2.67578   0.05061
     65c     -0.01479   3.28840   2.67578   0.05061
     66c     -0.05619   3.22690   2.78163   0.04766
     67c     -0.06107   3.25312   2.76244   0.04551
     68c      0.03807   3.20095   2.71311   0.04787
     69c     -0.03783   3.22845   2.76448   0.04491
     70c     -0.06107   3.25312   2.76244   0.04551
     71c     -0.00220   3.26197   2.69741   0.04282
     72c     -0.00220   3.26197   2.69741   0.04282
     73c      0.01836   3.25271   2.68472   0.04422
     74c     -0.01972   3.23112   2.74372   0.04488
     75c      0.03807   3.20095   2.71311   0.04787
     76c     -0.05619   3.22690   2.78163   0.04766
     77c     -0.01972   3.23112   2.74372   0.04488
     78c      0.01836   3.25271   2.68472   0.04422
     79c     -0.03783   3.22845   2.76448   0.04491
     80c     -0.01479   3.28840   2.67578   0.05061
     81c     -0.01479   3.28840   2.67578   0.05061
     82c     -0.06107   3.25312   2.76244   0.04551
     83sc     0.90189   2.11188   6.17957   1.72652   0.08014
     84sc     0.78471   2.11747   6.16853   1.83477   0.09452  
     
       

**Input.**

::

   atom          charge    n(s)      n(p)      n(d)      n(f)      n(g)
     1 c          0.38831   2.82152   2.78257   0.00760   0.00000   0.00000
     2 c         -0.28006   2.96303   3.31384   0.00319   0.00000   0.00000
     3 c         -0.29805   2.95382   3.34117   0.00306   0.00000   0.00000
     4 c          0.30863   2.81657   2.86796   0.00684   0.00000   0.00000
     5 c         -0.26135   2.95502   3.30331   0.00302   0.00000   0.00000
     6 c         -0.27931   2.96474   3.31137   0.00321   0.00000   0.00000
     7 h          0.23929   0.76071   0.00000   0.00000   0.00000   0.00000
     8 h          0.22228   0.77772   0.00000   0.00000   0.00000   0.00000
     9 h          0.23891   0.76109   0.00000   0.00000   0.00000   0.00000
    10 h          0.23958   0.76042   0.00000   0.00000   0.00000   0.00000
    11 f         -0.32883   3.82079   5.50537   0.00267   0.00000   0.00000
    12 o         -0.64730   3.65574   4.98631   0.00526   0.00000   0.00000
    13 h          0.45789   0.54211   0.00000   0.00000   0.00000   0.00000
       
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="populations">   
           <module cmlx:templateRef="populations">
               <array dataType="xsd:integer" size="84" dictRef="cc:serial">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79 80 81 82 83 84</array>
               <array dataType="xsd:string" size="84" dictRef="cc:atomType">c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c c sc sc</array>
               <array dataType="xsd:double" size="84" dictRef="x:charge">-0.05111 0.05267 -0.04145 -0.05618 -0.03783 0.01836 -0.01972 -0.02691 0.00406 -0.01023 -0.01023 -0.05618 -0.05111 0.05267 -0.04145 -0.06107 -0.0022 -0.0022 0.01836 -0.03783 -0.01972 -0.11931 0.13552 -0.11931 -0.11931 -0.01023 -0.02691 0.00406 -0.01023 -0.05111 0.05267 -0.04145 -0.05618 -0.01023 0.00406 -0.01023 -0.02691 -0.04145 -0.05111 0.05267 -0.05618 -0.05618 0.05267 -0.04145 -0.05111 -0.05618 0.05267 -0.04145 -0.05111 -0.03783 0.01836 -0.01972 0.03807 -0.05619 -0.06107 -0.0022 -0.0022 -0.06107 -0.03783 -0.01972 0.01836 -0.01479 -0.01479 -0.01479 -0.01479 -0.05619 -0.06107 0.03807 -0.03783 -0.06107 -0.0022 -0.0022 0.01836 -0.01972 0.03807 -0.05619 -0.01972 0.01836 -0.03783 -0.01479 -0.01479 -0.06107 0.90189 0.78471</array>
               <array dataType="xsd:double" size="84" dictRef="x:s">3.23232 3.2442 3.22136 3.23473 3.22845 3.25271 3.23112 3.22806 3.24437 3.24625 3.24625 3.23473 3.23232 3.2442 3.22136 3.25312 3.26197 3.26197 3.25271 3.22845 3.23112 3.29464 3.32267 3.29464 3.29464 3.24625 3.22806 3.24437 3.24625 3.23232 3.2442 3.22136 3.23473 3.24625 3.24437 3.24625 3.22806 3.22136 3.23232 3.2442 3.23473 3.23473 3.2442 3.22136 3.23232 3.23473 3.2442 3.22136 3.23232 3.22845 3.25271 3.23112 3.20095 3.2269 3.25312 3.26197 3.26197 3.25312 3.22845 3.23112 3.25271 3.2884 3.2884 3.2884 3.2884 3.2269 3.25312 3.20095 3.22845 3.25312 3.26197 3.26197 3.25271 3.23112 3.20095 3.2269 3.23112 3.25271 3.22845 3.2884 3.2884 3.25312 2.11188 2.11747</array>
               <array dataType="xsd:double" size="84" dictRef="x:p">2.7739 2.65701 2.77473 2.77618 2.76448 2.68472 2.74372 2.75448 2.70298 2.71758 2.71758 2.77618 2.7739 2.65701 2.77473 2.76244 2.69741 2.69741 2.68472 2.76448 2.74372 2.77667 2.48978 2.77667 2.77667 2.71758 2.75448 2.70298 2.71758 2.7739 2.65701 2.77473 2.77618 2.71758 2.70298 2.71758 2.75448 2.77473 2.7739 2.65701 2.77618 2.77618 2.65701 2.77473 2.7739 2.77618 2.65701 2.77473 2.7739 2.76448 2.68472 2.74372 2.71311 2.78163 2.76244 2.69741 2.69741 2.76244 2.76448 2.74372 2.68472 2.67578 2.67578 2.67578 2.67578 2.78163 2.76244 2.71311 2.76448 2.76244 2.69741 2.69741 2.68472 2.74372 2.71311 2.78163 2.74372 2.68472 2.76448 2.67578 2.67578 2.76244 6.17957 6.16853</array>
               <array dataType="xsd:double" size="84" dictRef="x:d">0.04488 0.04612 0.04535 0.04528 0.04491 0.04422 0.04488 0.04437 0.0486 0.0464 0.0464 0.04528 0.04488 0.04612 0.04535 0.04551 0.04282 0.04282 0.04422 0.04491 0.04488 0.048 0.05204 0.048 0.048 0.0464 0.04437 0.0486 0.0464 0.04488 0.04612 0.04535 0.04528 0.0464 0.0486 0.0464 0.04437 0.04535 0.04488 0.04612 0.04528 0.04528 0.04612 0.04535 0.04488 0.04528 0.04612 0.04535 0.04488 0.04491 0.04422 0.04488 0.04787 0.04766 0.04551 0.04282 0.04282 0.04551 0.04491 0.04488 0.04422 0.05061 0.05061 0.05061 0.05061 0.04766 0.04551 0.04787 0.04491 0.04551 0.04282 0.04282 0.04422 0.04488 0.04787 0.04766 0.04488 0.04422 0.04491 0.05061 0.05061 0.04551 1.72652 1.83477</array>
               <array dataType="xsd:double" size="84" dictRef="x:f">-1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 0.08014 0.09452</array>
               <array dataType="xsd:double" size="84" dictRef="x:g">-1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0 -1.0</array> 
           </module>
       </comment>

**Output text.**

.. code:: xml

   <comment class="example.output" id="populations2">
           <module cmlx:templateRef="populations">
              <array dataType="xsd:integer" dictRef="cc:serial" size="43">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43</array>
              <array dataType="xsd:string" dictRef="cc:atomType" size="43">fe n n n n n n n n n n n n n n n n n n n n n n n n c c c c c c h h h h h h h h h h h h</array>
              <array dataType="xsd:double" dictRef="x:charge" size="43">0.29209 -0.10253 -0.10253 -0.08969 -0.08969 0.03584 0.03584 -0.05936 -0.05936 -0.05027 -0.05027 -0.12596 -0.12596 -0.06467 -0.06467 -0.05369 -0.05369 -0.13139 -0.13139 -0.05562 -0.05562 -0.05202 -0.05202 -0.12955 -0.12955 0.06453 0.06453 0.06052 0.06052 0.05740 0.05740 0.21683 0.21683 0.29732 0.29732 0.21652 0.21652 0.29719 0.29719 0.22385 0.22385 0.29871 0.29871</array>
              <array dataType="xsd:double" dictRef="x:s" size="43">6.56555 3.61036 3.61036 3.60363 3.60363 3.53412 3.53412 3.75597 3.75597 3.39404 3.39404 3.72530 3.72530 3.76035 3.76035 3.39827 3.39827 3.72335 3.72335 3.75380 3.75380 3.39753 3.39753 3.72863 3.72863 3.18400 3.18400 3.18672 3.18672 3.18729 3.18729 0.76036 0.76036 0.66526 0.66526 0.76061 0.76061 0.66538 0.66538 0.75298 0.75298 0.66385 0.66385</array>
              <array dataType="xsd:double" dictRef="x:p" size="43">12.59879 3.40843 3.40843 3.40223 3.40223 3.33958 3.33958 3.19854 3.19854 3.57129 3.57129 3.29380 3.29380 3.19950 3.19950 3.57026 3.57026 3.30131 3.30131 3.19693 3.19693 3.56937 3.56937 3.29371 3.29371 2.60852 2.60852 2.60995 2.60995 2.60963 2.60963 0.02281 0.02281 0.03742 0.03742 0.02287 0.02287 0.03743 0.03743 0.02317 0.02317 0.03744 0.03744</array>
              <array dataType="xsd:double" dictRef="x:d" size="43">6.54256 0.07828 0.07828 0.07832 0.07832 0.08479 0.08479 0.09683 0.09683 0.07849 0.07849 0.09890 0.09890 0.09680 0.09680 0.07871 0.07871 0.09876 0.09876 0.09686 0.09686 0.07867 0.07867 0.09922 0.09922 0.12691 0.12691 0.12672 0.12672 0.12939 0.12939 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1</array>
              <array dataType="xsd:double" dictRef="x:f" size="43">0.00101 0.00547 0.00547 0.00550 0.00550 0.00567 0.00567 0.00801 0.00801 0.00644 0.00644 0.00795 0.00795 0.00802 0.00802 0.00645 0.00645 0.00798 0.00798 0.00803 0.00803 0.00645 0.00645 0.00799 0.00799 0.01605 0.01605 0.01610 0.01610 0.01628 0.01628 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1</array>
              <array dictRef="x:g" size="43">-1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1</array>
           </module>     
       </comment>

**Template definition.**

.. code:: xml

   <templateList>  <template id="noorbital" pattern="\s+(\d+\s?\w+)\s+[-\w\.]+\s*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record>{I,cc:serial}{A,cc:atomType}{F,x:charge}</record>    <transform process="addChild" dataType="cml:double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="3" dictRef="x:s" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="4" dictRef="x:p" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="5" dictRef="x:d" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="6" dictRef="x:f" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="7" dictRef="x:g" value="-1" />                                            
           </template>  <template id="s" pattern="\s+(\d+\s?\w+)\s+[-\w\.]+\s+[-\w\.]+\s*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record id="s">{I,cc:serial}{A,cc:atomType}{F,x:charge}{F,x:s}</record>    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="4" dictRef="x:p" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="5" dictRef="x:d" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="6" dictRef="x:f" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="7" dictRef="x:g" value="-1" />                                                                    
           </template>  <template id="sp" pattern="\s+(\d+\s?\w+)\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record id="sp">{I,cc:serial}{A,cc:atomType}{F,x:charge}{F,x:s}{F,x:p}</record>    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="5" dictRef="x:d" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="6" dictRef="x:f" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="7" dictRef="x:g" value="-1" />                              
           </template>  <template id="spd" pattern="\s+(\d+\s?\w+)\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record id="spd">{I,cc:serial}{A,cc:atomType}{F,x:charge}{F,x:s}{F,x:p}{F,x:d}</record>    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="6" dictRef="x:f" value="-1" />    <transform process="addChild" dataType="double" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="7" dictRef="x:g" value="-1" />
           </template>  <template id="spdf" pattern="\s+(\d+\s?\w+)\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record id="spdf">{I,cc:serial}{A,cc:atomType}{F,x:charge}{F,x:s}{F,x:p}{F,x:d}{F,x:f}</record>    <transform process="addChild" xpath="./cml:list/cml:list[position()=last()]" elementName="cml:scalar" position="7" dictRef="x:g" value="-1" dataType="xsd:double" />                              
           </template>  <template id="spdfg" pattern="\s+(\d+\s?\w+)\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s+[-\w\.]+\s*" endPattern=".*" endPattern2="~" endOffset="0" repeat="*">    <record id="spdfg">{I,cc:serial}{A,cc:atomType}{F,x:charge}{F,x:s}{F,x:p}{F,x:d}{F,x:f}{F,x:g}</record>                
           </template>
       </templateList>
   <transform process="setValue" xpath=".//cml:scalar[@dictRef='x:s'][@dataType='xsd:string']/@dataType" value="xsd:double" />
   <transform process="setValue" xpath=".//cml:scalar[@dictRef='x:p'][@dataType='xsd:string']/@dataType" value="xsd:double" />
   <transform process="setValue" xpath=".//cml:scalar[@dictRef='x:d'][@dataType='xsd:string']/@dataType" value="xsd:double" />
   <transform process="setValue" xpath=".//cml:scalar[@dictRef='x:f'][@dataType='xsd:string']/@dataType" value="xsd:double" />
   <transform process="setValue" xpath=".//cml:scalar[@dictRef='x:g'][@dataType='xsd:string']/@dataType" value="xsd:double" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:serial']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='cc:atomType']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:charge']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:s']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:p']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:d']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:f']" />
   <transform process="createArray" xpath="." from=".//cml:scalar[@dictRef='x:g']" />
   <transform process="pullup" xpath=".//cml:array" repeat="3" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/None.png
