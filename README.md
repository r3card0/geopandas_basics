# Foundations
[Geopandas](https://geopandas.org/en/stable/) es una libreria opensource de Python que permite realizar operaciones con datos y geometrias espaciales. Como base, cuenta con el apoyo de las librerias pandas, shapely, fiona y matplotlib. El uso de pandas es para el manejo de datos espaciales en formatos de series y dataframes. Shapely es una libreria que permite realizar operaciones geometricas. Fiona es una libreria que permite accesar a archivos y para visualizar los datos en mapas se aplica Matplotlib.

# Installation Process
Geopandas puede ser usado e instalado con las herramientas **conda** y **pip**

Forma de instalar geopandas en **conda**
````
conda install -c conda-forge geopandas
````

Instalar *geopandas* con **pip**
````
pip install geopandas
````

Para más informacion, consultar la [guia de instalacion](https://geopandas.org/en/stable/getting_started/install.html)

# Virtual environment creation
* [Guia para crear un ambiente virtual con **conda**]()
* [Guia para crear un ambiente virtual con **pip**]()

# Geopandas introduction
La estructura de datos principal en Geopandas es *geopandas.GeoDataFrame*, que es una subclase de *pandas.DataFrame*. La estructura princial en Geopandas almacena columnas de *geometria* y puede ejecutar operaciones espaciales.

Mas informacion, ver [introduction guide](https://geopandas.org/en/stable/getting_started/introduction.html#Concepts)

![data structure](https://geopandas.org/en/stable/_images/dataframe.svg)

# How to read and write files
## 1.Reading files
Se pueden leer archivos comunes como csv, y de excel o archivos espaciales (GeoPackage, GeoJSON, Shapefile). Estos ultimos se pueden se leidos aplicando el metodo: **geopandas.read_file()**, el cual detecta de forma automática los formatos espaciales y genera el **GeoDataFrame**
