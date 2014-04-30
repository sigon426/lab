
## Animated Orhodrome

The great-circle or orthodromic distance is the shortest distance between two points on the surface of a sphere, measured along the surface of the sphere (as opposed to a straight line through the sphere's interior).

![great circle](http://mappingco.github.io/lab/orthodrome/Rhumb-line-Great-Circle-mer.jpg)

Figure: Rhumb line and Great Circle in Mercator projection [more](http://www.free-online-private-pilot-ground-school.com/navigation-basics.html)


The orthodroma was created with PostGIS following [this post](http://anitagraser.com/2011/08/20/visualizing-global-connections/) by Anita Graser.

```sql
UPDATE geodeticlines
SET the_geom = 
(SELECT ST_Transform(ST_Segmentize(ST_MakeLine(
       ST_Transform(a.the_geom, 953027),
       ST_Transform(b.the_geom, 953027)
     ), 100000), 4326 ) 
 FROM salidas a, llegadas b

)
```

The plane was animated with the [AnimatedMarker](https://github.com/openplans/Leaflet.AnimatedMarker) 
Leaflet plugin.

Adding points to the orthodroma in an animation use code from [this mapbox's post](https://www.mapbox.com/mapbox.js/example/v1.0.0/dynamically-drawing-a-line/).

![orthodrome](http://mappingco.github.io/lab/orthodrome/orthodrome.png)Rhumb-line-Great-Circle-mer

 