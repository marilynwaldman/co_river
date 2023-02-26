From here:

https://bertt.wordpress.com/2023/01/06/creating-vector-pmtiles-with-tippecanoe/

Installed tippecanoe locally - no docker

Geojson from here:

https://coloradoriverbasin-lincolninstitute.hub.arcgis.com/datasets/lincolninstitute::colorado-river-water-allocation/explore?location=37.073540%2C-110.665687%2C5.96

```
ogr2ogr -f GeoJSON ../ne_10m_railroads.geojson -t_srs EPSG:4326   ne_10m_railroads.shp

-t_srs EPSG:4326
```

```

tippecanoe -zg --projection=EPSG:4326 -o railroad2.pmtiles -l zcta ne_10m_railroads.geojson

tippecanoe -zg -o co_basin.pmtiles --drop-densest-as-needed Colorado_River_Water_Allocation.geojson

 tippecanoe --output=railroads.pmtiles  ne_10m_railroads.geojson --maximum-zoom=7 --force For layer 0, using name "ne_10m_rtiailroads"


tippecanoe -zg -o us-states.pmtiles --drop-densest-as-needed us-states.json
```