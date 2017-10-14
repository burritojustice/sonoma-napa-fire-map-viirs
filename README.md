# sonoma-napa-fire-map-viirs

##data

Fire data (375m resolution) via NASA/NOAA VIIRS (Suomi polar orbit)

data updates every ~12 hours (typically 1-3 AM & 1-3 PM for California), data available a few hours later:

https://earthdata.nasa.gov/earth-observation-data/near-real-time/firms/active-fire-data

Fire names from GeoMAC/USGS:

https://rmgsc.cr.usgs.gov/outgoing/GeoMAC/current_year_fire_data/current_year_all_states/

##map source:

https://mapzen.com/tangram/play/?api=22/1119#11.5535/38.3784/-122.5101

Colors are divided into 12 hour steps. White dots are the latest data -- the darker the color, the older the data, using the [Viridian palette](https://github.com/politiken-journalism/scale-color-perceptual).

The date can be locked down on line 208. Primary source is defined on line 133, in the `viirs_7d:` url. 

Haven't yet figured out a way to download and convert the shapefile automatically into GeoJSON -- converting the CSV version ont the fly may be an option.
