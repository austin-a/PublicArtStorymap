Public Art Application Maintenance Guide

This guide is intended to explain how to maintain the public art application and web map.
Table of Contents:
* Web map
o Editing metadata
o Editing feature data
* Story map explanation
Web Map
The web map is hosted on ArcGIS Online (http://arcgis.com) as part of the City of Olympia’s ArcGIS Online subscription. The public art data consists of several pieces. 
The service definition file is what the feature service is generated with. The service definition is the original data which can always be used to generate another feature service. This should not be shared with the general public as you risk losing this archive of data.
The feature service contains the visible representation of the data. It is similar to a shapefile in ArcGIS Desktop. It can be viewed on ArcGIS Online; overlaid with a basemap. This data must be shared with the public in order for a public audience to view it. When changes are made to the feature service, those changes are reflected in the web map and story map. This feature service can also be added to maps created using the ArcGIS Javascript API for use in future web apps.
The web map is a saved configuration of layers (feature services) and a basemap. The map itself does not contain any spatial data; it only makes reference to the feature services. The web map functions similar to a map document in ArcGIS Desktop. This web map can be used in a variety of ways. It can be embedded directly into a web page using html, shared through social media, or transformed into a web application using a pre-established template.
Editing Metadata
Maintaining proper metadata is important so that the data remains usable and accessible to a larger audience. This data will most likely go unchanged for long periods of time, but it may be necessary to modify it at some point. To edit the metadata, begin by clicking the “Edit” button located in the toolbar below the thumbnail image, exposing the text fields for editing.This page also allows you to enable the data to be edited and set the thumbnail.
Editing Feature Data
To edit the features and their data, open the feature service using the ArcGIS Online map viewer. Click the “Edit” button in the toolbar above the map view. A new panel will open on the left side of the screen titled “Add Features”. If you wish to add new features to the data, click on the appropriate icon for the layer you wish to edit. You can now place new points by clicking on the map. When you add a new point to the map, you will be prompted to enter data in the pop-up that appears. 
To edit existing data, click on an existing feature in the map instead of using the “Add Features” panel.  This will open a pop-up displaying the attributes for that point. If multiple points exist at that location, there will be two sideways arrows at the top of the pop-up that enable you to cycle through the features. When you are finished editing, click the “Edit” button again and your edits will be saved automatically.
Story Map Explanation
The story map was made with a template created by Esri using the ArcGIS Javascript API. The original template can be downloaded here: http://www.arcgis.com/home/item.html?id=d4a2705a8b224e71961404542ae94c6f
The original Javascript code has been modified to access a feature service that is hosted on ArcGIS Online. There is a config section of code starting on line 51. It is here that you can control the initial picture, the basemap used and several other variables. Code in the init function determines which feature service is currently being accessed. The points are programmatically symbolized using a collection of .png images. The code for that can be found in the subRoutine function.
The feature service that the program points to has the following fields: Title_of_Work, Name_of_Artist, Address, City, State, Description, Photo_URL, Collection, and ThumbNail. Many more fields currently exist within the feature service, but they are largely for internal use only.
The story map code uses additional functions that are included alongside the .html file. These .js files contain the jQuery code used for some of the page elements such as the picture carousel.
The story map can be modified to display a certain selection of points by changing the query parameters. The default settings are as follows:
query.where = “1=1”;
This can be changed to display only certain points by referencing the ID of the feature.
query.where = “ID in (4,7,2,1,6,8)”;
The overall look and feel of the application can be changed by loading a different dojo dijit theme.
