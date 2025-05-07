# **LibreIncu: Tecnología Libre para la Soberanía Alimentaria en la AFCI**

video: [Incubadoras AlterMundi](https://www.youtube.com/watch?v=WrC1Y-ACtMoç)

## **Introducción al Proyecto**

LibreIncu es una iniciativa de soberanía tecnológica y alimentaria desarrollada colaborativamente por AlterMundi y Comunidad, Trabajo y Organización (CTO), junto con diversas organizaciones de la Agricultura Familiar, Campesina e Indígena (AFCI) de la provincia de Córdoba, Argentina. El proyecto busca romper la triple dependencia que enfrenta la AFCI en la producción avícola:

1. **Dependencia genética**: El "pollito bebé híbrido" utilizado tanto en la industria como por pequeños productores proviene de un oligopolio mundial (Cobb-Vantress y Aviagem), que controlan la genética de todos los pollos industriales.  
2. **Dependencia alimentaria**: La dieta de estos pollos requiere precursores de crecimiento, núcleos vitamínicos y minerales de origen industrial, además de maíz y soja del modelo del agronegocio.  
3. **Dependencia tecnológica**: Las incubadoras comerciales son inaccesibles por su costo o están diseñadas para hobbistas, no para producción familiar.

Como respuesta a este problema, LibreIncu presenta una incubadora avícola con tecnología de monitoreo y control en línea, diseñada específicamente para las necesidades de la AFCI, permitiendo la recuperación del "saber ancestral" y el desarrollo de genética propia para la transición hacia un modelo agroecológico integral.

## **video:[Equipo de Desarrollo LibreIncu. Sistemas de Monitoreo y Control](https://youtu.be/SZky4Ak8hUw)**

## **Hardware**

La incubadora LibreIncu es el resultado de un cuidadoso proceso de diseño iterativo , buscando crear un dispositivo accesible, eficiente y adaptado a las necesidades específicas de la AFCI. Además, usa componentes disponibles en el mercado y fáciles de reemplazar. 

### **Especificaciones técnicas**

* **Dimensiones**: 100 cm de altura, 50 cm de ancho y 50 cm de profundidad  
* **Capacidad**: 150 huevos en tres bandejas de incubación, con 50 huevos de nacedora  
* **Sistema de control térmico**:  
  * Resistencia calefactora de 200W ubicada en la base (la misma que una panchera industrial)  
  * Sensor BME280 para monitoreo preciso de temperatura, humedad y presión  
  * Ventilador de distribución de aire (modelo Turbina Cooler Extractor Fan)  
  * Control de temperatura objetivo de promedio 37.8°C  
* **Sistema de humidificación**:  
  * Microaspersor con sistema de carga automática de agua  
  * Presión de trabajo de 3 bar  
  * Bomba de nafta (tipo genérica automotor)  
  * Control integrado con el sistema de temperatura  
* **Sistema de rotación**:  
  * Motor de rotación ubicado en la parte superior  
  * Sistema de cinta de tracción para movimiento de bandejas  
  * Sensores Reed para detectar posiciones extremas (los de alarma)   
  * Rotación automática programable  
* **Control electrónico**:  
  * Microcontrolador ESP32 como cerebro del sistema  
  * Conectividad WiFi para control remoto  
  * Aplicación LibrePollo para Android  
  * Interfaz para visualización de datos históricos en Grafana

El diseño físico incluye un circuito de convección forzada para una distribución uniforme del calor, con el aire caliente generado por la resistencia ascendiendo por detrás de las bandejas, acumulándose en el techo, y siendo forzado hacia abajo por el ventilador por la parte frontal.

En las pruebas realizadas, LibreIncu ha logrado un índice de eclosión del 86%, comparable con las mejores marcas comerciales pero con un costo significativamente menor y adaptada específicamente a las necesidades de pequeños productores.

## **Software**

El ecosistema de software de LibreIncu está diseñado para facilitar el monitoreo remoto y control automático de la incubadora, ofreciendo una interfaz intuitiva y accesible para los usuarios.![][image2]

Cada incubadora emite una red wifi cuyo nombre empieza con el nombre “incu-” seguida de un número. Un usuario que desee controlar su incubadora se puede conectar a ese wifi. Además cada incubadora se conecta a la red wifi para enviar datos por internet a un servidor.

**Firmware de la incubadora** 

El firmware de la incubadora, alojado en la carpeta /src/embedded del [repositorio](https://github.com/AlterMundi-MonitoreoyControl/Proyecto-Incubadora/tree/main/src/embedded#readme) del proyecto, es el componente de software que corre directamente en el microcontrolador del sistema de control. Está desarrollado para gestionar de forma autónoma el funcionamiento de la incubadora, manteniendo condiciones ambientales óptimas para el desarrollo de los embriones.

El firmware utiliza nodemcu y está escrito en lua, un lenguaje sencillo para propiciar la apropiación del software por parte de las comunidades. 

### 

###       **Aplicación LibrePollo para Android**

La aplicación móvil LibrePollo permite supervisar y controlar la incubadora desde cualquier dispositivo Android, ofreciendo las siguientes funcionalidades:

* Información en tiempo real sobre el estado de conexión WiFi, estado de rotación, temperatura y humedad actuales.  
* Permite gestionar hasta tres bandejas de incubación, indicando si están vacías o en uso con un ciclo activo con contador de días.  
* **Permite ajustar**  temperatura máxima y mínima, niveles de humedad, período de incubación e intervalos de rotación. Además cuenta con un cont**rol manual de rotación**,  y por último informa sobre problemas con el sensor, rotación o conexión a internet.

### 

### **Sistema de registro y visualización de datos (Grafana)**

Complementando la aplicación móvil, LibreIncu integra Grafana para el almacenamiento y visualización de datos históricos:

* Gráficos históricos de temperatura y humedad  
* Análisis de tendencias para optimizar el proceso de incubación  
* Identificación de patrones o problemas en el funcionamiento  
* Acceso mediante conexión WiFi a internet

Este sistema permite no solo el monitoreo en tiempo real, sino también el análisis posterior para mejora continua del proceso de incubación, facilitando el aprendizaje colectivo y el intercambio de experiencias entre las diferentes organizaciones participantes.

![][image3]

## **video:[Las voces de las comunidades que recibieron la LibreIncu](https://youtu.be/KnWVigydmrw)**

## **Impactos positivos:**

Ya hay 8 LibreIncus en producción en comunidades de la provincia de Córdoba con las cuáles el equipo de Desarrollo compartió capacitaciones tanto en la parte productiva avícola (manejo de reproductores y huevos fértiles) como en lo tecnológico (manejo del artefacto y software). Las características distintivas de nuestra incubadoras son:

1) La automatización de la carga de agua y el control de la humedad, ahorran tiempo real de trabajo frente al artefacto.  
2) El monitoreo online, permite hacer el seguimiento de las variables de Tº,Hº y rotación por parte de l@s productor@s a través de un teléfono android de manera remota, ahorrando el tiempo de “ir a ver” la incubadora.  
3) La eficiencia del sistema de control de Hº y Tº y la ubicación de cada bandeja y la nacedora, lograron una eficiencia del 86% de eclosión, igual o superior a las mejores marcas del mercado.  
4) El tamaño y diseño de la LibreIncu está pensado para que una familia con pocos reproductores (15 gallinas y 2 gallos) pueda cargar todas las semanas 50 huevos, en un ciclo continuo de 21 días hasta el nacimiento.  
5) El registro prolijo y completo mediante formularios de las cargas de incubadora y el uso de un  obvoscopio casero (agregar foto) a los 18 días, nos permite diagnosticar con mayor certeza los problemas que pueden surgir en el proceso productivo; cruzando estos datos de nacimientos con el registro histórico de grafana.

