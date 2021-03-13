# bigmap
The former project and script name was „mapCreator“.

A script that downloads OSM tiles and stitches them to a single png map. Based on [osm_download](https://github.com/maxolasersquad/osm_download) script.

Main source of tiles is the [osm-de](https://tile.openstreetmap.de) provider, but it can be changed to other tile servers in the ini file.

## How it works
* The script gets its configuration from the *settings.ini* file.
* Here each section corresponds to a map.
* The tiles are stored on disk to limit load on the server. Please avoid stressing the tile servers too much.
* The tiles are stitched to a single .png image and saved to the *dest* folder.

## Usage
* configure map setting in ```settings.ini``` file:
    * source : tile server url, with placeholders for x,y and zoom
    * dest : destination directory on disk where the map will be saved
    * tilestore : local tilestore directory
    * zoom : zoom setting, more zoom=more tiles
    * bbox : bounding box of the map. Bounding box parameters can be found [here](https://boundingbox.klokantech.com/).
* run with ```python bigmap.py <mapname>```
