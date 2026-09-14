# Análisis exploratorio de los datos de una campaña de marketing bancaria.
Este proyecto realiza un análisis exploratorio de datos sobre una campaña comercial bancaria portuguesa. El objetivo es consolidar las dos fuentes de información facilitadas (campaña y clientes), limpiar y transformar las variables, analizar los principales patrones asociados al resultado de la campaña y representar gráficamente los resultados más relevantes.

## Objetivo
- Integrar la información de clientes y campaña en un único conjunto de datos.
- Revisión de tipo de variables y calidad de la información.
- Transformar fechas, variables numéricas y variables binarias al formato adecuado.
- Descripción de cada variable indicando estadísticos principales (numéricas) o valores posibles.
- Estudiar la relación entre características del cliente, características de la campaña y el resultado comercial.
- Visualización de resultados mediante Matplotlib.

## Datos utilizados
El notebook trabaja con las siguientes fuentes datos:
- 'bank-additional.csv': información de la campaña comercial
- 'customer-details.cv': información de clientes repartida en tres años: 'customer-details2012.csv', 'customer-details2013.csv', 'customer-details2014.csv'
Los tres ficheros de clientes, importados individualmente porque de partida se encuentran en pestañas diferentes, se consolidan en unos solo y se cruzan con los datos de la campaña. El conjunto de datos consolidado contiene 43.170 registros y 28 variables. Se confirma que cada identificador de cliente es único y 170 clientes no disponen de información relativa a la campaña.

## Tecnologías aplicada
- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

## Estructura del análisis

### 1.- Importación y consolidación
Carga de las fuentes, consolidación de los ficheros anuales de clientes, comprobación de duplicados y unión con los datos de campaña.

### 2.- Transformación y limpieza
Entre las principales transformaciones realizadas se encuentran:
- Conversión de variables numéricas almacenadas como texto.
- Conversión y descomposición (año, mes, día) de variables de fecha.
- Tratamiento de `pdays` sustituyendo el valor 999 por un valor nulo.
- Conversión de las variables 'y,' 'default', 'housing' y 'loan' a variables booleanas.
- Construcción de un resumen final de variables del dataset consolidado.

### 3.- Análisis descriptivo
Se estudian variables, según su tipo, y se analiza la tasa de éxito de la campaña. También se crean variables auxiliares de antigüedad del cliente, grupo de edad y duración de llamada en minutos.

Algunos resultados destacados son:
- La tasa de éxito global, excluyendo valores nulos de 'y', es del 11.27%.
- La tasa anual de éxito se mantiene relativamente estable entre los años 2015 y 2019 entre el 11.11% y el 11.89%.
- Los clientes con menos de un año de antigüedad presentan una tasa de éxito del 20.53%, frente al 7.11% de los clientes con más de cinco años.
- Los clientes cuyo resultado en la campaña anterior fue 'SUCCESS' alcanzan una tasa de éxito del 65.32%.
- Por profesión, 'student' (31.34%) y 'retired' (25.20%) presentan los porcentajes más altos.
- El contacto por 'cellular' presenta una tasa de éxito del 14.74%, frente al 5.16% del contacto por 'telephone'.
- La tasa de éxito tiende a disminuir a medida que aumenta el número de contactos realizados durante la campaña.
- Las llamadas asociadas a resultados positivos presentan, de forma descriptiva, una duración superior a las llamadas sin éxito.

## Visualización de resultados
El notebook incluye seis visualizaciones con Matplotlib:

1. Gráfico de barras verticales de tasa de éxito según antigüedad del cliente.
2. Gráfico de barras horizontales de tasa de éxito por profesión.
3. Gráfico de líneas de tasa de éxito según número de contactos.
5. Gráfico combinado de volumen de clientes y tasa de éxito según número de contactos.
6. Histograma de distribución de edades.
7. Boxplot de duración de llamada según resultado de la campaña.

## Ejecución
1. Instalar el software necesario.
2. Colocar los orígenes de datos en la ubicación desde la que se ejecute el notebook.
3. Abrir el notebook y ejecutar todas las celdas de arriba abajo.
4. El proceso genera el fichero `Tabla_trabajo.csv` con el conjunto de datos consolidado y transformado.

## Consideraciones
- El análisis es exploratorio y descriptivo.
- Algunas categorías tienen un número reducido de observaciones, por lo que sus porcentajes deben interpretarse con cautela.
