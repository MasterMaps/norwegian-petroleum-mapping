The Norwegian Offshore Directorate has large amounts of public data about petroleum activities on the Norwegian continental shelf.

https://www.sodir.no/en/facts/data-and-analysis/open-data/

To download all datasets use the FGBD format under "Datasets Factmaps".
Unzip the file. You can open the .gdb folder in QGIS to inspect the data.

brew install gdal

https://gdal.org/en/stable/drivers/vector/openfilegdb.html#vector-openfilegdb

ogrinfo data/SODIR_FactMaps_data_v3_0/SODIR_FactMaps_data_v3_0.gdb

ogr2ogr data/block.geojson data/SODIR_FactMaps_data_v3_0/SODIR_FactMaps_data_v3_0.gdb block -t_srs EPSG:4326

ogr2ogr data/sbm_block.geojson data/SODIR_FactMaps_data_v3_0/SODIR_FactMaps_data_v3_0.gdb sbm_block -t_srs EPSG:4326

ogr2ogr data/areastatus.geojson data/SODIR_FactMaps_data_v3_0/SODIR_FactMaps_data_v3_0.gdb areastatus -t_srs EPSG:4326

ogr2ogr data/sub_area.geojson data/SODIR_FactMaps_data_v3_0/SODIR_FactMaps_data_v3_0.gdb sub_area -t_srs EPSG:4326

brew install tippecanoe

tippecanoe -o examples/data/norway-petroleum.pmtiles data/block.geojson data/sbm_block.geojson data/areastatus.geojson data/sub_area.geojson -z 10

npm install --global serve

cd examples

serve

https://jupyterbook.org/en/stable/publish/gh-pages.html
https://github.com/MasterMaps/norwegian-petroleum-mapping/settings/pages
