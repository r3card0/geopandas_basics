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

La estructura de datos principal en Geopandas es *geopandas.GeoDataFrame*, que es una subclase de *pandas.DataFrame*. La estructura princial en Geopandas almacena columnas de *geometria* y puede ejecutar operaciones espaciales.

Mas informacion, ver [intruction guide](https://geopandas.org/en/stable/getting_started/introduction.html#Concepts)

