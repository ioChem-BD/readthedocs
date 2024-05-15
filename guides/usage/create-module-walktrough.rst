Create module walkthrough
=========================

The Create module is a single-page web application aimed at managing input and output files from computational chemistry research work, and to generate derived content from it. Create allows uploading, organizing, visualizing and curing your data, and share it with your project mates. 

.. figure::  /imgs/CreateMain.png 
   :alt: Create module main page

   Create module main page
   

The window is composed of three frames, some with several tabs:

 -  `Navigation`_ / `Search`_ / `Reports`_ frame 
 -  `Item Actions`_ frame
 -  `Item Details`_ frame

.. figure:: /imgs/CreateMainPageFrames.png 
   :alt: Frame composition
   
   Frame composition

| The default operation flow within the  Create module starts by navigating/browsing user-uploaded content in the *Navigation* frame and selecting one of them to display its content. 
| When any Item is selected, both the *Item Actions* frame and the *Item Details* frame get actualized and display additional data. 

Multiple element selection is allowed, this is normally associated to global operations, such for instance when publishing a project, or when generating reports. 
Multiple element selection also disables *Item Actions* and *Item Details* frames.

Navigation frame
-----------------

| This frame is the entry point of all managing functionalities of the Create module. 
| Three tabs allow us to select the current operative mode:

  -  `Navigation`_
  -  `Search`_
  -  `Reports`_

To switch between modes, the user only has to click on each tab: 

.. figure:: /imgs/CreateNavigationTabs.png
   :alt: Mode switch tabs
   
   Mode switch tabs


Navigation/Edition mode
~~~~~~~~~~~~~~~~~~~~~~~

The Navigation tab will display a navigation tree composed of nodes and leaves. From now on we will call it our *workspace*. 

.. figure:: /imgs/CreateNavigationTreeElements.png
   :alt: Project and calculation navigation tree
   
   Project and calculation navigation tree

| Each node represents what we call a **project**. This is just a container element, like a folder, and can contain other subprojects or simply a set of single calculations, which are the basic element of your data. 
| A **calculation** usually contains input files, CML converted output files, additional files, etc ...
| The *Navigation* frame is the place to gather projects and calculations and organize your data sets in the way you want to eventually publish them.

| We can easily recognize **projects** inside the workspace by looking at the *Type* column as they are labeled as *PRO*. Another way to recognize them (when they contain child elements) is by a small arrow next to their name. When clicking on it, the project’s content will expand or collapse. 

| **Calculations** are the leafs in the hierarchy tree, ending points where nothing can hang from them. A calculation item represents all data associated to a single calculation, which comes straight from the output of computational chemistry packages. By selecting a calculation, both the *Item Actions* frame and the *Item Details* frame get actualized to display additional data. 

| On calculations, the *Type* column contains the abbreviation of the original software package used:

  -  ADF/AMS/: Calculation generated with `Amsterdam Density functional`_ software package
  -  AMB: Calculation generated with `Amber`_ software package
  -  CAS: Calculation generated with `CASTEP`_ software package
  -  GAU: Calculation generated with `Gaussian`_ software package
  -  GMC: Calculation generated with `GROMACS`_ software package
  -  GRRM: Calculation generated with `GRRM`_ software package    
  -  GRO: Calculation generated with `GronOR`_ software package
  -  LAM: Calculation generated with `LAMMPS`_ software package
  -  MOL: Calculation generated with `Molcas`_ software package
  -  MOP: Calculation generated with `Mopac`_ software package
  -  ORC: Calculation generated with `Orca`_ software package
  -  QEX: Calculation generated with `QuantumESPRESSO`_ software package
  -  SIE: Calculation generated with `SIESTA`_ software package
  -  TML: Calculation generated with `Turbomole`_ software package
  -  VSP: Calculation generated with `Vienna Ab initio Simulation Package`_ software package

This list will increase as more calculations types are implemented.

| Other interesting columns that are worth explaning are:

  -  *Description*: Text about the project/calculation (special symbols are allowed).
  -  *Status*: Current element status. Possible values: created/published.
  -  *Handle*: Unique identifier of each published element, which can be accessed from the Browse module (please read section `Publishing Calculations into Browse`_)
  -  *Published flag*: Check mark indicating if the element is published 

There is a context menu to help you with the repetitive actions. You have to first select any element in the workspace with the left click and then right click on it to see its available options in the context menu.

.. figure:: /imgs/CreateNavigationTreeContextMenu.png
   :alt: Element context menu

   Element context menu

Read the `Publishing Calculations`_ section or the `Generate reports`_ section to learn how to proceed further.

Search mode
~~~~~~~~~~~

The Search tab will display a form where the user can query all uploaded projects/calculations. Multiple filters are available to refine queries. Currently, it filters by administrative metadata and molecular structure:

  -  *Name* and *description* of the element, partial text matching search.
  -  *Type* of the element (calculation software type)
  -  *Path*, starting path to search for, see more at `path definition`_ section
  -  *User* who created the element and *group of users* that element belongs to
  -  *Access permissions* assigned to element
  -  *Creation* and *modification* dates
  -  Current element *state*


.. important:: Note that by enriching the *Description* field with meaningful information will allow you to look for those concepts when performing a search. 

.. figure:: /imgs/CreateSearchForm.png
   :alt: Multiple field search form 

   Multiple field search form

After setting the search parameters you whish, click the *Search* button to perform a query. A list of results will appear. 

