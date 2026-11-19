# Cámara de seguridad inteligente con ESP32

## Objetivo del proyecto

El objetivo de este proyecto es desarrollar un sistema de seguridad simulado capaz de detectar movimiento y cambios en la luminosidad del ambiente. Para ello se utiliza un microcontrolador ESP32 conectado a sensores y un actuador que responde automáticamente ante determinadas condiciones.

Además, el sistema transmite los datos obtenidos mediante WiFi a la plataforma ThingSpeak, donde se pueden visualizar y analizar las mediciones en tiempo real.

## Componentes utilizados

- ESP32.
- Sensor de movimiento.
- Sensor de luminosidad (LDR).
- Actuador de alerta (según el circuito implementado).
- Protoboard y cables de conexión.
- Plataforma de simulación Wokwi.
- Plataforma ThingSpeak para la visualización de datos.

## Funcionamiento general

El ESP32 recibe periódicamente las mediciones de los sensores conectados. El sensor de luminosidad permite conocer el nivel de luz del ambiente, mientras que el sensor de movimiento permite identificar si se detecta actividad.

A partir de estos datos, el microcontrolador ejecuta una condición lógica que determina cuándo debe activarse el actuador. De esta manera, el sistema funciona de forma automática, sin necesidad de intervención manual.

Las mediciones obtenidas también se transmiten a través de una conexión WiFi simulada hacia ThingSpeak, donde se almacenan y representan gráficamente.

## Condiciones de activación del actuador

El actuador se activa automáticamente cuando se cumple la condición lógica establecida en el programa, relacionada con la detección de movimiento y/o el nivel de luminosidad.

La condición específica depende de la programación implementada en el ESP32.

## Conectividad y transmisión de datos

El ESP32 utiliza una conexión WiFi simulada para comunicarse con ThingSpeak.

Los datos enviados al canal son:

- **Field 1:** Luminosidad.
- **Field 2:** Movimiento detectado.

La transmisión de datos se realiza periódicamente, con un intervalo de 30 segundos, utilizando la API de ThingSpeak.

Las credenciales de conexión se configuran de manera local y no se incluyen en el repositorio público.

## Visualización de datos

ThingSpeak permite visualizar la evolución de las mediciones mediante gráficos:

1. Gráfico de luminosidad: representa los cambios en la intensidad de la luz a lo largo del tiempo.
2. Gráfico de movimiento: representa cuándo se detecta movimiento y cuándo no.

Estos gráficos permiten comprobar el funcionamiento del sistema y analizar los datos obtenidos durante la simulación.

## Componentes y programación

El proyecto está programado en Arduino/C++ para el ESP32.

El programa utiliza la función `millis()` para controlar los intervalos de lectura y transmisión, evitando bloquear el funcionamiento principal mediante el uso de `delay()`.

## Instrucciones para ejecutar la simulación

1. Abrir el proyecto en Wokwi.
2. Verificar las conexiones entre el ESP32, los sensores y el actuador.
3. Configurar las credenciales necesarias para WiFi y ThingSpeak.
4. Iniciar la simulación.
5. Comprobar la detección de movimiento y los cambios de luminosidad.
6. Verificar que el actuador responda a las condiciones programadas.
7. Ingresar al canal de ThingSpeak y comprobar la recepción de datos y la actualización de los gráficos.

## Herramientas utilizadas

- Wokwi: simulación del circuito electrónico.
- Arduino IDE / Arduino C++: programación del microcontrolador.
- ThingSpeak: almacenamiento y visualización de datos.
- GitHub: almacenamiento y documentación del proyecto.

## Autor

Proyecto escolar de sistemas electrónicos e Internet de las Cosas (IoT).
