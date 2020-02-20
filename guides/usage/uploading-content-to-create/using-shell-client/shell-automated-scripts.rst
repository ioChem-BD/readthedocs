Shell automated scripts
=======================

All ioChem-BD shell client commands can be shell-scripted to ease upload files into the Create Module in an automated way. Find herein few helper scripts that will assist you when uploading calculations. By using scripts, uploading data automaticly is just a trivial exercise. 

All our shell commands are contained within the shell client, which is `downloadable`_ from your Create web page. Feel free to customize these scripts to fit your needs, or turn them into new ones. Set the **-v** parameter (verbose) on these scripts to display more information about each script mechanism.

Per file type
-------------

- `loadadf`_
- `loadgauss`_
- `loadmolcas`_
- `loadmopac`_
- `loadqespresso`_
- `loadturbo`_
- `loadvasp`_
     - `neb`_ calculations
     - `dim`_ calculations


loadadf
~~~~~~~

Loads an ADF calculation into the the Create module.

============= ======================================================================================================
Parameters    Description
============= ======================================================================================================
-i *filename* Input file, (optional), if not defined will use script defined name
-o *filename* Output file (optional), if not defined will use script defined name
-a            Append additional file (optional)
-n *name*     Name of the calculation in the data base (optional), if not defined will use parent folder name
-d *desc*     Description of the calculation in the data base (optional), if not defined will use parent folder name
–auto         Autogenerate current path into Create module (optional). Refer to `-auto`_ parameter section.
============= ======================================================================================================

If parameters **-i** and **-o** are not set, this script will look for *input.in* and *output.out* files. If that info is missing, the upload process will be aborted. If you wish to use another naming convention just edit the *loadadf* script file and replace default filenames.

.. code:: bash

       # Default static file names, change them in order to fit your naming conventions
       INPUT_DEFAULT_FILENAME="input.in"
       OUTPUT_DEFAULT_FILENAME="output.out"

If parameters **-n** and **-d** are not defined, the scripts will use the parent folder’s name as calculation name and description.

Examples
'''''''' 

Upload calculation *a-pw12* using *a-pw12.opt.in* and *a-pw12.opt.in* files

.. code:: bash

       $ loadadf -i a-pw12.opt.in -o a-pw12.opt.out -n "a-pw12" -d "Optimization a-pw12"

Upload calculation named *metane* using *me-mp2.in* and *me-mp2.out* files; name and description are picked from the parent folder name.

.. code:: bash

       $ pwd
       /home/user/Desktop/methane
       $ loadadf -i me-mp2.in -o me-mo2.out

Upload calculation named *a-pw12.opt* and attach additional file *report.pdf*

.. code:: bash

       $ loadadf -i a-pw12.opt.in -o a-pw12.opt.out -a report.pdf -n a-pw12.opt -d "Optimization a-pw12"

Upload calculation and automatically build its parent folder. calculation name and description will be same as parent folder

.. code:: bash

       $ loadadf -i irc_ts2_09.in -o irc_ts2_09.out --auto

loadgauss
~~~~~~~~~

Same parameters and functionalities than the `loadadf`_ script.
  
.. Attention:: Please always use **#p** flag in your Gaussian calculations. Link information is required by ioChem-BD to properly capture Gaussian sections information.

loadmolcas
~~~~~~~~~~

Same parameters and functionalities than the `loadadf`_ script.


loadmopac
~~~~~~~~~

Same parameters and functionalities than the `loadadf`_ script.


loadqespresso
~~~~~~~~~~~~~

Same parameters and functionalities than the `loadadf`_ script.



loadturbo
~~~~~~~~~

Loads a Turbomole calculation into the Create Module. It can be used standalone as other shell client commands, or it can be attached to a job script to be automatically uploaded after the calculation has finished.

============= ===========================================================================================================
Parameters    Description
============= ===========================================================================================================
-i *control*  Input file (optional) , if not defined it will look for *control* file on current folder
-o *job.last* Output file (optional) , if not defined it will look for *job.last* file on current folder
-oe *energy*  Energy file (optional), if not defined it will look for *energy* file on current folder
-ob *basis*   Basis file (optional) , if not defined it will look for *basis* file on current folder
-oc *coord*   Coord file (optional), if not defined it will look for *coord* file on current folder
-a *file*     Append an additional file (optional)
-n            Name of the calculation in the data base (optional), if not defined it will use the parent folder’s name
-d *desc*     Description of the calculation in the data base (optional), if not defined it will use parent folder’s name
–auto         Autogenerate current path into the Create module (optional). Refer to `-auto`_ parameter section.
============= ===========================================================================================================

