Setting the embargo
^^^^^^^^^^^^^^^^^^^

Under some circumstances, ioChem-BD users need to restrict the access to some elements published on Browse module.

The most common situation is while publishing a manuscript in a journal and its supporting information needs to be accessed by the reviewers. In that special case, the published dataset has to be private to everyone but visible for a reduced number of users (reviewers). In this case the users who are publishing to Browse module must activate the checkbox *Embargo published elements*

|image0|

With this option activated, published elements will be visible inside its collection…

|image1|

but will request for validation when trying to access any individual item.

|image2|

Accessing the embargoed elements 
--------------------------------

Embargoed collections have its individual item pages restricted, only using the collection *reviewer link* will have access to:

-  full list of metadata fields,
-  display molecule geometry in a specific viewer (JSmol)
-  view HTML5 resume
-  download calculation related files

Embargoed collections generate an unique URL to review its content, example:

https://iochem-bd-test.iciq.es/browse/review-collection/100/78/7d61fee92da1ef2ac787cccc

This links are displayed after publishing the embargoed content from Create module, they should be shared with the collection reviewers.

Users can get them anytime on the Create module by clicking on the black icon next to the project.

.. figure:: /imgs/EditPublishedElement.png
   :alt: This links point to the Edit Collection page

   This links point to the Edit Collection page

On the edit collection page, users can modify certain aspects of the published elements and also retrieve the Embargo link, this link won’t appear if the collection doesn’t have embargoed elements

|image3|

Lifting the embargo
-------------------

Once the content has been validated/reviewed, users can lift the embargo on the same *Edit collection* page . Clicking this button will lift the embargo on the collection:

|image4|

Once the embargo is lifted, the embargo section on *Edit collection* page will disappear and the review links will cease to work.

.. |image0| image:: /imgs/PublicationOptions2a.png
.. |image1| image:: /imgs/embargoed-collection.png
.. |image2| image:: /imgs/LoginRequired.png
.. |image3| image:: /imgs/EditCollection3.png
.. |image4| image:: /imgs/EditCollection4.png
