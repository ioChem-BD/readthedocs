Shell commands
==============

All commands described here allow **-h** parameter that will display a help message containing a wider description of its usage.

.. warning:: It is not allowed to upload calculations to the base path (*/db/username*), you must always upload calculations into a project.

.. warning:: Two calculations with the **same name** and in the **same project** are not allowed, otherwise upload process will **fail**.
 

Basic parameters
----------------

========================= ===================================
Command                   Description
========================= ===================================
`source start-rep-shell`_ Connect to repository
`lspro`_                  List current path contents
`pwdpro`_                 Print current path (similar to pwd)
`exit-rep`_               Disconnect from repository
========================= ===================================

Project related commands
~~~~~~~~~~~~~~~~~~~~~~~~

========== =========================================
Command    Description
========== =========================================
`catpro`_  Display project information
`cdpro`_   Change to project
`cpro`_    Create a new project
`mpro`_    Modify a project
`dpro`_    Delete a project
`findpro`_ Find project by it’s name (regex allowed)
========== =========================================

Calculation related commands
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

================================== ======================================
Command                            Description
================================== ======================================
`viewcalc`_                        View calculation information
`mcalc`_                           Modify a calculation
`dcalc`_                           Delete calculation from repository
`getxyz`_                          Retrieve calculation geometry as XYZ
Calculation type specific commands 
`loadadf`_                         Load ADF calculation
`loadams`_                         Load AMS calculation
`loadamber`_                       Load Amber calculation
`loadcastep`_                      Load CASTEP calculation
`loadgauss`_                       Load Gaussian calculation
`loadgromacs`_                     Load GROMACS calculation
`loadgronor`_                      Load GronOR calculation
`loadgrrm`_                        Load GRRM calculation
`loadlammps`_                      Load LAMMPS calculation
`loadmolcas`_                      Load Molcas calculation
`loadmopac`_                       Load Mopac calculation
`loadorca`_                        Load Orca calculation
`loadqespresso`_                   Load QuantumESPRESSO calculation
`loadturbo`_                       Load Turbomole calculation
`loadsiesta`_                      Load SIESTA calculation
`loadvasp`_                        Load Vasp calculation
================================== ======================================

|

Basic parameters explained
-------------------------- 

start-rep-shell 
~~~~~~~~~~~~~~~

Used to connect to the repository, it must be always preceded by **source** or **.** (dot), otherwise neither connection nor commands will work.


Examples:
+++++++++

.. code:: console

   $ source start-rep-shell   #Connect to repository using long format
   $ . start-rep-shell        #Connect to repository using short format     


lspro
~~~~~

Displays content of current path: projects and calculations. Otherwise we can define a path to list its content.


+-----------------------------------+----------------------------------------------+
| Parameters                        | Description                                  |
+===================================+==============================================+
|  -n *path*                        | Relative or absolute path project (optional) |
+-----------------------------------+----------------------------------------------+
| -f                                | Display long format in listing (optional)    |
+-----------------------------------+----------------------------------------------+
| -o *order*                        | Order by. Possible values:                   |
|                                   |                                              |
|                                   |    - n->name,                                |
|                                   |    - o->owner,                               |
|                                   |    - g ->groupt->time,                       |
|                                   |    - c->concept,                             |
|                                   |    - s->state                                |
+-----------------------------------+----------------------------------------------+

Examples:
+++++++++

.. code:: console

    $ lspro                               #Sample listing in current path 
    $ lspro -n /db/username/hexenol       #Lists by name the content of hexenol project (absolute path)
    $ lspro -o Sc2C82                     #Lists by owner the content of hexenol project (relative to current path)


|

pwdpro
~~~~~~ 

Displays the current path, similar to pwd (print working directory) but lists current position inside the project’s hierarchy.

Examples:
+++++++++

.. code:: console

   $ pwdpro      #Prints current path


|

exit-rep
~~~~~~~~

Disconnects from the repository and ends current session. All repository commands are disabled after this command is executed.

Examples:
+++++++++

.. code:: console

   $ exit-rep     #Disconnects from repository


|

Project related commands
------------------------
 
catpro
~~~~~~

Displays project information.

========== =============================================
Parameters Description
========== =============================================
-n *path*  Relative or absolute project path (mandatory)
========== =============================================

Examples:
+++++++++

.. code:: console

   $ catpro -n hexenol                 # Prints project information using relative path
   $ catpro -n /db/username/hexenol    # Print project information using absolute path


|

cdpro
~~~~~

Changes path by navigating to parent / child project or an absolute path.

========== ==========================================================
Parameters Description
========== ==========================================================
-n *path*  Relative or absolute project path (mandatory except on ..)
========== ==========================================================

