.. _atom.potcar-d3e37229:

atom.potcar
===========

.. table:: Implementation level

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Type                                                                                                                       | Status                                                                                                                     |
   +============================================================================================================================+============================================================================================================================+
   | CML extraction template                                                                                                    | |image0|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | HTML5 representation                                                                                                       | |image1|                                                                                                                   |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

.. table:: Template attributes

   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Attribute                                                                                                                  | Value                                                                                                                      |
   +============================================================================================================================+============================================================================================================================+
   | *source*                                                                                                                   | VASP outcar                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | id                                                                                                                         | atom.potcar                                                                                                                |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | name                                                                                                                       | Potcar resume section                                                                                                      |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | pattern                                                                                                                    | &#92;s*POTCAR:.*$&#92;s{2,}&#92;w.\*                                                                                       |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern                                                                                                                 | &#92;s&#92;w.\*                                                                                                            |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endPattern2                                                                                                                | ~                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | endOffset                                                                                                                  | 0                                                                                                                          |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | repeat                                                                                                                     | \*                                                                                                                         |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+
   | xml:base                                                                                                                   | potcar/atom.potcar.xml                                                                                                     |
   +----------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------+

**Input.**

::

    POTCAR:   PAW_GGA O 05Jan2001                    
      VRHFIN =O: s2p4                                                              
      LEXCH  = 91                                                                  
      EATOM  =   433.0277 eV,   31.8266 Ry                                         
                                                                                   
      TITEL  = PAW_GGA O 05Jan2001                                                 
      LULTRA =        F    use ultrasoft PP ?                                      
      IUNSCR =        0    unscreen: 0-lin 1-nonlin 2-no                           
      RPACOR =     .000    partial core radius                                     
      POMASS =   16.000; ZVAL   =    6.000    mass and valenz                      
      RCORE  =    1.520    outmost cutoff radius                                   
      RWIGS  =    1.550; RWIGS  =     .820    wigner-seitz radius (au A)           
      ENMAX  =  400.000; ENMIN  =  300.000 eV                                      
      ICORE  =        2    local potential                                         
      LCOR   =        T    correct aug charges                                     
      LPAW   =        T    paw PP                                                  
      EAUG   =  605.392                                                            
      DEXC   =     .000                                                            
      RMAX   =    2.264    core radius for proj-oper                               
      RAUG   =    1.300    factor for augmentation sphere                          
      RDEP   =    1.550    radius for radial grids                                 
      QCUT   =   -5.520; QGAM   =   11.040    optimization parameters              
                                                                                   
      Description                                                                  
        l     E      TYP  RCUT    TYP  RCUT                                        
        0   .000     23  1.200                                                     
        0  -.700     23  1.200                                                     
        1   .000     23  1.520                                                     
        1   .600     23  1.520                                                     
        2   .000      7  1.500                                                     
     local pseudopotential read in
     atomic valenz-charges read in
     non local Contribution for L=           0  read in
       real space projection operators read in
     non local Contribution for L=           0  read in
       real space projection operators read in
     non local Contribution for L=           1  read in
       real space projection operators read in
     non local Contribution for L=           1  read in
       real space projection operators read in
       PAW grid and wavefunctions read in
    
      number of l-projection  operators is LMAX  =           4
      number of lm-projection operators is LMMAX =           8
    
    PAW_GGA Ti 08Aug2001                   :   
       

**Output text.**

.. code:: xml

   <comment class="example.output" id="atom.potcar"> 
           <module cmlx:templateRef="atom:potcar">
               <scalar dataType="xsd:string" dictRef="v:pseudopotential">PAW_PBE O 08Apr2002</scalar>
               <scalar dataType="xsd:string" dictRef="cc:atomType">O</scalar>
               <scalar dataType="xsd:double" dictRef="cc:mass">16.000</scalar>
               <scalar dataType="xsd:double" dictRef="cc:valence">6.000</scalar>
           </module> 
       </comment>

**Template definition.**

.. code:: xml

   <record>\s*POTCAR:\s*{X,v:pseudopotential}</record>
   <transform process="addChild" xpath="." dictRef="cc:atomType" value="$string(tokenize(tokenize(.//cml:scalar[@dictRef='v:pseudopotential'],'\s+')[2],'_')[1])" elementName="cml:scalar" />
   <transform process="pullup" xpath=".//cml:list/cml:scalar" />
   <templateList>  <template id="massvalence" pattern="\s*POMASS\s*=.*;\s*ZVAL\s*.*" endPattern=".*">    <record>\s*POMASS\s*={F,cc:mass};\s*ZVAL\s*={F,cc:valence}mass\sand\svalenz\s*</record>    <transform process="pullup" xpath=".//cml:scalar" repeat="3" />
           </template>       
       </templateList>
   <transform process="delete" xpath=".//cml:list" />
   <transform process="delete" xpath=".//cml:module" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Partial.png
