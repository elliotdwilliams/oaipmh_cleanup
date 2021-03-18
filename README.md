# Recipes for cleaning up OAI-PMH exports in OpenRefine

This repository contains two sets of OpenRefine (OR) operations for preparing metadata exported from an OAI-PMH endpoint.  These commands do some very basic clean-up and re-ordering of the columns to make it easier to analyze a metadata set using OR.  

I use these recipes when working with metadata exported from an OAI-PMH endpoint. (I use the metadata-harvest script developed by Christina Harlow based on work by Mark Phillips, and documented here: https://github.com/dpla/Metadata-Analysis-Workshop/blob/master/Metadata_Harvest.md)  After exporting the metadata, I frequently use OpenRefine to analyze it, and found myself performing the same set of operations on each harvested XML file that I opened in OR.  These recipes are a way to speed up that initial process and make it easier to read and work with the metadata in OR.  Basically, they make it easier to see the columns that include data (i.e. are not empty container elements) and rename the columns with more helpful names.

There are two recipes included in this repository, one for Qualified Dublin Core and one for MODS:
1. Qualfied Dublin Core - This recipe is very simple.  It moves the OAI record identifier column to the front of the project (which makes it easier to use OR's record mode); removes a few empty columns; and renames each column with just the DC element.
2. MODS - This recipe is a bit more complicated (because MODS is more complicated), but still pretty straight-forward.  It also moves the OAI record identifier column to the front of the project (which makes it easier to use OR's record mode) and renames columns with the MODS element/attribute name (including any parent elements).  Because MODS using more nested elements, it also removes the empty columns for parent elements that do not contain any data.

To perform these operations in OpenRefine: 
1. Create a new project using the exported XML metadata
2. Go to the "Undo/Redo" tab at the top-left of the grid view
3. Select the "Apply..." button
4. Copy and paste the JSON text from this repository into the window
5. Click "Perform Operations"

I've used and tested these recipes with XML metadata exported from CONTENTdm and Islandora systems, but not others.  Some operations, particularly in the MODS recipe, are specific to systems I work with, but if your metadata doesn't include those elements (such as the FLVC extension elements), OR will simply skip over those operations.

Please feel free to reach out or open an issue if you have feedback or suggestions!
