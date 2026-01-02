# stm32-esp32-i2c-telemetry
Sistema de telemetría multi-nodo que integra una STM32L476RG y un ESP32 mediante I2C para la captura de sensores de distancia y temperatura, con visualización dual en servidor web local y dashboards dinámicos en Python.
Este proyecto implementa un sistema robusto de adquisición de datos basado en una arquitectura maestro-esclavo utilizando el protocolo I2C. El objetivo principal es la sincronización de dos ecosistemas de hardware distintos (ARM Cortex-M4 y Xtensa Dual-Core) para procesar y visualizar variables físicas en tiempo real.

El flujo de información sigue esta jerarquía:

Captura de Datos: La STM32L476RG actúa como el nodo de adquisición primaria, leyendo dos sensores de distancia (ej. ultrasónicos) y un sensor de temperatura (ej. termistor o LM35).

Comunicación Inter-Chip: Los datos son empaquetados y transmitidos vía I2C hacia la ESP32.

Gateway & Servidor Web: La ESP32 recibe la información y despliega una interfaz HTML accesible desde cualquier dispositivo en la red local.

Análisis de Datos: Un script de Python consume los datos para generar gráficas avanzadas, permitiendo un análisis visual del comportamiento de los sensores.

🛠️ Tecnologías Utilizadas
Hardware: * STM32L476RG (Núcleo-64)

ESP32 (WROOM-32)

Sensores: Distancia (x2) y Temperatura (x1).

Protocolos de Comunicación: I2C, HTTP, UART.

Software & Lenguajes: * C/C++: Firmware para STM32 y ESP32.

HTML/CSS: Interfaz de usuario embebida en la ESP32.

Python: Procesamiento y visualización de datos (Matplotlib/Plotly).
