geocoder-data
======

festivals_netex_poi.xml
-------
Copied from kakka in GCS (`gs://ror-kakka-prd/tiamat/geocoder/festival_poi_netex.zip`) and
stored here for easy access from the [geocoder download script](https://github.com/entur/geocoder/blob/main/converter/create-nominatim-data.sh#L9)

country-boundaries.osm
--------
Originally imported from https://josm.openstreetmap.de/export/HEAD/josm/trunk/resources/data/boundaries.osm

Manually edited with JOSM to improve border accuracy

Converting to `.geojson`:
```
osmium export country-boundaries.osm -o country-boundaries.geojson
```
Converting to `.ser` (for [countryboundaries](https://github.com/westnordost/countryboundaries), which is used in the [geocoder Geo class](https://github.com/entur/geocoder/blob/main/common/src/main/kotlin/no/entur/geocoder/common/Geo.kt#L81)):
```
git clone https://github.com/westnordost/countryboundaries
cd countryboundaries/generator
../gradlew build
java -jar build/libs/generator-all.jar path/to/country-boundaries.osm 60 30
```
