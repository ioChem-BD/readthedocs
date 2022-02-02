How to use this help?
=====================

This WebHelp document can be used in a different way depending on your
purposes. You're free to navigate it as you like but if you need a rapid
access to specific parts of informations that are contained inside this
webpage. Here are some useful hints:

-  "I need to know if an specific section of my quantum chemistry
   software is captured by your repository software"

   First of all you must check whether your format is implemented, so
   you must first look at webhelp main page under *Legacy to CML*
   section if your format is listed there. Then you can continue reading
   this paragraph, otherwise you must contact our development team to
   code this new calculation format.

   Once we know that our format is captured, the fastest approach in
   discovering if such section is processed is searching few words from
   a line of text of such section in WebHelp Search field (on search
   tab).

   .. image:: /imgs/searchTab.png

   We must avoid capturing numerical values because our search will fail
   to find matches, just use alphabetic and symbol characters, p.ex.:
   *NUCLEAR COORDINATES (ANGSTROMS):*, *Rotational constants (GHZ)*,
   *Spin components of T(2) and E(2)* , *The second derivative* , etc.

   Once we've searched such value, a list of matches ordered by
   relevance will appear:

   -  If some of the matched templates points to our desired section we
      must procede to consult it by clicking on it's link.

      The new page that will appear is a resume of our template, it will
      display the most relevant information:

      Template name, physical file name, capture start/end regular
      expressions among other information. There should be also some
      examples of common inputs and it's converted output as formatted
      CML, it will help us in understanding which fields are generated
      and not.

      On top of this template definition there must be a resume table
      that defines it's implementation level :

      .. image:: /imgs/implementationLevel.png

      This value will vary depending on current template implementation
      status:

      -  |image1|\ All fields all captured / displayed

      -  |image2|\ Some fields are captured / displayed

      -  |image3|\ No field is captured / displayed

   -  If there are no matches for our section, you can try to find it
      directly from *Conversion templates : Text to CML* section inside
      content tab. If even then you don't find it, you must contact our
      development team to code such data extraction template and it's
      visualized fields.

-  "I want to view the logic under some fields assignement inside HTML5
   templates: charge, multiplicity, calculation type and so on"

   The straight way to access such information is to refer calculation
   HTML5 conversion related section. To do so we'll access content tab
   and then navigate to *HTML report content* entry, then we must choose
   selected format and later navigate to *Page components detail* and
   then to *Header* section.

.. |image1| image:: /imgs/Total.png
.. |image2| image:: /imgs/Partial.png
.. |image3| image:: /imgs/None.png
