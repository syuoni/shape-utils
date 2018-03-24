# shape-utils
A tool for shapefile, mapping coordinates to shapes (districts/zones/tracts) in the shapefile. 

## Requirements
numpy, pandas, matplotlib, pyshp, shapely

## Usage
1. Put the Coord2Dist.py and shape_utils.py in the working directory. 
2. Put the shapefile in the working directory. 

For example, the shapefile is taxi_zones/taxi_zones.shp (https://s3.amazonaws.com/nyc-tlc/misc/taxi_zones.zip).
    
    from shape_utils import ShapeMap
    sm_nyc_taxi = ShapeMap(shp_fn='taxi_zones/taxi_zones.shp')
    # Show the information of each shape in the shapefile. 
    print(sm_nyc_taxi.sf_df.head())
    
    # `key` is the shape identifier. 
    sm_nyc_taxi.set_key('OBJECTID')
    
    # Map coordinate to shape identifier. 
    print(sm_nyc_taxi.coord2key(914408.0, 124617.0))
    
    # Visulize the shapefile. 
    sm_nyc_taxi.visualize(color_col='borough')
    
