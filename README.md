# Mapjig

Mapnik stylesheets to serve as templates for woodcut maps.


# Requirements

  * Mapnik trunk

  * PostGIS

  * OpenStreetMap data
  
  * osm2pgsql


# Setup

Shapefile extracts from OpenStreetMap:
 
    wget http://tile.openstreetmap.org/processed_p.tar.bz2 # (227M)
    wget http://tile.openstreetmap.org/shoreline_300.tar.bz2 # (46M)
    mkdir world_boundaries
    tar xjf processed_p.tar.bz2 -C world_boundaries
    tar xjf shoreline_300.tar.bz2 -C world_boundaries

OSM Extract imported into PostGIS with osm2pgsql
  
    osm2pgsql --slim -d <your database> extract.osm.bz2


Edit the datasource.xml.inc settings to match your system:

    datasource.xml.inc


Test rendering:

    sudo easy_install nik2img
    
    nik2img.py fast.xml test.png # should get red land, blue ocean