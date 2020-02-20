Publishing endpoints definition  
===============================

Once our users and groups are generated, we must consider building the entity hierarchy on the Browse module to store all published elements coming from the *Create* module.

As we explained on `Basic introduction to ioChem-BD software`_ page, the *Create* module will be used to work with calculations coming from HPC clusters. On this module we will be able to read a HTML5 summary of the most important calculations fields, their geometry and perform searches, generate reports and so on.

All this work is done privately inside the *Create* module but it can be published into the *Browse* module to share your calculations with the rest of the world. 

This process is done by publishing *Create* projects and calculations into *Browse*, but that raises a question: *where to publish on Browse module?* So that is the reason why it is necessary to generate a publishing hierarchy on the *Browse* module to hold all these new calculations and projects.


The hierarchy inside Browse is really up to administrator’s choice and needs. Here are some example of this organization: 


.. topic:: A top community with your institution’s name

   Then inside it, their research groups community and inside them, its researchers community. 

   Here we expect every researcher to publish inside his/her named community:

.. code:: text

   Institute of Chemical Research of Catalonia
   ├── Carles Bo group
   │   ├── Bandeira, Nuno
   │   ├── Gonzalez-Fabra, Joan
   │   ├── Melgar, Dolores
   │   └── Serapian, Stefano
   ├── Feliu Maseras group
   │   ├── Besora, Maria
   │   ├── Fernandez, Victor
   │   ├── Kuniyil, Rositha
   │   └── Lakuntza, Oier
   └── Nuria Lopez group
       ├── Bellarosa, Luca
       ├── Capdevila, Marçal
       ├── Garcia, Miquel Alexandre
       ├── Li, Qiang
       └── Rellán, Marcos


.. topic::  Multiple top communities per research group

   And inside them, each researcher’s community.

.. code:: text

       Carles Bo group
       ├── Bandeira, Nuno
       ├── Gonzalez-Fabra, Joan
       ├── Melgar, Dolores
       └── Serapian, Stefano
       Feliu Maseras group
       ├── Besora, Maria
       ├── Fernandez, Victor
       ├── Kuniyil, Rositha
       └── Lakuntza, Oier
       Nuria Lopez group
       ├── Bellarosa, Luca
       ├── Capdevial, Marçal
       ├── Garcia, Miquel Alexandre
       ├── Li, Qiang
       └── Rellán, Marcos


.. topic::  One top community per researcher 

   (no grouping per research group) 

.. code:: text

       .
       ├── Bandeira, Nuno
       ├── Bellarosa, Luca
       ├── Besora, Maria
       ├── Capdevial, Maçal
       ├── Fernandez, Victor
       ├── Garcia, Miquel Alexandre
       ├── Gonzalez-Fabra, Joan
       ├── Kuniyil, Rositha
       ├── Lakuntza, Oier
       ├── Li, Qiang
       ├── Melgar, Dolores
       ├── Rellán, Marcos
       └── Serapian, Stefano

.. topic:: Only create top communities per research group and no subcommunities at all, 

   Then all group reseachers will publish directly into his/her group community, grouping all calculations inside it.

.. code:: text

       Carles Bo group
       Feliu Maseras group
       Nuria Lopez group



Another option instead of creating communities by group/person could be to create them by calculation type, molecule type. Please choose the structure you feel that will fit your needs better.


Community generation 
--------------------

Once we know how *Browse* will be structured we will start by creating the top community/ies. As administrator we will click *Browse* > *Communities and collections* on the upper menubar option.

.. figure:: /imgs/Admin_communities_and_collections.png
   :alt: Communities and collections menu option

   Communities and collections menu option

On the next page we will click on the *Create top level community* button.

.. figure:: /imgs/Admin_addtopcommunity.png
   :alt: Admin add new top community page

   Admin add new top community page

From the next form we must fill in the mandatory *Community name* textbox. We can also attach an image describing the community or append more info on the Description text field. 

.. figure:: /imgs/Admin_addtopcommunity2.png 
   :alt: Admin community add form 

   Admin community add form


Once this is done we will click on the *Create* button, and our community will be created

Subcommunity generation
-----------------------

Depending on the needed hierarchy, you will have to generate new subcommunities inside your top communities.

As administrators, we will navigate to the base community via *Browse > *Communities and collections*, then click on the desired community.

From the right sidebar we will choose *Create Sub-community* option and follow the same steps as when we create a top community.

.. figure:: /imgs/Admin_addsubcommunity.png
   :alt: Community options panel

   Community options panel

Assign community publishers
---------------------------

Once our publication structure has been defined, our last step as administrator is to define who will publish and where he/she will publish

To assign publication rights to a community we must define its administrators, it can be done in two ways.

1.Adding users as community administrators
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. note:: The ioChem-BD administrator account has higher levels of administrator than simple users managing their publishing community. So the system admin will be able to remove published collections and items, whereas other users will not.

We will first navigate to the desired community, in this example this will be a specific user community. From the sidebar we will click on the *Edit* button.

.. figure:: /imgs/Admin_addcommunityadmin.png
   :alt: Edit community sidebar

   Edit community sidebar

From next form we will click on *Create* administrator button on the right sidebar.

.. figure:: /imgs/Admin_addcommunityadmin2.png
   :alt: Community permissions toolbar

   Community permissions toolbar

In the new form we will choose which users or groups of users are allowed to publish inside this specific community.

In this demo case we are working with a user community so we will add this only user as administrator.
If we are working with a group community with no users, as described in the fourth example, we can add a users’ group (right panel) instead of a list of single users (left panel).

.. figure:: /imgs/Admin_addcommunityadmin3.png
   :alt: Set community administrators

   Set community administrators

We will do so for every user / group of users that we want to be able to publish, otherwise users will not be able to publish in the Browse module.

2. Adding the community on user’s edition form
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

On the top bar we will navigate to the *Administer* option, then *Access control* and finally *E-People*, it will open *Administer EPeople* page.

From here, we will search and edit the specific user by clicking the *Edit* button. On the edition form, you can choose the communities where the user will be allowed to publish by selecting it on the listbox named *Communities user can publish into*.

.. figure:: /imgs/Admin_createuser4.png
   :alt: Set user publishing communities

   Set user publishing communities

Resume
~~~~~~

Adding new users to ioChem-BD will require: 

  1. `Create the user`_, associate it to (at least) a user group and 
  2. `Create a community`_ where the user will publish or associate that user into a user group that already have publishing communities associated.

.. _Basic introduction to ioChem-BD software: ../../index.html
.. _Create the user: user-and-group-generation.html#creating-users
.. _Create a community: #publishing-endpoints-definition
 
