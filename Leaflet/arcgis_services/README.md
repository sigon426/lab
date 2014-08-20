ArcGIS Server map services
==========================
 
A lot of public data are layers available only through ArcGIS Server map services

Esri-Leaflet is a Javascript library used to make applications using the Leaflet.js library.

http://esri.github.io/esri-leaflet/
![esri-leaflet](http://mappingco.github.io/lab/Leaflet/arcgis_services/esri-leaflet.png)

```html
<!-- Load Esri Leaflet from CDN -->
<script src="http://cdn-geoweb.s3.amazonaws.com/esri-leaflet/0.0.1-beta.5/esri-leaflet.js"></script>
```

```javascript
var baseUrl = "http://services.arcgisonline.com/ArcGIS/rest/services/Demographics/
USA_Tapestry/MapServer";
```
Choose a packaged basemap (Streets, Topographic, NationalGeographic, Oceans, Gray, DarkGray, Imagery and ShadedRelief):

```javascript
L.esri.basemapLayer('Streets').addTo(map);
```

Displaying tiles hosted on ArcGIS Online:

```javascript
L.esri.tiledMapLayer("http://services.arcgisonline.com/ArcGIS/rest/services/USA_Topo_Maps/MapServer", {}).addTo(map);
```




Examples
--------

* Example 1, simple map with the Topographic basemap layer:

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_1.html

* Example 2, simple map that can switch between all available basemaps packaged with the esri-leaflet.js

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_2.html

* Example 3, add different geometries

http://mappingco.github.io/lab/Leaflet/arcgis_services/example_3.html

Arcgis dynamicMapLayer
----------------------

Dynamic map layers (Render and visualize Map Services from ArcGIS Online and ArcGIS Server):

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
----------------------------

* http://services.arcgisonline.com/arcgis/rest/services

http://services.arcgisonline.com/ArcGIS/rest/services/Demographics/
USA_Tapestry/MapServer

http://services.arcgisonline.com/arcgis/rest/services/World_Street_Map/MapServer

* USGS National Map Viewer:

http://viewer.nationalmap.gov/example/services/serviceList.html
