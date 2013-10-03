In JOSM 5932:

1.  Download data from OpenStreetMap.org or the OSM Task Manager

2.  Open SLO_ADDR_PTS.osm, found in X:\_data\Population\AddressPoints_to_OSM\ogr2osm

3.  Use the search tool to search for: building=*
    -This will select all polygons tagged as buildings.

4.  Next remove all buildings with addresses already by searching: "addr:housenumber"
    -This will remove all the buildings that already have addresses and leave only those buildings that did not get conflated.

5.  Turn on the SLO_ADDR_PTS layer and select the appropiate addresses that match the selected buildings.
    -With the address points layer selected you will be able to denote selected buildings by a slight red hue.

6.  Once you have addresses that match up with the buildings you can conflate them with the conflation plugin.
    -Select Configure on the conflation plugin found at the bottom of the right-hand side windows.
    -The Reference layer is SLO_ADDR_PTS.osm, hit freeze with this layer selected in the Layers window
    -The Subject layer is the current Data Layer, hit freeze with this layer selected in the Layers window
    -Set your threshold distance to 100 and hit Generate matches

7.  In the conflation window select a record and hit Ctrl+A to select all and then hit Conflate.
    *Never conflate a single-match.  There is a bug in the plugin that will crash JOSM if you try to only conflate one match.  To avoid this you can select the address point and building manually and also select a building and address that have already been conflated.  Then highlight both of these matches and conflate them.

8.  Now you can upload the edited data layer to OSM.