**Proyección a dos años**

Nuestro equipo está trabajando en un  Ecosistema Tecnológico para Economía Social y la Producción Sustentable. Un conjunto integrado de sistemas, cada uno enfocado en producciones específicas, que incluye:

* Innovaciones tecnológicas adaptadas a las necesidades locales.  
* Caracterización productiva de los procesos.  
* Curaduría de materiales bibliográficos y manuales técnico-productivos.  
* Definición de requerimientos físicos y estructurales.  
* Interfaces de usuario amigables y accesibles

Este Ecosistema gira alrededor de las necesidades reales, explicitadas en 1ra persona por los protagonistas de la Economía Social y la Producción Sustentable. Implica proponer soluciones a través de la Innovación tecnológica que sean  social y ambientalmente pertinentes. Cada subsistema se construye y ensambla a partir de un **núcleo común de HardWare o Software**, al cual se van anexando, de manera modular, una diversidad de complementos, capas o funcionalidades (físicas o de SW) acordes a las necesidades específicas de cada producción o contexto. Estos subsistemas se integran de manera complementaria, en un **sistema mayor**, que no solo da respuestas a un producción o cadena específica; sino que intenta acompañar al sujeto de la economía y la producción social. La **modularidad** facilita la **adaptación a diferentes realidades productivas** y promueve la **apropiación tecnológica** por parte los trabajadores y los productores.

