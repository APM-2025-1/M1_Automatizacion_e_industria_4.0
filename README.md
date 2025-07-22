<div align="center">
<picture>
    <source srcset="https://imgur.com/5bYAzsb.png" media="(prefers-color-scheme: dark)">
    <source srcset="https://imgur.com/Os03JoE.png" media="(prefers-color-scheme: light)">
    <img src="https://imgur.com/Os03JoE.png" alt="Escudo UNAL" width="350px">
</picture>

<h3>AUTOMATIZACIÓN DE PROCESOS DE MANUFACTURA</h3>

<h1>Módulo 1 - Automatización e industria 4.0</h1>

<h2>Mep Mep Raideres</h2>

<h5>Joan Sebastian Arcila Cardozo<br>
    Juan Sebastian Daleman Martinez<br>
    Daniel Santiago Muñoz Bernal<br>
    Maria Alejandra Pérez Petro<br>
    Emma Carolina Sarmiento Cabarcas</h5>

<h6>Universidad Nacional de Colombia<br>
    Facultad de Ingeniería<br>
    Departamento de Ingeniería Mecánica y Mecatrónica<br>
    Bogotá, Colombia<br>
    2025</h6>
</div>


<details>
    <summary>🗂️ Tabla de Contenido</summary>

<!-- TOC -->
- [](#)





</details>

# 1. Diagramas de instrumentación (identificación de sensores y actuadores)

El sistema de automatización implementado en la planta cuenta con una instrumentación precisa que permite la supervisión y control de cada etapa del proceso. En los gabinetes eléctricos se han identificado sensores como sensores fotoeléctricos difusos (SICK WTB4-3P1361), utilizados para la detección de piezas en las bandas transportadoras, y sensores de temperatura y humedad para el monitoreo ambiental. Como actuadores se incluyen contactores, resistencias calefactoras, lámparas piloto, balizas acústicas y motores eléctricos controlados mediante relés y salidas digitales del PLC.

Cada sección de la planta tiene su propio conjunto de dispositivos. Por ejemplo, los sensores fotoeléctricos están distribuidos a lo largo de la línea para garantizar la detección precisa de productos. Las señales de entrada provenientes de estos sensores son canalizadas a tarjetas de entradas digitales, mientras que las señales de salida hacia actuadores como balizas y lámparas son gestionadas por tarjetas de salidas digitales.

# 2. Arquitectura de control y comunicaciones utilizadas
La arquitectura de control está basada en una estructura jerárquica dividida en tres niveles de la pirámide de automatización:

Nivel de Campo: incluye sensores, actuadores y bornas distribuidas para señales analógicas y digitales.

Nivel de Control: constituido por controladores PLC X90 de B&R (modelo X90CP174.48-00 y módulos de expansión), encargados del procesamiento lógico y control de procesos.

<img width="887" height="550" alt="Screenshot 2025-07-21 221636" src="https://github.com/user-attachments/assets/6b95202b-0c82-4b0f-8b4c-a325b0823add" />

Nivel de Supervisión: conformado por una HMI táctil de 5.7” (modelo 4PPC70.0573-20W) para operación local, e interfaces de red para acceso remoto.

<img width="1020" height="481" alt="Screenshot 2025-07-21 221603" src="https://github.com/user-attachments/assets/f0fdf06e-195d-4f6d-8dd4-076246d7a809" />

Las comunicaciones en el sistema están soportadas por:

Ethernet industrial, utilizando switches NS-206AF para conexión entre módulos y acceso a redes superiores.

RS-485, destinada a comunicación entre sensores/actuadores específicos con los módulos del PLC.

Modem satelital y Firewall VPN, que permiten conectividad remota segura para monitoreo en la nube.

Los protocolos utilizados incluyen Modbus RTU, Ethernet/IP y protocolos propietarios de B&R Automation.

# 3. Tecnologías de Industria 4.0 y relación con la transformación digital
El diseño propuesto integra diversas tecnologías de la Industria 4.0 que fortalecen la capacidad de digitalización y mejora continua del proceso:

Gemelo Digital (Modelo Ciberfísico): La planta ha sido modelada virtualmente en un entorno CAD, lo que permite simular, validar y ajustar el comportamiento del sistema antes de su implementación física. Esto facilita el mantenimiento predictivo y la mejora del diseño sin interrumpir la producción.

<img width="994" height="500" alt="PlantaProyecto" src="https://github.com/user-attachments/assets/55170fd6-91ab-4f99-8161-de3631bafffa" />

IIoT (Internet Industrial de las Cosas): Se incorporan elementos conectados como sensores y actuadores con capacidad de transmisión de datos en tiempo real hacia plataformas de análisis o supervisión. Esto posibilita el diagnóstico remoto, el ajuste de parámetros y la recopilación de datos para análisis predictivos.

Ambas tecnologías contribuyen al proceso de transformación digital industrial, permitiendo a la planta migrar de una operación tradicional hacia un entorno inteligente, flexible y adaptativo, en donde el análisis de datos y la interconectividad son claves para la toma de decisiones y la eficiencia operativa.

