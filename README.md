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
- [1. 📊🛂 Diagramas de instrumentación.](#1--diagramas-de-instrumentación)
- [2. 🏗️🎛️ Arquitectura de control y comunicaciones utilizadas](#2-️️-arquitectura-de-control-y-comunicaciones-utilizadas)
- [3. 👨🏻‍💻🏭 Tecnologías de Industria 4.0 y relación con la transformación digital](#3--tecnologías-de-industria-40-y-relación-con-la-transformación-digital)

</details>

# 1. 📊🛂 Diagramas de instrumentación.

El sistema de automatización implementado en la planta cuenta con una instrumentación precisa que permite la supervisión y control de cada etapa del proceso. En los gabinetes eléctricos se han identificado sensores como sensores fotoeléctricos difusos (SICK WTB4-3P1361), utilizados para la detección de piezas en las bandas transportadoras, y sensores de temperatura y humedad para el monitoreo ambiental. Como actuadores se incluyen contactores, resistencias calefactoras, lámparas piloto, balizas acústicas y motores eléctricos controlados mediante relés y salidas digitales del PLC.

<img width="5405" height="5934" alt="Diagrama en blanco" src="https://github.com/user-attachments/assets/c4922647-4400-454a-8a6d-b1f6bd2138f9" />

Cada sección de la planta tiene su propio conjunto de dispositivos. Por ejemplo, los sensores fotoeléctricos están distribuidos a lo largo de la línea para garantizar la detección precisa de productos. Las señales de entrada provenientes de estos sensores son canalizadas a tarjetas de entradas digitales, mientras que las señales de salida hacia actuadores como balizas y lámparas son gestionadas por tarjetas de salidas digitales.

# 2. 🏗️🎛️ Arquitectura de control y comunicaciones utilizadas

La arquitectura de control del sistema ha sido diseñada siguiendo un enfoque jerárquico conforme a la pirámide de automatización industrial, y se estructura en tres niveles. En el nivel de campo se ubican los elementos encargados de la interacción directa con el proceso físico, como los sensores fotoeléctricos difusos SICK WTB4-3P1361, que permiten la detección de objetos en movimiento sobre las bandas transportadoras. También se encuentran en este nivel los motores eléctricos trifásicos SEW-EURODRIVE DRN, que se encargan de generar el movimiento mecánico de las líneas de transporte, así como diversos actuadores de señalización y bornas distribuidas para la correcta conexión, protección y canalización de señales tanto analógicas como digitales.

El nivel de control está conformado por un sistema modular basado en la plataforma B&R Automation X90. El corazón del sistema es el controlador principal X90CP174.48-00, responsable de ejecutar la lógica de control, supervisar el proceso y gestionar las comunicaciones con los dispositivos de campo y los sistemas superiores. Este controlador se complementa con módulos de expansión como las tarjetas X90DI110.10-00 para entradas digitales, X90RO440.05-00 para salidas digitales, X90AT910.08-00 para entradas analógicas en corriente y X90AO410.04-00 para salidas analógicas. Esta configuración permite una implementación flexible y escalable, adaptable a los requerimientos específicos de cada etapa del proceso.

<img width="887" height="550" alt="Screenshot 2025-07-21 221636" src="https://github.com/user-attachments/assets/6b95202b-0c82-4b0f-8b4c-a325b0823add" />

En el nivel de supervisión se encuentra una HMI táctil de 5.7 pulgadas, modelo 4PPC70.0573-20W, que brinda al operador una interfaz gráfica para visualizar variables del proceso, introducir comandos manuales y recibir mensajes de alerta. Este nivel también incluye capacidades de acceso remoto mediante una red protegida por firewall y conectividad satelital, lo que garantiza un monitoreo seguro desde ubicaciones remotas y facilita tareas de diagnóstico y mantenimiento sin necesidad de presencia física en la planta.

<img width="1020" height="481" alt="Screenshot 2025-07-21 221603" src="https://github.com/user-attachments/assets/f0fdf06e-195d-4f6d-8dd4-076246d7a809" />

En cuanto a las comunicaciones industriales, el sistema utiliza una red mixta compuesta por tecnología Ethernet industrial y RS-485. La conexión entre los módulos del PLC, la HMI y los dispositivos de red se realiza mediante switches industriales NS-206AF, los cuales ofrecen cuatro puertos RJ-45 y dos puertos de fibra óptica multimodo tipo SC. Para la comunicación robusta y de largo alcance con sensores distribuidos o módulos remotos se emplea el protocolo RS-485, conectado directamente a los módulos del PLC. Además, el acceso a servicios en la nube y a plataformas de teleasistencia se realiza a través de un módem satelital de banda Ku, en conjunto con un firewall que garantiza la ciberseguridad mediante túneles VPN.

Finalmente, el sistema integra diversos protocolos de comunicación para asegurar la compatibilidad y eficiencia operativa. Se utiliza Modbus RTU para la comunicación serial con dispositivos del nivel de campo, Ethernet/IP para la red principal entre dispositivos críticos como el PLC y la HMI, y protocolos propietarios de B&R como POWERLINK y Automation Runtime, que permiten una sincronización precisa, configuración automática de dispositivos y un alto nivel de integración en entornos de automatización industrial avanzados.

# 3. 👨🏻‍💻🏭 Tecnologías de Industria 4.0 y relación con la transformación digital
El diseño propuesto integra diversas tecnologías de la Industria 4.0 que fortalecen la capacidad de digitalización y mejora continua del proceso:

Gemelo Digital (Modelo Ciberfísico): La planta ha sido modelada virtualmente en un entorno CAD, lo que permite simular, validar y ajustar el comportamiento del sistema antes de su implementación física. Esto facilita el mantenimiento predictivo y la mejora del diseño sin interrumpir la producción.

<img width="994" height="500" alt="PlantaProyecto" src="https://github.com/user-attachments/assets/55170fd6-91ab-4f99-8161-de3631bafffa" />

IIoT (Internet Industrial de las Cosas): Se incorporan elementos conectados como sensores y actuadores con capacidad de transmisión de datos en tiempo real hacia plataformas de análisis o supervisión. Esto posibilita el diagnóstico remoto, el ajuste de parámetros y la recopilación de datos para análisis predictivos.

Ambas tecnologías contribuyen al proceso de transformación digital industrial, permitiendo a la planta migrar de una operación tradicional hacia un entorno inteligente, flexible y adaptativo, en donde el análisis de datos y la interconectividad son claves para la toma de decisiones y la eficiencia operativa.

