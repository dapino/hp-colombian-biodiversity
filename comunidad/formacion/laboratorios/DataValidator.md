---
layout: documentation
permalink: /formacion/laboratorios/DataValidator
title: "Validador de datos - GBIF"
description: "Objetivo: Detectar posibles problemas en  la estructura y contenido de su conjunto de datos, y mejorar la calidad de los mismos para ser publicados a través del SiB Colombia, GBIF y/o OBIS."
sideNavigation: sidenav_laboratorios.terms
toc: true
---

# Validador de datos - GBIF


**Objetivo**

Detectar posibles problemas en la estructura y contenido de los conjuntos de datos, mejorando la calidad de estos para ser publicados a través del SiB Colombia, GBIF y OBIS.

**Introducción**

<iframe width="560" height="315" src="https://www.youtube.com/embed/XDZu-mi7tAc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br/>
**Convenciones**

- Los elementos del estándar *Darwin Core* aparecen en color verde y cursiva. Por ejemplo: <span class="tag is-success is-light"><i>measurementUnit</i></span>.
- Los archivos a utilizar en los ejercicios se muestran entre comillas angulares, negrita, y tienen una tipografía diferente. Por ejemplo: <FONT FACE="monospace"><b>«archivo_Ejemplo.xls»</b></FONT>.
- Las secciones, ventanas y componentes de las herramientas utilizadas se muestran entre comillas inglesas y en negrita. Por ejemplo: **"Create Project"**.
- Las opciones de las herramientas que se asocian a instrucciones (dar clic, seleccionar, etc.) aparecen en color amarillo y cursiva. Por ejemplo: <span class="tag is-warning is-light"><i>New project</i></span>.
- Las secuencias de instrucciones y pasos se muestran en color amarillo, cursiva y negrita. Por ejemplo: <span class="tag is-warning is-light"><b><i>Paso 1 > Paso 2</i></b></span>.
- Las líneas que se escriben directamente en las herramientas, para programar o realizar algún proceso en específico, aparecen en formato de código, con una tipografía distinta de color negro. Por ejemplo: <span class="tag is-light"><b>value.replace(" sp.","")</b></span>.

**Sobre la Herramienta**

