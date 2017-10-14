# sonoma-napa-fire-map-viirs

![](https://s3.amazonaws.com/mapzen-assets/resources/viirs-375-napa/sonoma_napa_fire_map.png)

## data

US (Conterminous and Hawaii) Fire data (375m resolution) via NASA/NOAA VIIRS (Suomi polar orbit).

Satellite passes are every ~12 hours (typically 1-3 AM & 1-3 PM for California), data available for download a few hours later. 

https://earthdata.nasa.gov/earth-observation-data/near-real-time/firms/active-fire-data

Right now this is a manual update as the data has to be converted to GeoJSON. 

I've been downloading the 7 day file for the contiguous US -- you could easily load other areas of the world or the global file, see below.

Fire names are from GeoMAC/USGS:

https://rmgsc.cr.usgs.gov/outgoing/GeoMAC/current_year_fire_data/current_year_all_states/

the boundaries are in there too but I'm not showing them right now -- uncomment the line draw group in the `perimeters`  layer.

## map 

scene file:

https://mapzen.com/tangram/play/?api=22/1119#11.5535/38.3784/-122.5101

Colors are divided into 12 hour steps. White dots are the latest data, yellow 12 hours before that, orange the day before, red 12 hours before that -- the darker the color, the older the data, using the [Viridian palette](https://github.com/politiken-journalism/scale-color-perceptual).

The date can be locked down on line 208. Primary source is defined on line 133, in the `viirs_7d:` url. 

Haven't yet figured out a way to download and convert the shapefile automatically into GeoJSON -- converting the CSV version ont the fly may be an option. Let me know if you want to help me make a service that takes a URL to a CSV with lat/lons and converts it on the flyto GeoJSON.

