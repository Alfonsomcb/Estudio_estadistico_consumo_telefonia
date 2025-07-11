# Estudio_estadistico_consumo_telefonia
# Análisis Estadístico de Tarifas de Telecomunicaciones

## 📜 Descripción del Proyecto

Este proyecto se realiza para Megaline, un operador de telecomunicaciones, con el fin de llevar a cabo un análisis estadístico preliminar sobre sus dos planes de prepago: "Surf" y "Ultimate". A partir de una muestra de 500 clientes, se analiza su comportamiento de consumo durante el año 2018 para determinar cuál de las dos tarifas genera mayores ingresos.

El objetivo final es proporcionar al departamento comercial una recomendación basada en datos para ajustar el presupuesto de publicidad de manera más efectiva.

## 🚀 Metodología y Análisis

El análisis se estructuró en varias fases clave para garantizar la calidad y precisión de las conclusiones:

1.  **Carga y Preparación de Datos**:
    * Se cargaron y exploraron cinco fuentes de datos distintas que contenían información sobre usuarios, planes, llamadas, mensajes e uso de internet.
    * Se realizó una limpieza exhaustiva de los datos, que incluyó:
        * Conversión de tipos de datos (fechas a `datetime`, IDs a `object`).
        * Redondeo de la duración de las llamadas y el consumo de datos al siguiente entero superior, de acuerdo con las políticas de cobro de Megaline.
        * Estandarización de texto a minúsculas y división de columnas para un mejor manejo de la información geográfica.

2.  **Agregación y Enriquecimiento de Datos**:
    * Se agruparon los datos de consumo (llamadas, mensajes, internet) por usuario y por mes para consolidar la información en un único DataFrame.
    * Se calculó el ingreso mensual para cada usuario, restando los límites gratuitos del paquete y aplicando los costos por excedente definidos en cada plan.

3.  **Análisis del Comportamiento del Usuario**:
    * Se comparó el consumo promedio de minutos, mensajes y GB de internet entre los usuarios de ambos planes.
    * Se utilizaron estadísticas descriptivas, histogramas, diagramas de caja y gráficos de densidad (KDE) para visualizar y comparar las distribuciones de consumo y de ingresos.

4.  **Pruebas de Hipótesis Estadísticas**:
    * Se formularon y probaron dos hipótesis clave utilizando la prueba t de Student para muestras independientes:
        1.  **Hipótesis 1**: El ingreso promedio de los usuarios de las tarifas "Ultimate" y "Surf" es diferente.
        2.  **Hipótesis 2**: El ingreso promedio de los usuarios del área de "NY-NJ" es diferente al de los usuarios de otras regiones.

## 📊 Conclusiones Principales

1.  **El plan "Surf" es más rentable en promedio**: Aunque el plan "Ultimate" tiene una tarifa mensual más alta, los usuarios del plan "Surf" tienden a exceder sus límites con mayor frecuencia, lo que genera ingresos adicionales significativos para la empresa.
2.  **Comportamiento de Pago Diferenciado**:
    * Los usuarios de **Ultimate** rara vez exceden los límites de su plan, manteniendo un pago mensual estable y predecible.
    * Los usuarios de **Surf** tienen una probabilidad del 71% de superar su tarifa base, lo que resulta en una mayor varianza y picos de ingresos.
3.  **Diferencias de Ingresos Estadísticamente Significativas**: Las pruebas de hipótesis confirmaron con un alto nivel de confianza que:
    * El ingreso promedio de los usuarios del plan "Surf" es **diferente y superior** al del plan "Ultimate".
    * El ingreso promedio en la región de **NY-NJ es diferente** al de otras regiones, mostrando una preferencia marcada por el plan Surf en esa área.

### Recomendación
Se recomienda al departamento comercial **aumentar el presupuesto de publicidad para el plan "Surf"**, ya que demuestra ser la tarifa más lucrativa. Además, se sugiere un análisis más profundo de las preferencias regionales para optimizar campañas de marketing segmentadas.

## 💻 Tecnologías Utilizadas

* **Lenguaje**: Python 3
* **Librerías**:
    * `Pandas` y `NumPy` para la manipulación y el procesamiento de datos.
    * `Matplotlib` y `Seaborn` para la visualización de datos.
    * `SciPy.stats` para la realización de pruebas de hipótesis estadísticas.
