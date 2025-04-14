import pandas as pd
import geopandas as gpd
from shapely.geometry import Point
Ames = pd.read_csv('../data/Ames.csv')
geometry = [Point(xy) for xy in zip(Ames['Longitude'], Ames['Latitude'])]
geo_df = gpd.GeoDataFrame(Ames, geometry=geometry)
print(geo_df)