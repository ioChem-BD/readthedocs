.. _nucleus-d3e570:

nucleus
=======

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
   | *source*                          | ADF log                           |
   +-----------------------------------+-----------------------------------+
   | id                                | nucleus                           |
   +-----------------------------------+-----------------------------------+
   | name                              | NMR nucleus                       |
   +-----------------------------------+-----------------------------------+
   | pattern                           | .*N\sU\sC\sL\sE\sU\sS\s:.\*       |
   +-----------------------------------+-----------------------------------+
   | endPattern                        | \\s*#{20,}\s\*                    |
   +-----------------------------------+-----------------------------------+
   | endPattern2                       | \\s?\*{20,}\s\*                   |
   +-----------------------------------+-----------------------------------+
   | endPattern3                       | ~                                 |
   +-----------------------------------+-----------------------------------+
   | endOffset                         | 0                                 |
   +-----------------------------------+-----------------------------------+
   | repeat                            | \*                                |
   +-----------------------------------+-----------------------------------+
   | xml:base                          | nmr/nucleus.xml                   |
   +-----------------------------------+-----------------------------------+

**Input.**

::

   ****  N U C L E U S : W(23)
   ... 
   ================================================================================
    
    
   === SCALED: PARAMAGNETIC NMR SHIELDING TENSORS (ppm)
   ...
                           ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =  -7015.324
    
   ================================================================================
    
    
   === SCALED: DIAMAGNETIC NMR SHIELDING TENSORS (ppm)
   ...
                           ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =   9657.458

   ================================================================================ 
    
   === SCALED: SPIN-ORBIT NMR SHIELDING TENSORS (ppm)
   ...
                           ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =   -162.648 
   ================================================================================
    
    
   === SCALED: TOTAL NMR SHIELDING TENSOR (ppm)
   ... 
                           ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =   2479.486

   ################################################################################
   ********************************************************************************
   ****  N U C L E U S : W(22)
   ...
   === SCALED: PARAMAGNETIC NMR SHIELDING TENSORS (ppm)
   ...
                           ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =  -7001.298
                           
   ================================================================================

   === SCALED: DIAMAGNETIC NMR SHIELDING TENSORS (ppm)
                            ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =   9657.950

   ================================================================================ 
    
   === SCALED: SPIN-ORBIT NMR SHIELDING TENSORS (ppm)
   ...
                            ***********************************
                           CARTESIAN AXIS REPRESENTATION

                           isotropic shielding =   -167.181

   ================================================================================ 
    
   === SCALED: TOTAL NMR SHIELDING TENSOR (ppm)
    
                           ***********************************
                           CARTESIAN AXIS REPRESENTATION
   ...
                           isotropic shielding =   2489.471

   ################################################################################
       

.. warning::

   Current template has input comments defined but it's output is
   missing, please notify software developers.

**Template definition.**

.. code:: xml

   <record id="nucleus">.*N\sU\sC\sL\sE\sU\sS\s:{A,cc:elementType}\({X,a:nucleus}\)\s*</record>
   <templateList>  <template id="paramagnetic" pattern="\s*===(\sSCALED:)?\s*PARAMAGNETIC\sNMR\sSHIELDING\sTENSORS\s\(ppm\).*" endPattern="\s*={20,}+\s*" endPattern2="\s*#{20,}+\s*" endPattern3="~">    <templateList>      <template pattern=".*total\sparamagnetic\stensor.*" endPattern="\s+\*{20,}+\s*">        <record repeat="6" />        <record id="paramagnetic">\s*isotropic(\sshielding)?\s*={F,a:shielding}</record>
                   </template>
               </templateList>   
           </template>  <template id="diamagnetic" pattern="\s*===(\sSCALED:)?\s*DIAMAGNETIC\sNMR\sSHIELDING\sTENSORS\s\(ppm\).*" endPattern="\s*={20,}+\s*" endPattern2="\s*#{20,}+\s*" endPattern3="~">    <templateList>      <template pattern=".*total\sdiamagnetic(\sNMR)?\stensor.*" endPattern="\s+\*{20,}+\s*">        <record repeat="6" />        <record id="diamagnetic">\s*isotropic(\sshielding)?\s*={F,a:shielding}</record>
                   </template>
               </templateList>   
           </template>  <template id="spinorbit" pattern="\s*===(\sSCALED:)?\s*SPIN-ORBIT\sNMR\sSHIELDING\sTENSORS\s\(ppm\).*" endPattern="\s*={20,}+\s*" endPattern2="\s*#{20,}+\s*" endPattern3="~">    <templateList>      <template pattern=".*total\sspin-orbit\stensor.*" endPattern="\s+\*{20,}+\s*">        <record repeat="6" />        <record id="shielding">\s*isotropic(\sshielding)?\s*={F,a:shielding}</record>
                   </template>
               </templateList>   
           </template>  <template id="total" pattern="\s*===(\sSCALED:)?\s*TOTAL\sNMR\sSHIELDING\sTENSOR\s*\(ppm\).*" endPattern="\s*={20,}+\s*" endPattern2="\s*#{20,}+\s*" endPattern3="~">    <templateList>      <template pattern="\s*isotropic(\sshielding)?.*" endPattern=".*">        <record id="shielding">\s*isotropic(\sshielding)?\s*={F,a:shielding}</record>
                   </template>
               </templateList>   
           </template>   
       </templateList>
   <transform process="pullup" repeat="2" xpath=".//cml:scalar" />
   <transform process="addUnits" xpath=".//cml:scalar[@dictRef='a:shielding']" value="nonsi2:ppm" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:list[count(*)=0]" />
   <transform process="delete" xpath=".//cml:module[count(*)=0]" />

.. |image0| image:: ../../imgs/Total.png
.. |image1| image:: ../../imgs/Total.png
