# Esquemático del Diseño - USB Hub 3.2 Gen 1

## Descripción de la carpeta
Esta carpeta contiene el archivo de captura esquemática del proyecto, donde se define toda la lógica electrónica y las conexiones del Hub USB de 6 puertos. 

En el diseño de este esquemático se abordaron los siguientes bloques críticos para el funcionamiento del controlador **USB7006**:
* **Configuración del IC principal:** Asignación de pines y configuración de hardware del USB7006 para habilitar las velocidades SuperSpeed (5Gbps).
* **Red de Distribución de Energía (PDN):** Diseño de la etapa de alimentación para soportar la carga simultánea de los 6 puertos downstream, incluyendo la selección de reguladores de voltaje y capacitores de desacoplo.
* **Protección y Filtrado:** Implementación de supresores de transitorios (TVS) para protección ESD en todos los puertos USB y filtros de ruido para mantener la integridad de la señal.
* **Circuito de Reloj:** Configuración del oscilador de cristal necesario para la temporización de alta precisión del PHY interno.

## Archivos incluidos
* **`TAREA1.DSN`**: Archivo maestro del esquemático, estructurado de manera jerárquica para facilitar la lectura de las distintas etapas del circuito.

## Herramientas utilizadas
* **OrCAD Capture CIS**: Utilizado para la selección de componentes, interconexión lógica y generación del *Netlist* hacia la PCB.