Examples:
+++++++++

.. code:: console

   $ cdpro ..                               # Changes path to parent project 
   $ cdpro -n metanol                       # Navigates to child project called metanol
   $ cdpro -n /db/username/metanol/freq     #Navigates to project using full path


|

cpro
~~~~

Creates new project in current path. If name or description parameters contains blank spaces, they must be enclosed in double quotes.

========== =======================================
Parameters Description
========== =======================================
-n         Name of the project (mandatory)
-d         Description of the project (mandatory)
-cg        Concept Group of the project (optional)
========== =======================================

Examples:
+++++++++

.. code:: console

   $ cpro -n metanol -d metanol                 # Creates metanol project with metanol description 
   $ cpro -n metanol -d metanol -cg FRQ         # Creates project with description and concept group
   $ cpro -n metanol -d  "This is the metanol project description"  # Creates metanol project with a long description


|

mpro 
~~~~

Modifies the selected project properties, name, description or even moves it to another project (as a nested project).

=================== ===================================================
Parameters          Description
=================== ===================================================
-n *path*           Relative or absolute project path (mandatory)
-p *permissions*    Permissions of the project. Ex: ‘rw----’ (optional)
-o *owner*          Owner of the project (optional)
-g *group*          Group owner of the project (optional)
-cg *concept_group* Concept Group of the project (optional)
-nn *name*          New Name of the project (optional)
-np *path*          New Parent project (absolute path) (optional)
-d *description*    Description of the project (optional)
=================== ===================================================


Examples:
+++++++++

.. code:: console
  
  $ mpro -n /db/username/hexenol -nn hexenolMod             # Replaces project name by hexenolMod 
  $ mpro -n /db/username/hexenol -np /db/user/alcohols      # Moves selected project to another parent project
  $ mpro -n /db/username/hexenol -d "Replaced description"  # Replaces description on selected project


|

dpro 
~~~~

Deletes a project by defining its path, all child projects and calculations will also be removed from Create.

========== =============================================
Parameters Description
========== =============================================
-n *path*  Relative or absolute project path (mandatory)
========== =============================================

Examples:
+++++++++

.. code:: console

   $ dpro -n metanol                          # Deletes metanol project using relative path, our path must be at the level of this project 
   $ dpro -n /db/username/alcohols/metanol    # Deletes metanol project using absolute path, current path position is not relevant here


|

findpro 
~~~~~~~

Find project by it’s name (regex allowed)

================ =========================================================================
Parameters       Description
================ =========================================================================
-n *name*        Regular expression to find in the name field of project (optional)
-d *description* Regular expression to find in the description field of project (optional)
-p *path*        Regular expression to find in the path field of project (optional)
================ =========================================================================


Examples:
+++++++++

.. code:: console

    $ findpro -n metan*            # Finds projects which name match regular expression metan*
    $ findpro -d "alco*"           # Finds projects which description match regular expression alco*


|

Calculation related commands
----------------------------

viewcalc 
~~~~~~~~

This comands displays the most relevant information about a calculation and retrieves its files.

================ ====================================================================================================
Parameters       Description
================ ====================================================================================================
-n *path*        Relative or absolute project path (mandatory)
-f *[filename]*  Download single calculation file, all if filename not specified. Requires -dcp parameter. (optional)
-dcp *path*      Full path where to store the files. It is mandatory to set also -f parameter. (optional)
================ ====================================================================================================


Examples:
+++++++++

.. code:: console

    $ viewcalc -n calc1                      # Display calculation on current project with name calc1
    $ viewcalc -n /db/user1/project/calc1    # Display calculation providing is fullpath
    $ viewcalc -n calc1 -f output.cml -dcp /home/user/tmp/calc1  # Display calculation information and store output.cml file on the provided folder
    $ viewcalc -n calc1 -f -dcp /home/user/tmp/calc1  # Display calculation information and store its files on the provided folder

|

mcalc
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Modifies the selected calculation properties, name, description or even moves it to another project.

================ =================================================
Parameters       Description
================ =================================================
-n *path*        Relative or absolute calculation path (mandatory)
-nn *name*       New Name of the calculation (optional)
-np *path*       New Parent project (absolute path) (optional)
-d *description* New description of the calculation (optional)
================ =================================================


Examples:
+++++++++

.. code:: console
                                                                                                                                                                       
   $ mcalc -n /db/user/metOH-oxidation/freq1 -nn freq2                  # Replaces calculation name by freq2 
   $ mcalc -n /db/user/metOH-oxidation/freq1 -np /db/user/alcohols      # Moves selected calculation to another project
   $ mcalc -n /db/user/metOH-oxidation/freq1 -d "Another description"   # Replaces description on selected calculation