If parameters **-i** and **-o** are not set, it will look by default for *control* and *job.last* files on current folders, if they are missing the upload will be aborted. If we use another naming convention just edit *loadturbo* script file and replace the default file names.

.. code:: bash

       # Default static file names, change them in order to fit your naming conventions
       CONTROL_DEFAULT_FILENAME="control"
       ENERGY_DEFAULT_FILENAME="energy"
       BASIS_DEFAULT_FILENAME="basis"
       COORD_DEFAULT_FILENAME="coord"
       JOB_LAST_DEFAULT_FILENAME="job.last"

If parameters -n and -d are not defined, the loadturbo script will use the parent folder’s name as calculation name and description. If a parameter value contains multiple words and blank spaces (like description), they have to be enclosed inside double quotes.

Multiple step calculation
'''''''''''''''''''''''''

On calculations that generate multiple output files like **dscf**, **escf**, we can upload them as a unique file by joining its output files into one. We do so by repeating the -o parameter with the name of each output file. Must be defined in the same order as they were generated. Example:

.. code:: bash

       $ loadturbo -i control -o dscf.out -o escf.out


Examples
''''''''

Upload calculation *flourophenol* using *control*. *job.last*, *energy*, *basis* and *coord* files. Set name as *flourophenol*.

.. code:: bash

       $ loadturbo -i control -o job.last  -n "flourophenol" -d "Population analysis" -oe energy -ob basis -oc coord

We can omit multiple parameters if they are named the same as default script names, so the last command can be the same than this one:

.. code:: bash

       $ loadturbo -n "flourophenol" -d "Population analysis"

If no parameter is set, *name* and *description* fields will come from parent folder.

.. code:: bash

       $ pwd
       /home/user/Desktop/flourophenol
       $ loadturbo


loadvasp
~~~~~~~~

Loads a VASP calculation into the Create module, it can be used standalone as other shell client commands or it can be attached to a job script to be automatically uploaded after the calculation has finished.

============= ============================================================================================================================
Parameters    Description
============= ============================================================================================================================
-i *INCAR*    Input file (optional), if not defined it will look for INCAR file on current folder
-o *OUTCAR*   Output file (optional) , set to OUTCAR by default
-dc *DOSCAR*  Attach DOSCAR file information to resulting uploaded calculation (optional), it will extract Density of states coefficients.
-kp *KPOINTS* Attach KPOINTS file information to resulting uploaded calculation (optional), it will extract KPOINT generation data
-a *file*     Coord file (optional), if not defined it will look for the *coord* file from the current folder
-n            Name of the calculation in the data base (optional), if not defined the calculations’ output file name will be used
-d *desc*     Description of the calculation in the data base (optional), if not defined the calculations’ file name will used.
–auto         Autogenerate current path into Create module (optional). Refer to the `-auto`_ parameter section.
-neb          Upload Nudged Elastic Band calculation, see more at: `Uploading NEB/DIM calculations section`_
-dim          Upload Dimmer calculation, see more at: `Uploading NEB/DIM calculations section <#dim>`__
============= ============================================================================================================================

.. _examples-1:

Examples
''''''''

Uploads a calculation and sets identical name and description as the parent folder. It will capture INCAR and OUTCAR files by default

.. code:: bash

      $ loadvasp

Automatically generates parent folder structure and uploads calculation and sets identical name and description as the parent folder. It will capture INCAR and OUTCAR files by default, and will attach report.pdf file to calculation.

.. code:: bash

      $ loadvasp -a report.pdf --auto

Uploads calculation and associates its KPOINTS and DOSCAR files, sets name and description to *opt1*. It will capture INCAR and OUTCAR files by default

.. code:: bash

      $ loadvasp -n opt1 -d opt1 -kp KPOINTS -dc DOSCAR

Upload calculation set name and description to *opt2*. Will capture INCAR2 and OUTCAR2 files, because we set *-i* and *-o* parameters.

.. code:: bash

      $ loadvasp -i INCAR2 -o OUTCAR2 -n opt2 -d opt2 -kp KPOINTS -dc DOSCAR


Uploading VASP NEB/DIM calculation 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NEB 
''''''''

