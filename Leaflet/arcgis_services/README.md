ArcGIS Oline and ArcGIS Server map services
===========================================
 
A lot of public data are layers available only through ArcGIS Server map services so you can use Esri-Leaflet, a Javascript library used to make applications using the open source Leaflet.js library.

http://esri.github.io/esri-leaflet/

![esri-leaflet](http://mappingco.github.io/lab/Leaflet/arcgis_services/img/esri-leaflet.png)

```html
<!-- Load Esri Leaflet from CDN -->
<script src="http://cdn-geoweb.s3.amazonaws.com/esri-leaflet/0.0.1-beta.5/esri-leaflet.js"></script>
```

Choose a packaged basemap (Streets, Topographic, NationalGeographic, Oceans, Gray, DarkGray, Imagery and ShadedRelief):

```javascript
L.esri.basemapLayer('Streets').addTo(map);
```

Displaying tiles hosted on ArcGIS Online:

```javascript
// add a tile layer from ArcGIS Online or ArcGIS Server
L.esri.tiledMapLayer("http://services.arcgisonline.com/ArcGIS/rest/services/USA_Topo_Maps/MapServer", {}).addTo(map);
//L.esri.TiledMapLayer("http://services.arcgisonline.com/ArcGIS/rest/services/Specialty/World_Navigation_Charts/MapServer").addTo(map);
```

Displaying vector features:

```javascript
// add a tile layer from ArcGIS Online or ArcGIS Server
L.esri.tiledMapLayer("http://services.arcgisonline.com/ArcGIS/rest/services/USA_Topo_Maps/MapServer", {}).addTo(map);
//L.esri.TiledMapLayer("http://services.arcgisonline.com/ArcGIS/rest/services/Specialty/World_Navigation_Charts/MapServer").addTo(map);
```

Examples
--------

* Example 1, simple map with the Topographic basemap layer:

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_1.html

* Example 2, simple map that can switch between all available basemaps packaged with the esri-leaflet.js

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_2.html

* Example 3, add different geometries

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_3.html

* Example 4, dynamicMapLayer

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_4.html

* Example 5, custom popups (Heritage_Trees_Portland layer)

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_5.html

![example_5](http://mappingco.github.io/lab/Leaflet/arcgis_services/img/example5.png)

* Example 6, featureLayer with esriGeometryPoint and simple query (map with meteors)

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_6.html

* Example 7, map with the active Fires and perimeter (USA)

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_7.html

* Example 8, DynamicMapLayer: hurricanes / tornadoes (real-time data, global)

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_8.html

* Example 9, DynamicMapLayer: hurricanes / tornadoes with some query

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_9.html

Arcgis dynamicMapLayer
----------------------

Dynamic map layers (Render and visualize Map Services from ArcGIS Online and ArcGIS Server). A dynamic map service generates images on the fly, no tiles:

```javascript
  var map = L.map('map').setView([34.025, -116.203], 9);

  L.esri.basemapLayer('Gray').addTo(map);

  L.esri.dynamicMapLayer('http://maps1.arcgisonline.com/ArcGIS/rest/services/USA_Federal_Lands/MapServer', {
    opacity: 0.5
  }).addTo(map);
```

reference: http://esri.github.io/esri-leaflet/api-reference/layers/dynamic-map-layer.html


```javascript
L.esri.dynamicMapLayer("https://as1.sesync.org/arcgis/rest/services/OA_Vulnerability/Global_Annual_Chlorophyll_A_2002/MapServer/", {
        opacity : 1
      }).addTo(map);
```

Some Arcgis Rest services layers:
---------------------------------

* arcgisonline services:

http://services.arcgisonline.com/arcgis/rest/services

http://services.arcgisonline.com/ArcGIS/rest/services/Demographics/USA_Tapestry/MapServer

http://services.arcgisonline.com/arcgis/rest/services/World_Street_Map/MapServer

* USGS National Map Viewer:

http://viewer.nationalmap.gov/example/services/serviceList.html

* ArcGIS Services Directory

http://maps1.arcgisonline.com/ArcGIS/rest/services


* ArcGIS REST Services Directory

http://services.arcgis.com/rOo16HdIMeOBI4Mb/ArcGIS/rest/services

* raster

http://raster.nationalmap.gov/arcgis/rest/services/


raster layer, Spatial Reference: 3857
http://maps1.arcgisonline.com/ArcGIS/rest/services/USGS_Forest_Fragmentation/MapServer/0


Type: Feature Layer, Geometry Type: esriGeometryPoint, Spatial Reference: 3857
http://maps1.arcgisonline.com/ArcGIS/rest/services/NWS_Weather_Stations/MapServer/4

Type: Feature Layer, Geometry Type: esriGeometryPoint, Spatial Reference: 102100
http://services.arcgis.com/rOo16HdIMeOBI4Mb/ArcGIS/rest/services/Meteors/FeatureServer/0
