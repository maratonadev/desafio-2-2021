[![](https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg)](https://cloud.ibm.com)
[![](https://img.shields.io/discord/734849242153222221?logo=discord)](https://discord.gg/yJYmTGDWKH)

# Desafío 02 | Quanam

- [1. Sobre Quanam y Aleph](#1-sobre-quanam-y-aleph)
  - [1.1. Introducción](#11-introducción)
  - [1.2. Premiación](#12-premiación)
- [2. Desafio de negócio](#2-desafio-de-negócio)
- [3. Objetivo](#3-objetivo)
- [4. Tecnologias aplicadas](#4-tecnologias-aplicadas)
- [5. Desarrollo de la Solución](#5-desenvolvimento-da-solução)
  - [5.1. Pré-requisitos](#51-pré-requisitos)
  - [5.2. Resumen de Tareas](#52-resumo-das-tarefas)
  - [5.3. Desarollo](#53-desenvolvimento)
- [6. Envío](#6-submissão)
- [7. Sobre la evaluación](#7-sobre-a-avaliação)

## Para ayudarte

- [Material de Apoyo](#materiales-de-apoyo)

## 1. Sobre Quanam y Aleph

### 1.1. Introducción

Quanam es una federación internacional de firmas que tiene por objetivo la innovación y la gestión del conocimiento en beneficio de los clientes y la comunidad a través de consultorías de negocios, gestión y aplicación de tecnologías líderes en diferentes segmentos.

Mantiene diversas actividades a nivel internacional, cuenta con 7 oficinas en América, más de 600 clientes y 400 especialistas de alto expertise.

La iniciativa "Aleph" ha sido creada y desarrollada por Quanamen en el marco de una fuerte apuesta por la innovación. El propósito de la iniciativa Aleph es potenciar el crecimiento sostenido de todos los actores de un ecosistema (organizaciones, Pymes, empresas tradicionales, ciudadanos, etc) a través de la dinamización de sus interacciones e integraciones. Tal dinamización se logra mediante la aplicación de metodologías y herramientas de TI que generan espacios de oportunidades, posibilitando la aceleración del ritmo en que una determinada comunidad o ecosistema prospera.

### 1.2. Premiación

En línea con el propósito de nutrir una comunidad capaz de generar soluciones para el proyecto, Quanam destinará recursos para formar y acompañar a través de un mentoring a aquellos desarrolladores ganadores del evento y que deseen acompañar el proyecto. El apoyo vendrá dado en la forma de "Vouchers Aleph". En principio disponibilizaremos 3 vouchers, pero dependiendo de los resultados del concurso podremos disponibilizar alguno más.

El poseedor de cada Vouchers Aleph recibirá un mentoring dirigido a transformar una idea en un modelo de negocio exponencial

- El mentoring se realizará aplicando metodologías de innovación disruptiva.
- El modelo de negocios será formulado de tal forma que podrá ser presentado ante fondos de inversión a definir en conjunto con el ganador.
- La idea no necesariamente tiene que estar relacionada con la maratona.

Cada Voucher Aleph incluye:

- 1 taller para crear modelos de negocios sobre ecosistemas o comunidades Aleph
- Metodología Pentagrowth, una de las metodologías utilizadas por Aleph para crear modelos de negocios disruptivos a partir de una idea provista por el participante
- 3 meses de acompañamiento a cargo de Consultores Aleph
- Acompañamiento en sesiones semanales de 1 hora para explorar juntos el potencial de la idea
  Valor del Voucher: USD 3.000. Los 3 mejores participantes pueden optar por el "Voucher Aleph" o por un vale-compras de US$ 500.

## 2. Desafio de negócio

En un centro de rehabilitación de salud, existen instalados sensores para determinar la calidad de las condiciones ambientales. Se necesita tener control de la calidad del aire y otros parámetros relativos al ambiente, para actuar rápidamente si se detectaran anomalías, ya que las mismas podrían ser muy perjudiciales para los pacientes.

Los sensores están instalados en ubicaciones diversas como: sala de espera, habitaciones, baños, comedor, sala de actividades, oficina, jardín.

Los niveles aceptables de los datos medidos pueden variar según la ubicación del medidor.

Así mismo, en los horarios de visita, los niveles aceptables podrán variar (se asume que podrá haber más contaminación).

Adicionalmente, se cuenta con pulseras que miden el ritmo cardíaco colocadas en pacientes con enfermedades o riesgos cardíacos. El propósito es poder controlar y realizar intervenciones tempranas en pacientes que sufran una descomposición en estos valores.

En la oficina, hay un servidor disponible para el monitoreo de los parámetros medidos, para poder visualizar los niveles de los mismos.

Se requiere desarrollar una solución de software, que lea los datos de los sensores, los evalúede acuerdo a los parámetros establecidos y genere alarmas cuando los datos salgan de los rangos permitidos.

## 3. Objetivo

Desarrollar una solución capaz de:

- Captura de datos de una central IoT y persistencia de los mismos en algún formato estándar. (ej. Archivo CSV);
- Detectar anomalías en cada una de las series de datos. El proceso deberá devolver advertencias, dependiendo de los valores recibidos de los sensores y el ambiente en que se encuentre el sensor.
- Confeccionar un modelo que permita pronosticar las condiciones futuras de una habitación, en base al análisis de los datos pasados. El modelo deberá poder predecir el ritmo cardíaco de los pacientes en la habitación que usan la pulsera, en función de las condiciones ambientales.

## 4. Tecnologias aplicadas

Para este desafío, se utilizarán los siguientes servicios de IBM Cloud:

- [Watson Studio](https://cloud.ibm.com/catalog/services/watson-studio), también conocido como Cloud Pak for Data as a Service. Este servicio permite el uso de una variedad de herramientas relacionadas con la ciencia de datos, incluida la ejecución de Jupyter Notebooks con procesadores en la nube.

- [Cloud Functions](https://cloud.ibm.com/functions), un servicio para execución de funciones en la nube sin necesidad de un servidor (modelo conocido como Serverless).

## 5. Desarrollo de la Solución

### 5.1. Pre-requisitos

Para realizar este desafío, debe cumplir con los siguientes requisitos previos:

- Regístrese en la [Maratón Behind the Code](https://maratona.dev/?register=true) y confirmar tu correo electrónico de registro;
- Tener una [cuenta de IBM Cloud](https://ibm.biz/Bdf8dW), que puede ser una cuenta Lite o Pay-As-You-Go (no es necesario registrarse para el evento con la misma dirección de correo electrónico utilizada para crear tu cuenta de IBM Cloud).

### 5.2. Resumen de Tareas

1. Crear una instancia de los servicios del desafío en IBM Cloud: Object Storage y Watson Studio (opcionales);
2. Crear una API Serverless capaz de generar alertas para los datos de los dispositivos IoT;
3. Recopilar los datos disponibles de los dispositivos IoT;
4. Crear un modelo de Machine Learning capaz de realizar predicciones basadas en datos capturados de los dispositivos;
5. Enviar la solución en la [página del desafío](https://maratona.dev/challenge/2).

### 5.3. Desarollo

#### Parte 1 - Alertas de sensores

Necesitamos generar alertas si las medidas con las que estamos trabajando se salen del rango esperado. Para ello, te pedimos que crees una API sin servidor, usando Cloud Functions. Mire el video a continuación para comprender cómo hacer esto:

<div align="center">
    <a href="https://youtu.be/lq6BXii31Eo">
        <img width="375" src="../img/video.jpg" alt='video'>
    </a>
</div>

La API que creará recibirá los siguientes datos, en formato JSON, como en el siguiente ejemplo:

```json
{
  "room": "bathroom-main",
  "values": {
    "co2": 400,
    "temperature": 22,
    "humidity": 70,
    "sound": 30,
    "illumination": 150
  }
}
```

Y debería devolver un objeto JSON con una lista de medidas con alertas como en el siguiente ejemplo:

```json
{
  "alerts": ["temperature", "humidity"]
}
```

Las alertas de la lista pueden aparecer en cualquier orden.

Los rangos de valores aceptables se definen en la siguiente tabla:

| Dato                         | Unidad de Medida | Ambiente                              | Rango de valores aceptables        |
| ---------------------------- | ---------------- | ------------------------------------- | ---------------------------------- |
| CO2 (`co2`)                  | PPM              | Sala de Actividades (`activity-room`) | Hasta 500                          |
| "                            | "                | Comedor (`refectory`)                 | Hasta 400                          |
| "                            | "                | Habitación 1 (`room-1`)               | Hasta 300                          |
| "                            | "                | Baño Principal (`bathroom-main`)      | Hasta 500                          |
| "                            | "                | Jardín (`garden`)                     | Hasta 500                          |
| Temperatura (`temperature`)  | °C               | Sala de Actividades (`activity-room`) | 19 - 22                            |
| "                            | "                | Comedor (`refectory`)                 | 20 - 23                            |
| "                            | "                | Habitación 1 (`room-1`)               | 21 - 23                            |
| "                            | "                | Baño Principal (`bathroom-main`)      | 22 - 25                            |
| "                            | "                | Jardín (`garden`)                     | 15 - 22                            |
| Humedad (`humidity`)         | %                | Sala de Actividades (`activity-room`) | 50 - 60                            |
| "                            | "                | Comedor (`refectory`)                 | 50 - 70                            |
| "                            | "                | Habitación 1 (`room-1`)               | 50 - 60                            |
| "                            | "                | Baño Principal (`bathroom-main`)      | 60 - 75                            |
| "                            | "                | Jardín (`garden`)                     | 50 - 80                            |
| Sonido (`sound`)             | dB               | Sala de Actividades (`activity-room`) | 0 - 40                             |
| "                            | "                | Comedor (`refectory`)                 | 20 - 35                            |
| "                            | "                | Habitación 1 (`room-1`)               | 10 - 30                            |
| "                            | "                | Baño Principal (`bathroom-main`)      | 20 - 35                            |
| "                            | "                | Jardín (`garden`)                     | 10 - 35                            |
| Iluminación (`illumination`) | Lux              | Sala de Actividades (`activity-room`) | 300 - 750                          |
| "                            | "                | Comedor (`refectory`)                 | 200 - 500                          |
| "                            | "                | Habitación 1 (`room-1`)               | 100 - 200                          |
| "                            | "                | Baño Principal (`bathroom-main`)      | 100 - 200                          |
| "                            | "                | Jardín (`garden`)                     | N/A (Cualquier valor es aceptable) |

#### Parte 2 - Predicción con datos de IoT

Para este desafío, tenemos un _broker_ MQTT disponible online. Este _broker_ está capturando datos de sensores de IoT en un loop y publicándolos en el tema `quanam`, y usted debería capturarlos. En total, hay 3200 muestras de datos diferentes, cada una con los valores de co2 (`CO2`), temperatura (`TEMP`), humedad (`HUMID`), sonido (`SOUND`), iluminación (`ILLUM` ) y ritmo cardíaco (`RYTHM`), junto con un número de identificación de muestra (`ID`), que va de 1 a 3200. El primer paso que debe completar es capturar estos datos del _broker_ y luego hacer un análisis con ellos. A continuación se muestran las credenciales de acceso del _broker_:

```
HOST: iot.maratona.dev
PORT: 31666
USERNAME: maratoners
PASSWORD: btc-2021
```

Nuestro _broker_ utiliza el protocolo MQTT v3.1.1. Al escuchar el tema `quanam`, obtendrá los datos en el siguiente formato:

```json
{
  "ILLUM": "523.98",
  "HUMID": "67.24",
  "CO2": "564.43",
  "SOUND": "36.97",
  "TEMP": "18.6",
  "RYTHM": "73.73",
  "ID": 1994
}
```

Puedes elegir el cliente MQTT que prefieres para capturar los datos. Como recomendación, dejamos [Node-RED](https://nodered.org/docs/getting-started/local), que viene con el nodo `mqtt in` por defecto, listo para usar, o el cliente Python [paho-mqtt](https://pypi.org/project/paho-mqtt/). Recuerda ingresar el usuario y contraseña para suscribirte al tema, de lo contrario no podrás recibir los eventos.

Queremos, a partir de los datos obtenidos vía IoT, hacer una predicción de cuál será el ritmo cardiaco de una persona para saber si está en riesgo o no. Entonces, después de agrupar estos datos, tu tarea es crear un modelo de **regresión** que pueda predecir cuál será el ritmo cardiaco de un paciente en función de las mediciones disponibles. Esta vez, no es necesario publicar el modelo en Watson Machine Learning. Para enviar tus respuestas obtenidas con el modelo, simplemente complete la columna **RYTHM** de las respuestas del [archivo CSV](../../assets/answers.csv) y envíenosla. **No cambie ningún otro dato en el archivo, solo los valores de la columna RYTHM**.

**Nota**: Los datos proporcionados en este desafío son ficticios y no se corresponden con la realidad de ninguna manera.

## 6. Envío

Habiendo completado ambos pasos, el último paso es completar el envío. Recuerda que solo se aceptará un envío para el desafío, así que pruébelo bien antes de enviarlo.

Para enviar, debe acceder a la página de desafío: [https://maratona.dev/challenge/2](https://maratona.dev/challenge/2) y enviar:

- La URL de tu función en Cloud Functions
- El archivo CSV con tus respuestas
- Un archivo `.zip`, de hasta 10 MB, que contiene el código fuente utilizado para el **modelo de regresión**. No incluya el código utilizado para Cloud Functions.

La página se hara una prueba para verificar que los datos sean correctos.

Las evaluaciones solo comenzarán después de la primera semana del desafío. Una vez enviadas, las credenciales para acceder a su solución se guardarán y se utilizarán para la evaluación posteriormente. **¡No elimine ningún servicio utilizado para el desafío antes de la evaluación!** Si los servicios cuyas credenciales fueron enviadas no están disponibles en la fecha de evaluación, la submisión se calificará con cero. En ese caso, se permitirá un nuevo envío.

Podrás seguir el estado del envío accediendo a la [página del desafío](https://maratona.dev/challenge/2), iniciando sesión en su cuenta.

## 7. Sobre la evaluación

Una semana después del inicio del desafío, nuestro sistema de evaluación automatizado iniciará las evaluaciones. Utilizará los datos enviados para calcular una puntuación numérica del 1 al 100, basado en respuestas de alertas IoT y la métrica [R<sup>2</sup>](https://en.wikipedia.org/wiki/Coefficient_of_determination). El archivo `.zip` enviado debe contener todo el código utilizado para el modelo de regresión . De lo contrario, la puntuación se cero.

Si el desafío se entrega dentro del plazo de envío (hasta el 28 de noviembre), el participante recibirá una bonificación del 10% de la puntuación total (10 puntos), independientemente del resultado de su desafío. Por tanto, la puntuación máxima posible es 110 (puntuación de 100 + bonificación de 10).

Después del plazo de envío, el participante aún puede realizar su envío hasta el 12 de diciembre, pero sin recibir el bono.

**Atención**: nos reservamos el derecho de darle a un envío cero de puntuación si:

- El código fuente enviado no es consistente con los resultados obtenidos de las pruebas en el modelo.
- Se detecta plagio, de uno o más participantes. En este caso, se dará cero puntos al desafio entregado por todos los participantes con la misma solución.

## Materiales de apoyo

- [Documentación de Cloud Functions](https://cloud.ibm.com/docs/openwhisk)
- [Tutorial Introductorio a IBM Cloud Functions](https://developer.ibm.com/es/tutorials/cloud-functions/)
- [El Internet de las Cosas es más que una moda, es una revolución tecnológica](https://developer.ibm.com/es/blogs/el-internet-de-las-cosas-es-mas-que-una-moda-es-una-revolucion-tecnologica/)
- [Los 10 principales desafíos de seguridad de IoT](https://developer.ibm.com/es/articles/iot-lp201-iot-architectures/)
- [Introducción a IBM Watson Studio](https://developer.ibm.com/es/articles/introduction-watson-studio/)
- [Visualizar datos con Python](https://developer.ibm.com/es/patterns/visualize-data-with-python/)

Recuerda que puedes acceder al Discord oficial del Maratón 2021 para hacer preguntas y/o interactuar con otros participantes: [Discord](https://discord.gg/yJYmTGDWKH).

## License

Copyright 2021 Maratona Behind the Code

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