The nudged elastic band (NEB) is a method for finding saddle points and minimum energy paths between known reactants and products. The method works by optimizing a number of intermediate images along the reaction path.\ `1`_ This kind of calculation generates multiple output files (images) inside a collection of numbered subfolders. To upload this kind
of calculations we will set **-neb** parameter on base folder. loadvasp script will expect at last this file structure, it will iterate all XX folders and concatenate all outcar files.

.. code:: text

      .
      ├── 00
      │   └── OUTCAR
      ├── 01
      │   └── OUTCAR
      ├── 02
      │   └── OUTCAR
      ├── 03
      │   └── OUTCAR
      ├── 04
      │   └── OUTCAR
      ├── 05
      │   └── OUTCAR
      ├── 06
      │   └── OUTCAR
      └── INCAR

Example of a NEB calculation upload: Upload NEB, attach *KPOINTS* file information and set *NEB-1* as name and description.

.. code:: bash

       $ loadvasp -neb -kp KPOINTS -n NEB-1-2 -d NEB-1-2

DIM
''''''''

The dimer method is one of the min-mode following methods that allows the user to start from any initial configuration and search for a nearby saddle point. This method can also be used to start from a minimum basin and search in random directions for saddle points.\ `2`_ We can just upload calculation as a normal single calculation or we can use *-dim* parameter if we already have initial and
final state calculations, so we must set a folder structure like this:

.. code:: text

      .
      ├── IS
      │   └── OUTCAR
      ├── TS
      │   ├── INCAR
      │   └── OUTCAR
      └── FS
          └── OUTCAR

Example of a DIM calculation upload: Upload Dimmer, attach KPOINTS and DOSCAR information and set NO_dim as name and description.

.. code:: bash

      $ loadvasp -dim -kp KPOINTS -dc TS/DOSCAR -n NO_dim -d NO_dim


loadorca 
~~~~~~~~

Loads an ORCA calculation into the the Create module, it can be used standalone as other shell client commands or it can be attached to a job script to be automatically uploaded after the calculation has finished.

============= ==================================================================================================================================================================================
Parameters    Description
============= ==================================================================================================================================================================================
-i *filename* Input file, (optional), if not defined will use script defined name
-o *filename* Output file (optional), if not defined will use script defined name
-a            Append additional file (optional)
-n *name*     Name of the calculation in the data base (optional), if not defined will use parent folder name
-d *desc*     Description of the calculation in the data base (optional), if not defined will use parent folder name
–molden       Build molden file with calculation molecular orbitals from output file. Will use orca_m2kl script to do such conversion. Please read `–molden`_ section for further configuration.
–auto         Autogenerate current path into Create module (optional). Refer to `-auto`_ parameter section.
============= ==================================================================================================================================================================================

If parameters **-i** and **-o** are not set, it will look for *input.in* and ‘output.out’ files, if they are missing, the upload will be aborted. If we use another naming convention just edit the *loadorca* script file and replace default file names.

.. code:: bash

       # Default static file names, change them in order to fit your naming conventions
       INPUT_DEFAULT_FILENAME="input.in"
       OUTPUT_DEFAULT_FILENAME="output.out"

If parameters -n and -d are not defined, the loadorca script will use the parent folder’s name as calculation name and description. If a parameter value contains multiple words and blank spaces (like description), they must be enclosed inside double quotes.

Molden orbitals file generation 
''''''''''''''''''''''''''''''''

Along with input, output and additional files. This script allows generating a molden-format file that contains calculation molecular orbitals. If we use this flag, uploaded calculations will also display molecular orbitals on JSmol viewer. To generate such file, we must first edit the *loadorca* script file that resides on the shell client folder. First lines
define multiple *orca_2mkl_X_X_X* variables.

.. code:: bash

       orca_2mkl_2_8="/opt/ORCA2_8/orca_x86_64_exe_r2131/orca_2mkl"
       orca_2mkl_2_9_0="/opt/ORCA2_9/orca_x86_64_exe_r2131/orca_2mkl"
       orca_2mkl_3_0_0=
       orca_2mkl_3_0_1=

We must set the correct path to this script file to match your file system configuration. orca_2mkl is installed along with Orca software. Be careful to define as much variables and paths for each installed Orca version on yous system. If you use *-molden* parameter on a Orca v2.8 output file and its parameter is undefined, wrong or points a different version (2.9, 3.0, …), it will fail to work.

.. _examples-2:

Examples
++++++++

Upload calculation *ete* using *ete.inp* and *ete.out* files

.. code:: bash

       $ loadorca -i ete.inp -o ete.out -n "ete optimization" -d "Optimization ete"

