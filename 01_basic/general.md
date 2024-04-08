# Como crear un shapefile de puntos

Se tiene datos de puntos a partir de un diccionario, y se requiere generar un shapefile a partir de este input.
1. Convertir el diccionario a dataframe
2. Convertir dataframe a Geodataframe
3. Visualizar los puntos en el notebook
4. Crear el archivo shapefile

### 1. Convertir el diccionario a dataframe
```python
data = {
    "place":["New York","New York"],
    "point": ["a","b"],
    "longitud": [-74.2589,-73.7004],
    "latitud": [40.4774,40.9176],
}
```

Importar la libreria *pandas*
```python
import pandas as pd
# crear el dataframe
data_df = pd.DataFrame(data)
```
### 2. Convertir el dataframe a Geodataframe
Convertir las columnas que almacenan los datos de latitud y longitud a objetos geometricos de puntos. Para esto, se requiere usar la libreria *shapely.geometry*. Se puede usar la siguiente funcion que retorne una columna llamada *geometry*, la cual será resultado de la conversion de las coordenadas a un objeto geometrico.
```python
from shapely.geometry import Point
def get_point_geometry(df:object,lon_col_name:str,lat_col_name:str):
    df["geometry"] = [Point(xy) for xy in zip(df[lon_col_name],df[lat_col_name])]
    return df
```
Ejecucion de la función:
```python
data_df_geom = get_point_geometry(data_df,"longitud","latitud")
```
Una vez listo el dataframe con la columna geometry, se puede convertir el dataframe a geodataframe, el cual es requerido para crear el archivo shapefile
```python
# Conversion a Geo dataframe
data_gdf = gpd.GeoDataFrame(data_df_geom,geometry=data_df_geom["geometry"], crs= "EPSG:4326")
```
### 3. Visualizar los puntos en el notebook
Usar el metodo *plot( )*, para visualizar los puntos en un notebook o grafica
```python
# plotear el o los puntos
data_gdf.plot(markersize=5, color="blue")
```
### 4. Crear el shapefile
Usar la libreria **os**, para definir el directorio donde se creará el shapefile
```python
# convertir a shapefile
import os
os.chdir("/directory/path/ny")
data_gdf.to_file("NewYork" + ".shp")
```
### Conclusión
* Se requieren las librerias *pandas* y *geopandas*, para crear el dataframe y convertirlo en geodataframe posteriormente.

* La libreria *shapely.geometry* con el método *Point*, permite crear objetos geométricos de tipo Point a partir de las coordenadas geográficas latitud y longitud. Se aplicó una list comprehension, combinando el método *Point* y el método *zip( )*, para combinar los valores de latitud y longitud y crear la geometría
* De esta manera, se puede crear un shapefile a partir de un diccionario como input.