El [validador de datos](https://www.gbif.org/es/tools/data-validator/){:target="_blank"} es un servicio de [GBIF](https://www.gbif.org){:target="_blank"} que permite evaluar de manera automática la completitud y otros aspectos de la calidad en los conjuntos de datos estructurados bajo el estándar [*Darwin Core* (DwC)](https://dwc.tdwg.org/terms/){:target="_blank"}. El validador genera un informe sobre la sintaxis y la calidad de los datos. Esto permite detectar posibles problemas en la información antes de publicarla. Por consiguiente, si se somete un [DwC-A](https://www.gbif.org/darwin-core){:target="_blank"}, el validador también evalúa la completitud y estructura de los metadatos en el estándar [EML](https://www.gbif.org/sites/default/files/gbif_resource/resource-80640/gbif_metadata_profile_guide_en_v1.pdf){:target="_blank"}.

**Enlace**

*Data validator*: [gbif.org/es/tools/data-validator/](https://www.gbif.org/es/tools/data-validator/){:target="_blank"}

**Requerimientos** 
* La primera fila del conjunto de datos a validar debe tener el nombre de los elementos DwC en inglés.

* El conjunto de datos debe tener la columna del ID según el tipo de datos que corresponda: <span class="tag is-success is-light"><i>occurrenceID</i></span> (registros biológicos), <span class="tag is-success is-light"><i>eventID</i></span> (eventos de muestreo) o <span class="tag is-success is-light"><i>taxonID</i></span> (listas de especies). La columna debe estar documentada para todas las filas y cada ID debe ser único.

* El validador admite archivos con los siguientes formatos:
  * Formato Excel (.xls o .xlsx).
  * Formato CSV.
  * Archivos *Darwin Core* comprimidos (DwC-A).

**Archivo de trabajo**

Descargue el archivo [<FONT FACE="monospace"><b>«datos_Estructurados.xls»</b></FONT>](https://raw.githubusercontent.com/SIB-Colombia/Formacion/master/LAB/lab01/_docs/datos_Estructurados.xlsx) para realizar el laboratorio.

----

## Paso 1 - Ingreso a GBIF 

Cree una cuenta de usuario en [GBIF](https://www.gbif.org){:target="_blank"} o ingrese con sus credenciales al [validador de datos](https://www.gbif.org/es/tools/data-validator/){:target="_blank"} si ya se encuentra registrado (Fig. 1).

![Figura 1. Ingreso/registro en la página de GBIF](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig.1_dataValidator.png)

<sup>*Figura 1. Ingreso/registro en la página de GBIF.*</sup>

## Paso 2 - Cargar el archivo
Cargue el archivo <FONT FACE="monospace"><b>«datos_Estructurados.xls»</b></FONT> en el validador. Para esto, (1) haga clic en <span class="tag is-warning is-light"><i>SELECCIONAR UN ARCHIVO</i></span> o (2) arrastre el archivo desde una carpeta al ícono <span class="tag is-warning is-light"><i>SOLTAR AQUÍ</i></span>. 

<article class="message is-warning">
  <div class="message-header">
   <p>¡Precaución!</p>
  </div>
  <div class="message-body">
El grado de incertidumbre de la identificación puede indicarse agregando varios calificativos, como “aff.” y “cf.”, al nombre científico. El calificativo se escribe después del elemento al que corresponde la incertidumbre de identificación (género o especie).
  </div>
</article>

El validador le indicará si el conjunto de datos tiene la estructura adecuada para ser publicado a través del SiB Colombia, GBIF y [OBIS](https://obis.org/) o si es necesario realizar ajustes. El informe de validación contiene la siguiente información:

### **2.1. Resumen**
* Un indicador semaforizado (rojo y verde) que indica si el conjunto de datos puede ser indexado (Fig. 2A).
* Resumen del tipo de conjunto de datos (Fig. 2B).
* Alertas de validación que indican **potenciales** problemas en la estructuración y calidad del conjunto de datos (Fig. 2C).

![Figura 2. Componentes del informe - Resumen de validación del conjunto de datos](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig2_datavalid_Informe.png)

<sup>*Figura 2. Componentes del informe - Resumen de validación del conjunto de datos.*</sup>

### **2.2. Frecuencia del término**

* Número de registros (filas) interpretados con éxito (Fig. 3A).
* Reporte del porcentaje de documentación de cada uno de los elementos del estándar DwC utilizados en el conjunto de datos (Fig. 3B).

![Figura 3. Componentes del informe - Frecuencia del término](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig3_datavalid_Informe_frecuencia.png)

<sup>*Figura 3. Componentes del informe - Frecuencia del término*.</sup>

**2.3. Problemas de validación**

* Reporte detallado de los problemas encontrados en el conjunto de datos por cada elemento del DwC (Fig. 4).

![Figura 4. Componentes del informe - Problemas de validación](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig4_datavalid_Informe_problemas.png)

<sup>*Figura 4. Componentes del informe - Problemas de validación.*</sup>

## Paso 3 - Validación

### 3.1. Resultado general de la validación 

Revise el encabezado del reporte. Si aparece en rojo, significa que no puede ser indexado (Fig. 5A). Si aparece en verde, significa que se puede indexar a GBIF (Fig. 5B).

![Figura 5. Posibles resultados de la validación](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig5_datavalid_semaforo.png)

<sup>*Figura 5. Posibles resultados de la validación. A. VERDE, el conjunto de datos puede ser indexado. B. ROJO, no puede indexarse.*</sup>

>¿Su conjunto de datos puede ser indexado?

Las razones más frecuentes por las que un archivo no puede ser indexado son:

<span class="tag is-danger"><b>Mensaje</b></span> **«Registro no identificado de forma única»**: indica que los ID documentados en el elemento DwC <span class="tag is-success is-light"><i>occurrenceID</i></span> (<span class="tag is-success is-light"><i>taxonID</i></span> o <span class="tag is-success is-light"><i>eventID</i></span> según el tipo de datos) no son únicos.

<span class="tag is-danger"><b>Mensaje</b></span> **«No se encontró ni determinó un _rowType_»**: indica que algunas de las columnas obligatorias para realizar la validación no se encuentran en el conjunto de datos. Por ejemplo, <span class="tag is-success is-light"><i>occurrenceID</i></span>, <span class="tag is-success is-light"><i>taxonID</i></span> o <span class="tag is-success is-light"><i>eventID</i></span>, dependiendo del tipo de datos que se esté indexando. 

### 3.2. Ajuste elementos críticos

Si el conjunto no puede ser indexado, revise el mensaje de alerta de la herramienta (Fig. 6), realice los ajustes necesarios y vuelva a correr la validación. Posteriormente, el validador le debe indicar que el conjunto de datos se puede indexar.

> En la sección **"Problemas de validación"**, encontrará los ID que están duplicados.

![Figura 6. Mensaje de alerta - Estructura del recurso](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig6_datavalid_detalleerror.png)

<sup>*Figura 6. Mensaje de alerta - Estructura del recurso. Al hacer clic en las alertas, podrá ver el detalle de los registros que presentan el error para saber qué debe ajustar. Al hacer clic en el ícono de información, obtendrá una descripción detallada del problema*.</sup>

### 3.3. Problemas de validación

Diríjase a la sección **"Problemas de validación"**, donde encontrará varias alertas. El validador indicará el número de registros a revisar para cada una. 

Haga clic sobre las flechas de cada una de las alertas para desglosar de los registros que deben ser revisados y ajustados. Utilice el botón de ayuda para obtener una breve explicación sobre las alertas de validación. (Fig. 7).

![Figura 7. Mensaje de alerta - Interpretación del registro de GBIF](https://raw.githubusercontent.com/gbif/hp-colombian-biodiversity/master/comunidad/formacion/laboratorios/Repositorio_Imagenes/Lab_DataValidator/Fig7_datavalid_detalleerror_2.png)

<sup>*Figura 7. Mensaje de alerta - Interpretación del registro de GBIF. Al hacer clic en las alertas, podrá ver el detalle de los registros que presentan el error para saber qué debe ajustar. Al hacer clic en el ícono de información, obtendrá una descripción detallada del problema*.</sup>

Las alertas se agrupan en 3 categorías según su color:

* Alertas de color <span class="tag is-danger"><b>ROJO</b></span>: indican un error estructural que no permite la indexación del recurso y debe ser corregido.

* Alertas de color <span class="tag is-warning"><b>AMARILLO</b></span>: indican potenciales errores que deben ser revisados en detalle para determinar si se debe o no corregir los datos.

* Alertas de color <span class="tag is-light"><b>GRIS</b></span>: indican el proceso de interpretación realizado por el validador. En la mayoría de los casos, no requieren ajustes importantes en los datos.

### 3.4. Revisión de alertas

Revise todas las alertas de validación y ajuste los datos de acuerdo a estas (Fig. 7).

A continuación se explican las alertas más frecuentes, cómo interpretarlas y cómo solucionarlas:

<span class="tag is-warning"><b>Alerta</b></span> **Base del registro inválida**

- **Problema**: la base del registro (<span class="tag is-success is-light"><i>basisOfRecord</i></span>) no cumple con los requerimientos del estándar.

- **Solución 1**: revise que todos los registros (filas) tengan este elemento documentado.

- **Solución 2**: documente el elemento con base en el vocabulario controlado en inglés (<span class="tag is-success is-light"><i>HumanObservation</i></span>, <span class="tag is-success is-light"><i>PreservedSpecimen</i></span>, <span class="tag is-success is-light"><i>LivingSpecimen</i></span>, <span class="tag is-success is-light"><i>MachineObservation</i></span>, <span class="tag is-success is-light"><i>MaterialSample</i></span>, <span class="tag is-success is-light"><i>FossilSpecimen</i></span>).

<span class="tag is-warning"><b>Alerta</b></span> **Coordenada inválida**

- **Problema**: las coordenadas documentadas no se encuentran estandarizadas en coordenadas decimales o las coordenadas originales no se pueden interpretar.

- **Solución**: asegúrese de que los elementos _Darwin Core_ <span class="tag is-success is-light"><i>decimalLatitude</i></span> y <span class="tag is-success is-light"><i>decimalLongitude</i></span> estén documentados con las coordenadas en formato decimal. Además, corrobore que las coordenadas originales (<span class="tag is-success is-light"><i>verbatimCoordinates</i></span>) hayan sido digitalizadas adecuadamente. 

<span class="tag is-warning"><b>Alerta</b></span> **Se presume latitud negativa**

- **Problema**: posible error en la latitud. Aunque se documentó como latitud sur, posiblemente corresponda a latitud norte (en coordenadas decimales, el norte se indica con un signo menos antes de la latitud).

- **Solución**: asegúrese de que los elementos _Darwin Core_ <span class="tag is-success is-light"><i>decimalLatitude</i></span> y <span class="tag is-success is-light"><i>decimalLongitude</i></span> estén documentados con las coordenadas en formato decimal. Además, corrobore que las coordenadas originales (<span class="tag is-success is-light"><i>verbatimCoordinates</i></span> y <span class="tag is-success is-light"><i>verbatimLongitude</i></span>) hayan sido digitalizadas adecuadamente. 

También puede obtener el mensaje «Se presume longitud negativa», pero es menos común para los datos de Colombia y probablemente corresponda a un problema de digitalización.

<span class="tag is-warning"><b>Alerta</b></span> **Coincidencia del taxón - taxonomía superior**

- **Problema**: el nombre científico fue validado a un nivel taxonómico superior al documentado. Por ejemplo, si el nombre científico corresponde a una especie (género + epíteto específico), significa que el validador solo pudo interpretar el género mas no el epíteto específico.

- **Solución 1**: revise que el nombre científico no contenga calificadores de identificación (*cf.*, *aff.*) u otros calificadores como *sp*.

- **Solución 2**: revise que el nombre científico esté escrito correctamente.

<div class="notification is-info is-light">
  <b>Nota:</b> Es posible que algunos nombres válidos y correctamente escritos sean marcados con esta alerta si no se encuentran en el árbol taxonómico de GBIF. Esto es común en el caso de especíes endémicas o recientemente descritas. En tal caso, ignore la alerta.
</div>

<span class="tag is-warning"><b>Alerta</b></span> **Coincidencia aproximada del taxón**

- **Problema**: hay una coincidencia parcial del nombre cíentífico y el [árbol taxonómico de GBIF](https://www.gbif.org/dataset/d7dddbf4-2cf0-4f39-9b2a-bb099caae36c){:target="_blank"}. Por lo general, esta alerta aparece cuando hay errores de tipeo menores en el nombre científico.

- **Solución**: asegúrese de que el nombre científico esté escrito correctamente.

<span class="tag is-warning"><b>Alerta</b></span> **Fecha registrada inválida**

- **Problema**: las fechas proporcionadas no cumplen con el formato ISO 8601: *AAAA-MM-DD; AAAA-MM; AAAA; AAAA-MM-DD/AAAA-MM-DD*.

- **Solución**: convierta las fechas al formato ISO 8601.

<span class="tag is-light"><b>Alerta</b></span> **Datum geodésico WGS84 asumido**

- **Problema**: el datum geodésico no fue documentado, pero el validador lo identificó como WGS84.

- **Solución 1**: documentar el elemento DwC <span class="tag is-success is-light"><i>geodeticDatum</i></span> como WGS84.

- **Solución 2**: si las coordenadas tienen un datum diferente a WGS84, documéntelo para evitar que el validador lo asuma.

<span class="tag is-light"><b>Alerta</b></span> **Coordenadas redondeadas**

- **Problema**: las coordenadas decimales tienen más de 5 cifras significativas. Más allá de 6 cifras, las coordenadas no mejoran su precisión, por lo que es más eficiente redondearlas.

- **Solución**: no es necesario ajustar las coordenadas, ya que es solo una alerta de interpretación. Sin embargo, si lo desea, puede hacer cambios en el conjunto de datos.


## Paso 4 - Verificación del resultado

Después de resolver las alertas, cargue nuevamente el conjunto de datos en el validador para confirmar el estado de calidad de los datos.

Compare sus resultados con el siguiente archivo, validado según las definiciones del estándar *Darwin Core*, para identificar aciertos y oportunidades de mejora. **¿Logró solucionar todas las alertas?**

* [<FONT FACE="monospace"><b>«Archivo validado»</b></FONT>](https://raw.githubusercontent.com/SIB-Colombia/Formacion/master/LAB/lab01/_docs/datos_Estandarizados.xlsx)

## Paso 5 - Datos propios

Si tiene datos propios que desee publicar, pruebe validarlos siguiendo los pasos de este laboratorio.

Recomendaciones:

Según el origen de sus datos (colecciones biológicas, permisos de recolección, datos marinos, eventos de muestreo), compruebe que los elementos obligatorios estén documentados al 100%. Para ello, utilice como referencia la última [<FONT FACE="monospace"><b>«Plantilla DwC Registros biológicos»</b></FONT>](https://sites.google.com/humboldt.org.co/wikisib/publicar/plantillas?authuser=0){:target="_blank"} y la sección **"Frecuencia del término"** del [validador de datos](https://www.gbif.org/es/tools/data-validator/){:target="_blank"} (Fig. 3B). 

****
**¡Felicitaciones!** Ha mejorado la calidad de su conjunto de datos.

****

**Atribución y uso de los laboratorios**

![](https://licensebuttons.net/l/by/3.0/88x31.png)

La licencia [CC-BY](https://creativecommons.org/licenses/by/4.0/){:target="_blank"} permite usar, redistribuir y construir sobre estos contenidos libremente.
¡La difusión de estos laboratorios contribuirá a la publicación de más y mejores conjuntos de datos sobre biodiversidad!


**Citación sugerida**

> Plata C., Ortíz R., Marentes E., Lozano J. (2021). Laboratorio de datos, Ciclo de formación. Consultado a través del SiB Colombia. Disponible en [https://biodiversidad.co/formacion/laboratorios](https://biodiversidad.co/formacion/laboratorios).
>
