# Esquemático en Formato PDF - USB Hub 3.2 Gen 1

## Descripción de la carpeta
Esta carpeta contiene la versión en formato PDF del esquemático completo del Hub USB de 6 puertos basado en el controlador **USB7006**. 

El propósito de este archivo es facilitar una visualización rápida, impresión y revisión del diseño de manera accesible, permitiendo la consulta de la lógica del circuito sin necesidad de abrir herramientas de CAD especializadas como OrCAD Capture.

## Archivos incluidos
* **`Esquematico.pdf`** : Documento PDF en alta resolución que compila todas las páginas del diagrama esquemático. Está exportado de manera que se mantiene la nitidez de los símbolos, etiquetas de red (*net names*) y texto técnico para una navegación cómoda.

## Secciones críticas disponibles para revisión rápida
Al consultar este documento, se pueden auditar visualmente los siguientes bloques de ingeniería:
* **Pinout del USB7006:** Conexiones de los pares diferenciales de alta velocidad y pines de configuración de hardware.
* **Red de Distribución de Energía (PDN):** Esquema de los reguladores de voltaje, circuitos de protección por sobrecorriente y la matriz de capacitores de desacoplo para los 6 puertos downstream.
* **Protección ESD:** Ubicación y conexión de los diodos supresores de transitorios (TVS) en las líneas de datos de cada conector USB.
* **Señales de Control y Reloj:** El circuito del oscilador de cristal y las líneas auxiliares de reset/sincronización.

## Ventajas de este formato
* **Portabilidad:** Permite inspeccionar el diseño desde cualquier dispositivo (computadora, tablet o móvil).
* **Revisiones de Diseño (Design Reviews):** Ideal para compartir el circuito con otros ingenieros, clientes o proveedores de manufactura que no posean licencias de la suite de Cadence (OrCAD/Allegro).
* **Búsqueda de Texto:** Permite la búsqueda directa de componentes (*RefDes* como R1, C1, U1) o nombres de señales específicas utilizando el buscador nativo del lector de PDF.
