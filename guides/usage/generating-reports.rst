Generating reports
==================

Along with navigation and search, there is another tab called *Reports*. 
This is responsible for storing and managing user-generated reports.

.. figure:: /imgs/CreateReportsMain.png
   :alt: Report manager tab

   Report manager tab

To generate a new report, users have to click on the Reports tab and then choose the desired report type.

.. figure:: /imgs/CreateReportsNew.png
   :alt: New report button

   New report button

.. note:: The current version of ioChem-BD has *Supporting information* and *Energy reaction profile* reports activated.


A new tab will appear with a blank report form. We can split the report's content into three sections:

  - *Report details*: Define general report fields, name and description are for internal Create module usage, title field is for the report header. 
  - *Report selected calculations*: A list of calculations associated to this report. We can order them by using drag-and-drop, set a name for each calculation or even remove them from this list. See the `Adding calculations to report`_ section to know how to populate this list. 
  - *Report configuration*: The right section of this form contains the specific report configuration. In the future, this section will vary depending on the report type that we are using.

.. figure:: /imgs/CreateReportsSupportingInformation.png
   :alt: Report form section

   Report form section

Once all report parameters are set, we need to look at the operation buttons under the Report configuration section.

All operations are activated except the *Publish* button. In future versions of ioChem-BD, that button will allow users to publish (as we do with calculations) into the Browse module and associate a handle identifier to it.

.. figure:: /imgs/CreateReportsNewButton.png
   :alt: New report options

   New report options

A single click on the *Generate* button will create the report and start its download on user’s web browser.

.. figure:: /imgs/CreateReportsNewResult.png
   :alt: Report PDF output example

   Report PDF output example

Adding calculations to report
-----------------------------

To add new calculations to an existing report, users have to select a group of calculations on the Navigation tab first. 

To select calculations we will follow the same steps as we described in `calculation publishing mechanism`_.

Once our projects/calculations are selected, we will click again on our report and then click on the *Add selected calculations* button. Previously selected elements will now populate the report list.

Another easy method to generate a report is to make a selection on *Navigation Frame* and then right click on it. 

From the contextual menu that will appear, we will select the *Supporting information* option, then a new report will be generated and all selected calculations will be included in it.

.. figure:: /imgs/CreateReportsNew2.png
   :alt: wikilink

   Creating reports based on calculation selection

.. _Adding calculations to report: #adding-calculations-to-report
.. _calculation publishing mechanism: ./publishing-calculations/publish-process.html#publication-steps