### **Objetivos a corto plazo**

1. **Fortalecimiento técnico-productivo**: Desarrollo de un programa estructurado de capacitación y acompañamiento a las organizaciones de la AFCI para el manejo integral de la producción avícola agroecológica.  
2. **Perfeccionamiento tecnológico**: Mejora continua del diseño y funcionalidad de la incubadora LibreIncu basado en la retroalimentación de usuarios y validación técnica del INTI.  
3. **Desarrollo genético autónomo**: Establecimiento de planteles reproductores en cada organización mediante la incorporación de gallos de razas pesadas y gallinas criollas regionales.  
4. **Alimentación agroecológica**: Formulación, prueba y sistematización de dietas agroecológicas específicas para cada etapa productiva avícola.  
5. **Expansión tecnológica**: Adaptación del sistema de monitoreo y control LibreIncu para su aplicación en plantineras hortícolas, como primer paso hacia la expansión del ecosistema tecnológico.

### **video [Incubadoras AlterMundi](https://www.youtube.com/watch?v=WrC1Y-ACtMo)**

### **Visión a largo plazo**

En el largo plazo, el proyecto aspira a generar una transformación profunda en los sistemas productivos avícolas de la AFCI en Argentina, desarrollando un modelo replicable que gradualmente pueda extenderse a otras regiones y escalas.

Se busca que las organizaciones participantes desarrollen completa autonomía en la producción avícola, desde el manejo genético para la producción de sus propios pollitos con características genéticas adaptadas, hasta la producción de carne de pollo agroecológica que se comercialice en mercados locales.

Esta visión de largo plazo implica establecer las bases para un cambio de paradigma, demostrando la viabilidad de sistemas productivos que no dependan de antibióticos preventivos, dietas industriales o genética controlada por corporaciones. A través de la combinación de tecnología apropiada y conocimiento agroecológico, se busca construir sistemas alimentarios más justos, resilientes y soberanos, donde la tecnología sirva a las necesidades de los pueblos.

Por otro lado, la construcción del  Ecosistema Tecnológico para Economía Social y la Producción Sustentable, implica desafíos metodológicos y técnicos, que sigan poniendo a los usuarios finales (los productores o trabajadores), en el centro de los procesos de I\&D, respondiendo a demandas y necesidades reales, desde un paradigma social y ambientalmente justo, que promueva prácticas transformadoras y sustentables.

**Anexo**  enlaces para:  
   
a)Notas y artículos periodísticos  
 b)videos de difusión.  
 c) Artículos académicos  
 d) Materiales para el Usuario Final

a)**Artículos y notas**

Tiempo Argentino.Tiempo Rural.