.. figure:: /imgs/CreateSearchFormResults.png
   :alt:  Search results list
   
   Search results list

We can click on any listed element to display its particular *Item actions* and *details*. To perform a new query, the *Reset search* button will clean the form and will bring you back to Search form.

Report mode
~~~~~~~~~~~

This tab activates advanced operatives to process sets of calculations. This mode is fully reported in the `Generating reports`_ page. Please check it.

Item Actions frame
------------------

| This part of Create is in charge of displaying all actions related to a selected element in the Navigation/Search frames. Projects do not have any specific action associated. By selecting a project, it will display the initial news page. 
| Calculations have the following actions, which are accessible in the tabs of this frame:

  -  `3D structure`_
  -  `View results`_
  -  `Download`_
  -  `RAW CML`_

3D structure
~~~~~~~~~~~~

| This action displays the molecular structure or simulation cell. In the case of geometry optimization runs, it will show the final geometry. 
| In the case of NEB calculations run with VASP, a special tab will allow visualizing all the points. 
| We use JSmol (Javascript version of Jmol) to display such structures (and their cells in the case of periodic systems). Common JSmol operations:

  -  Hold left click + drag = Rotate molecule
  -  Central button scroll = Zoom in / out
  -  Hold Shift + double click + drag = Translate molecule
  -  Right click = Display JSmol options menu 


.. figure:: /imgs/CreateItemAction3DStructure.png
   :alt:  JSmol molecule visualization
   
   JSmol molecule visualization
   

View Results
~~~~~~~~~~~~

Some results of the output file uploaded to ioChem-BD are translated into CML (Chemical Markup Language), an XML language oriented to chemistry. Such markup language allows easy further conversion into any existing format, such as an HTML5 report, a PDF file, or a JSON file.

Selected data is visualized, normally organized by content:
  -  *General info*: Contains calculation administrative and descriptive metadata such is: user name, calculation type, methods used, …
  -  *Settings*: (VASP only), most relevant INCAR settings.
  -  *Atom info*: Atom type, coordinates and basis used. Eventually cell parameters, lattice vectors and atom valence.
  -  *Molecular info*: Implicit Solvation parameters, charge and multiplicity
  -  *Job*: Its content varies depending on the quantum chemistry package used to generate the calculation (ADF software generates different output fields than VASP, for example). For calculations with multiple jobs this section will appear more than once.

There is an exhaustive description on which fields are captured and how they are visualized. Please refer to `Conversion template reference`_

.. figure:: /imgs/CreateItemActionViewResults.png
   :alt: HTML report   
   
   HTML report

Download
~~~~~~~~

This action allows downloading calculation files to your local filesystem.

.. figure:: /imgs/CreateItemActionDownload.png
   :alt:  Download files form
   
   Download files form


RAW view
~~~~~~~~

This action displays calculation files content inside a text area. On large files, it will start to download the file instead of displaying it.

.. figure:: /imgs/CreateItemActionRaw.png
   :alt: View original files form
   
   View original files form
   

Item Details frame
------------------

Any project or calculation selected in our workspace will immediately refresh this form, displaying its administrative metadata. Some fields are modifiable f. ex. name, description, owner group, assigned permissions. Other fields are fixed like owner user or creation date. 

| In the lower area of this frame three buttons provide important actions:

  -  *Create project* : Generates a project in the current path using the values in the form
  -  *Modify* : Replaces stored values for the selected element with values in the form
  -  *Delete* : Deletes selected element.

.. figure:: /imgs/CreateItemDetailsForm.png
   :alt: Item details frame with operation buttons

   Item details frame with operation buttons

Upload bar
~~~~~~~~~~

On the bottom area of this frame there is an empty space. It is left blank intentionally to fit the upload bar. This bar will only appear while uploading calculations via the web interface, showing the progress of the uploading step..

.. figure:: /imgs/CreateItemDetailsUploadBar.png
   :alt: Upload bar after a single upload

   Upload bar after a single upload


.. _Navigation: #navigation-frame
.. _Search: #search-mode
.. _Reports: #report-mode
.. _Item Actions: #item-actions-frame
.. _Item Details: #item-details-frame
.. _3D structure: #d-structure
.. _View results: #view-results
.. _Download: #download
.. _RAW CML:  #raw-view
.. _Amsterdam Density functional: https://www.scm.com/
.. _Amber: http://ambermd.org/
.. _Gaussian: http://www.gaussian.com/
.. _GROMACS: http://www.gromacs.org/
.. _GronOR: http://gronor.org/
.. _Molcas: https://www.molcas.org/
.. _Mopac: http://openmopac.net/
.. _Orca: https://orcaforum.kofo.mpg.de/app.php/portal
.. _QuantumESPRESSO: https://www.quantum-espresso.org
.. _Turbomole: http://www.turbomole.com/
.. _Vienna Ab initio Simulation Package: https://www.vasp.at/
.. _Publishing Calculations into Browse: publishing-calculations/publish-process.html
.. _Publishing Calculations: publishing-calculations/publish-process.html
.. _Generate reports: generating-reports.html
.. _path definition: uploading-content-to-create/using-web-interface.html#paths
.. _Generating reports: generating-reports.html
.. _Conversion template reference: ../../conversion-html.html
.. _CASTEP: http://www.castep.org/
.. _GRRM: https://iqce.jp/GRRM/index_e.shtml
.. _LAMMPS: https://www.lammps.org
.. _SIESTA: https://siesta-project.org/siesta/