Upload calculation named *ncs2* using *ncs2.inp* and *ncs2.out* files, name and description came from parent folder, then build molden molecular orbital files and upload it.

.. code:: bash

       $ pwd
       /home/user/Desktop/ncs2
       $ loadorca -i ncs2.inp -o ncs2.out -molden

Upload calculation and automatically build its parent folder, calculation name and description will be same as parent folder

.. code:: bash

       $ loadorca -i ete.inp -o ete.out --auto

–auto parameter 
---------------

In some situations our calculations lay inside a complex folder structure, under a high number of nested subfolders. Such project structure can be generated via the Create web interface or using the Create shell client commands, like `cpro`_, `cdpro`_ and `pwdpro`_. This can be a time-consuming process, so we can use the *-auto* parameter to generate such structure for us.
Imagine that we want to upload a calculation inside a path from a folder mounted like this:

.. code:: text

      /home/user/mnt_cluster/metOH-oxidation/MoO2/metOH/TS1_NEB/02/reopt/freq

Generating such project hierarchy via shell commands (excluding *$HOME*) will be like this 

.. code:: bash

       $ cpro -n metOH-oxidation -d metOH-oxidation    
       $ cdpro metOH-oxidation    
       $ cpro -n MoO2 -d MoO2    
       $ cdpro MoO2    
       $ cpro -n metOH -d metOH    
       $ cdpro metOH    
       $ cpro -n TS1_NEB -d TS1_NEB    
       $ cdpro TS1_NEB    
       $ cpro -n 02 -d 02    
       $ cdpro 02    
       $ cpro -n reopt -d reopt    
       $ cdpro reopt
       $ cpro -n freq -d freq    
       $ cdpro freq    
       $ loadcalc -i input.in -o output -n freq1 -d freq1


Using **-auto** parameter can be as simple as this

.. code:: bash

       $ cd /home/user/mnt_cluster/metOH-oxidation/MoO2/metOH/TS1_NEB/02/reopt/freq
       $ loadcalc -i input.in -o output -n freq1 -d freq1 **-auto**


Generated projects path will generate also *mnt_cluster* project, because **-auto** parameter excludes *$HOME*. If we want to exclude *mnt_cluster* folder or our folder is mounted in another path that does not contain a *$HOME* path like */mnt/cluster/…* we can edit our upload script *loadXXXX*:

.. code:: bash

     # On auto mode we will generate a project path, navigate inside and then upload calculation
      if [ $auto -gt 0 ]; then
          moveBasePath
          full_path="$(cd "$(dirname "$output")"; pwd)"   # Will use 'output' file parent folders
          home_path="$(cd $HOME_PATH/mnt_cluster; pwd)"   # Set this home_path if uploading from /home/user/mnt_cluster
          home_path="$(cd /mnt/cluster; pwd)"             # Set this home_path if uploading from /mnt/cluster


          partial_path="${full_path/$home_path/''}"         # Remove user home folder
          partial_path="${partial_path//[-@\$\%\& \"]/_}"   # Replace special characters and blank spaces by underscore
          if [ $verbose -gt 0 ]; then
              echo "Generating path : "$partial_path
          fi
          projects=$(echo $partial_path | tr "/" "\n")
          for project in $projects
          do
              if [ $project = "''" -o $project = "" ]; then
                continue
              fi
              project="${project//[-@\$\%\&\"\' ]/_}"
              createpro="cpro -n "$project" -d "$project
              changepro="cdpro "$project
              executeRepCommand "$REP_SCRIPTS/exe-rep-command $changepro" ""     # Try cdpro to project, if it fails, we'll create this project
              if [ ! $retval -eq  0 ]; then
              executeRepCommand "$REP_SCRIPTS/exe-rep-command $createpro" ""
                  executeRepCommand "$REP_SCRIPTS/exe-rep-command $changepro" ""
              fi
          done
      fi

Shell upload automation 
-----------------------

We can attach these lines to our calculation job scripts, so after the calculation software finishes its processing, it gets uploaded automatically into ioChem-BD, making this step totally unattended. 

Consider adding more verification steps inside upload scripts to avoid uploading erroneous calculations like premature exits, program crashes, not converged optimizations, etc.

In these examples, we consider that the shell client resides on *$HOME/shell*: 

Gaussian job submit file example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

.. code:: bash  
   :number-lines: 1
          
     #!/bin/bash
     #` -pe smp* 12    
     #$ -N test    
     #$ -cwd

     input=input.in    output=output.out

     /home/programs/bin/gaussian09.sh C01 :math: $input $output    
     . $HOME/shell/start-rep-shell                                              
     loadgauss -i $input -o $output -n $output -d $output –auto               
     exit-rep                                                                 