Crean “LibreIncu”, una incubadora para familias productoras que funciona con software libre  
 [https://bit.ly/LibreIncu](https://bit.ly/LibreIncu)

Pagina 12\.

Problemas en la salud, maltrato animal y pérdida de soberanía. ¿Qué hacer con la industria avícola?  
 [https://www.pagina12.com.ar/798691-que-hacer-con-la-industria-avicola](https://www.pagina12.com.ar/798691-que-hacer-con-la-industria-avicola)

Multimedio Comechingones: 

INCUBADORAS LIBRES Y LA SOBERANÍA ALIMENTARIA Y TECNOLÓGICA.  
 [https://www.youtube.com/watch?v=XAIEJV1IsmM](https://www.youtube.com/watch?v=XAIEJV1IsmM)

Radio Pueblo 103.3

Somos Tierra (programa) 07/03  
 “LibreIncu”, una incubadora para familias productoras que funciona con software libre.  
 [https://www.facebook.com/100064102022746/posts/pfbid0N8CtLHdo2AVj12pVsAtcoeShCmByB2GCyXqmLqw75aoo8GYHFhkMTCCCVQQF8PBvl/?app=fbl](https://www.facebook.com/100064102022746/posts/pfbid0N8CtLHdo2AVj12pVsAtcoeShCmByB2GCyXqmLqw75aoo8GYHFhkMTCCCVQQF8PBvl/?app=fbl)

CDM Noticias: 

👉🏽En una entrevista radial con CDM Noticias, Fabricio Puzio, integrante de la organización rural CTO y uno de los impulsores del proyecto, brindó detalles del proyecto  
 [https://cdmnoticias.com.ar/2025/03/11/libreincu-una-incubadora-de-pollos-con-software-libre-para-la-agricultura-familiar-en-cordoba/](https://cdmnoticias.com.ar/2025/03/11/libreincu-una-incubadora-de-pollos-con-software-libre-para-la-agricultura-familiar-en-cordoba/)

b) **Videos**

1. En este video encontrarán las voces de las comunidades que recibieron la incubadora en 1ra persona:  
    Youtube: [https://youtu.be/KnWVigydmrw](https://youtu.be/KnWVigydmrw)  
    Drive (para descarga archivo):  
    [https://drive.google.com/file/d/1XJGJvUBiZXpjTJCaMYPYS3Le8TjS4YHT/view?usp=drive\_link](https://drive.google.com/file/d/1XJGJvUBiZXpjTJCaMYPYS3Le8TjS4YHT/view?usp=drive_link)

2. Este video resume la actividad de febrero de 2025, dónde se realizó una capacitación técnica sobre el uso de la incubadora y su entrega a las comunidades:  
    Youtube: [https://youtu.be/x1D\_cCt7HYg](https://youtu.be/x1D_cCt7HYg)  
    Drive (archivo):  
    [https://drive.google.com/file/d/1NNPJ5\_CfbWtDd18YyunTMB\_yW\_l8wr9t/view?usp=drive\_link](https://drive.google.com/file/d/1NNPJ5_CfbWtDd18YyunTMB_yW_l8wr9t/view?usp=drive_link)

3. En este video, encontrarán las voces del Equipo de Altermundi, reflexionando sobre el proceso de desarrollo.  
    Youtube: [https://youtu.be/SZky4Ak8hUw](https://youtu.be/SZky4Ak8hUw)  
    Drive (archivo):  
    [https://drive.google.com/file/d/1BhJ7BwKUeTCceVNzBBIgxEsvleegejvH/view?usp=drive\_link](https://drive.google.com/file/d/1BhJ7BwKUeTCceVNzBBIgxEsvleegejvH/view?usp=drive_link)

4. En este video encontrarán testimonios sobre lo que implica el proyecto de desarrollo para las organizaciones involucradas.  
    Youtube: [https://youtu.be/OzdKqgwdBYY](https://youtu.be/OzdKqgwdBYY)

5. En este video encontrarán una presentación técnica Incubadora, con sus componentes:  
    [https://www.youtube.com/watch?v=WrC1Y-ACtMo](https://www.youtube.com/watch?v=WrC1Y-ACtMo)  
    Corte cuadrado 1:  
    [https://drive.google.com/file/d/1Y\_UQ-bno3-HFeVKtA\_xg6CsesUtA-4hE/view?usp=drive\_link](https://drive.google.com/file/d/1Y_UQ-bno3-HFeVKtA_xg6CsesUtA-4hE/view?usp=drive_link)  
    Corte cuadrado 2:  
    [https://drive.google.com/file/d/13rHx7xk9e1rThg5PIM3QHikm3YS5sNPg/view?usp=drive\_link](https://drive.google.com/file/d/13rHx7xk9e1rThg5PIM3QHikm3YS5sNPg/view?usp=drive_link)

6. En este video encontrarán testimonios sobre la 1er Capacitación realizada con las comunidades sobre manejo productivo de huevos fértiles e incubadora.  
    [https://youtu.be/IfGGvOIJ1b8](https://youtu.be/IfGGvOIJ1b8)  
    [https://drive.google.com/file/d/1ajWQofPJQxNfXo5LtOdFrOzkCoTbWGiC/view?usp=sharing](https://drive.google.com/file/d/1ajWQofPJQxNfXo5LtOdFrOzkCoTbWGiC/view?usp=sharing)

**c) Artículos Académicos**

1)X Congreso Latinoamericano de Agroecología \- Asunciónd el Paraguay.  
 Innovación tecnológica y productiva en la cadena avícola para la agricultura familiar,campesina e indígena (AFCI). Córdoba-Argentina. Fabricio Puzio.  
 [https://indico.una.py/event/3/contributions/772/](https://indico.una.py/event/3/contributions/772/)



d)**Materiales para usario Final:**

1) [https://hackmd.io/@pablomonte/Documentacion\_LibreIncu](https://hackmd.io/@pablomonte/Documentacion_LibreIncu)
