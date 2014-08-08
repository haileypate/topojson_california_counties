## data files for creating California state maps

TopoJSON files are handy for creating customizable maps in web browsers. Feel free to grab [`ca_map.json`](https://github.com/haileypate/california_topojson/blob/master/ca_map.json) to use as a base for your own projects. 

Especially well suited for building data visualizations with [D3](http://d3js.org)!

### how this file was created

Total credit to the [awesome tutorial](http://bost.ocks.org/mike/map/) published by @mbostock, which explains how to create a map of the UK for free with open source tools. Here's a summary of how I followed these steps to prepare a similar map for California. 

For those of you who are new to this stuff, you can find snapshots of what the files look like after each step of the process [here](https://github.com/haileypate/california_topojson/tree/master/precursor_files).

##### Step 1: Get the tools

You'll need to install two command line tools before you can transform the files. Super explanation (again from @mbostock) [here](http://bost.ocks.org/mike/map/#installing-tools).

##### Step 2: Start with shapefiles from the US Census Bureau

To get the data for California, we'll need to start with the file containing all 50 states. It comes as a ZIP folder that can be downloaded [here](ftp://ftp2.census.gov/geo/tiger/TIGER2013/COUNTY/).

##### Step 3: Convert the shapefile to geoJSON using ogr2ogr

From the command line, navigate to the directory that contains the 5 files downloaded from census.gov. Type this code to filter the non-California states and create your California geoJSON:

```
ogr2ogr -f GeoJSON -where "STATEFP = '06'" ca_afterOgr2Ogr.json tl_2013_us_county.shp
```

##### Step 4: Simplify the geoJSON file using the free tools at mapshaper.org

*more info on this step coming soon!*

##### Step 5: Use topojson to set handy identifiers for the 58 counties and remove unneeded attributes

*more into on this to come as well..*

##### Step 6: Enjoy your map

*need to add notes on some tools for rendering topojson, ie github! and tutorial links... such as bostock posts*