Numbered lines do:

   9.  Connect to Create
   10.  Upload calculation using Gaussian script and *$input* and *$output* parameters (builds path automatically)
   11.  Disconnect from Create


Turbomole job submit file example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash
   :number-lines: 1
   
      #!/bin/bash

      #$ -pe smp* 1-
      #$ -cwd
      #$ -q mag14.q

      . /home/programs/bin/turbomole.sh 6.6

      export TURBOTMPDIR=$TMPDIR

      cp HILL/* .
      /usr/bin/time -o time_output dscf

      output=$(basename $SGE_STDOUT_PATH)
      . $HOME/shell/start-rep-shell           
      loadturbo -o $output --auto           
      exit-rep                              


   
Numbered lines do:

   15. Connect to Create
   16. Upload calculation using turbomole script and *$output* parameters
   17. Disconnect from Create

Recursive upload
----------------

We can take advantage of shell scripting to automate calculation upload of multiple nested folders and subfolders. 


One calculation per folder 
~~~~~~~~~~~~~~~~~~~~~~~~~~

This is an example script that uploads a group of ADF calculations starting from current folder. Restrictions:

-  There must be only one input and ouput file inside each folder,
-  Uploaded calculations will have its name same as its parent folder name.

We can customize which input and output files are captured setting wildcards **\*.in** and **\*.out**.

.. code:: bash

      #!/bin/bash
      . start-rep-shell                           # <--- Please append full path to start-rep-shell command
       for folder in $(find  `pwd` -type d); do
           echo "Processing folder :" $folder
           inputfile="$(find  $folder -maxdepth 1  -name '*.in' -printf "%f\n")"
           outputfile="$(find $folder -maxdepth 1  -name '*.out' -printf "%f\n")"
           if [ -z $inputfile ]; then
          echo "  Not matching files"
           else
             echo "   Input file "$inputfile
             echo "   Output file "$outputfile
             cd $folder
             loadadf --auto -i $inputfile -o $outputfile
           fi
      done
      exit-rep


We can derive previous script into more sophisticated versions. 


Multiple calculations per folder 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following script navigates inside all child folders, it search for all input and output files inside each folder and then uploads them. 
This script allows setting file extensions for input and output files. 
Restrictions: 

  - Input and output files of the same calculation must have same name (and different extension) 
  - Uploaded calculation will be named as input file (to avoid name collisions)

.. code:: bash

    #!/bin/bash
    #Replace this variables to suit your naming convention
    INPUT_FILE_EXTENSION=in
    OUTPUT_FILE_EXTENSION=out
    . start-rep-shell                         # <--- Please append full path to start-rep-shell command
     for folder in $(find  `pwd` -type d); do
        echo "Processing folder :" $folder
        for inputfile in $(find  $folder -maxdepth 1  -name "*.$INPUT_FILE_EXTENSION" -printf "%f\n"); do
            filename=$(echo $inputfile | sed "s/\.$INPUT_FILE_EXTENSION//")
            outputfile="$filename.$OUTPUT_FILE_EXTENSION"
            if [ -z $outputfile ]; then
                echo "  Not matching output file "$outputfile
            else
                cd $folder
                loadgauss --auto -i $inputfile -o $outputfile -n $filename -d $filename
            fi
        done
    done
    exit-rep



.. _loadadf: #loadadf
.. _loadgauss: #loadgauss
.. _loadmolcas: #loadmolcas
.. _loadmopac: #loadmopac
.. _loadqespresso: #loadqespresso
.. _loadturbo: #loadturbo
.. _loadvasp: #loadvasp
.. _neb: #neb
.. _dim: #dim
.. _downloadable: ../../../usage/uploading-content-to-create/using-shell-client.html#shell-client
.. _-auto: #auto-parameter
.. _loadadf: #loadadf
.. _Uploading NEB/DIM calculations section: #neb
.. _1: http://theory.cm.utexas.edu/vtsttools/neb.html
.. _2: http://theory.cm.utexas.edu/vtsttools/dimer.html
.. _–molden: #molden
.. _cpro: ../../../usage/uploading-content-to-create/shell-commands.html#cpro
.. _cdpro: ../../../usage/uploading-content-to-create/shell-commands.html#cdpro
.. _pwdpro: ../../../usage/uploading-content-to-create/shell-commands.html#pwdpro