|

dcalc
~~~~~~~~~~~~~~~~~~~~~~~~~~~

This command deletes a calculation given its name.

========== =================================================
Parameters Description
========== =================================================
-n *path*  Relative or absolute calculation path (mandatory)
========== =================================================

Using full calculation path:

.. code:: console

       $ dcalc -n  /db/user/metOH-oxidation/freq1    #Will delete calculation freq1 inside metOH-oxidation project


Navigating to parent project and using calculation name:


.. code:: console

       $ cdpro metOH-oxidation             #Move to parent project
       $ dcalc -n freq1                    #Will delete calculation freq1


|

getxyz
~~~~~~~~~~~~~~~~~~~~~~~~~~~

This command retrieves the geometry of a calculation given its id.

================ =================================================
Parameters       Description
================ =================================================
-n *id*          Calculation number id (mandatory)
-o *filename*    Output to file instead of stdout (optional)
================ =================================================


.. code:: console

       $ getxyz -n 14837                   # Retrieve geometry of calculation with ID 14837 and display on stdout
       $ getxyz -n 14837 -o geom.xyz       # Retrieve geometry of calculation with ID 14837 and store it in geom.xyz file 


|

There is a group of helper Linux scripts that simplify the process of uploading calculations:

======================================================================================================= ==============================================================================
Script                                                                                                  Function
======================================================================================================= ==============================================================================
`loadadf`_                                                                                              Upload **ADF** calculation
`loadams`_                                                                                              Upload **AMS** calculation
`loadamber`_                                                                                            Upload **Amber** calculation
`loadcastep`_                                                                                           Upload **CASTEP** calculation
`loadgauss`_                                                                                            Upload **Gaussian** calculation
`loadgromacs`_                                                                                          Upload **GROMACS** calculation
`loadgronor`_                                                                                           Upload **GronOR** calculation
`loadgrrm`_                                                                                             Upload **GRRM** calculation
`loadlammps`_                                                                                           Upload **LAMMPS** calculation
`loadmolcas`_                                                                                           Upload **Molcas** calculation
`loadmopac`_                                                                                            Upload **Mopac** calculation
`loadorca`_                                                                                             Upload **Orca** calculation
`loadqespresso`_                                                                                        Upload **QuantumEspresso** calculation
`loadturbo`_                                                                                            Upload **Turbomole** calculation
`loadsiesta`_                                                                                           Upload **SIESTA** calculation
`loadvasp`_                                                                                             Upload **Vasp** calculations (Nudge Elastic Band and Dimmer are also included)
======================================================================================================= ==============================================================================

.. _source start-rep-shell: #start-rep-shell
.. _lspro: #lspro
.. _pwdpro: #pwdpro
.. _exit-rep: #exit-rep
.. _catpro: #catpro
.. _cdpro: #cdpro
.. _cpro: #cpro
.. _mpro: #mpro
.. _dpro: #dpro
.. _findpro: #findpro
.. _viewcalc: #viewcalc
.. _mcalc: #mcalc
.. _dcalc: #dcalc
.. _getxyz: #getxyz
.. _loadadf:  ./using-shell-client/shell-automated-scripts.html#loadadf
.. _loadams:  ./using-shell-client/shell-automated-scripts.html#loadams
.. _loadamber:  ./using-shell-client/shell-automated-scripts.html#loadamber
.. _loadcastep:  ./using-shell-client/shell-automated-scripts.html#loadcastep
.. _loadgauss:  ./using-shell-client/shell-automated-scripts.html#loadgauss
.. _loadgromacs:  ./using-shell-client/shell-automated-scripts.html#loadgromacs
.. _loadgronor:  ./using-shell-client/shell-automated-scripts.html#loadgronor
.. _loadgrrm:  ./using-shell-client/shell-automated-scripts.html#loadgrrm
.. _loadlammps:  ./using-shell-client/shell-automated-scripts.html#loadlammps
.. _loadmolcas:  ./using-shell-client/shell-automated-scripts.html#loadmolcas
.. _loadmopac:  ./using-shell-client/shell-automated-scripts.html#loadmopac
.. _loadorca:  ./using-shell-client/shell-automated-scripts.html#loadorca
.. _loadqespresso:  ./using-shell-client/shell-automated-scripts.html#loadqespresso
.. _loadturbo:  ./using-shell-client/shell-automated-scripts.html#loadturbo
.. _loadsiesta: ./using-shell-client/shell-automated-scripts.html#loadsiesta
.. _loadvasp: ./using-shell-client/shell-automated-scripts.html#loadvasp
