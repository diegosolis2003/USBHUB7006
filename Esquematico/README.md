# Esquemático del Diseño (PDF) - USB Hub 3.2 Gen 1

## Descripción de la carpeta
Esta carpeta contiene la exportación en formato PDF del diagrama esquemático completo para el proyecto del Hub USB de 6 puertos, basado en el controlador **USB7006**. 

El objetivo de proporcionar este archivo es facilitar la revisión, auditoría y consulta rápida del diseño electrónico sin la necesidad de instalar o tener acceso a herramientas CAD especializadas (como OrCAD Capture).

## Archivos incluidos
* **`Esquematico.pdf`**: Documento principal que contiene todas las hojas del esquemático del proyecto. La exportación conserva la legibilidad de los componentes, etiquetas de red (*net names*) y anotaciones técnicas.

## Secciones disponibles para revisión
Al explorar este documento, se pueden auditar visualmente los siguientes bloques críticos de ingeniería:
* **Configuración del USB7006:** Mapeo de pines, configuración de hardware y ruteo lógico de los pares diferenciales SuperSpeed.
* **Red de Distribución de Energía (PDN):** Diseño de la etapa de alimentación, incluyendo reguladores de voltaje, manejo de corriente para los 6 puertos downstream y la matriz de capacitores de desacoplo.
* **Protección y Filtrado:** Ubicación de los diodos supresores de transitorios (TVS) para la protección contra descargas electrostáticas (ESD) en todas las interfaces USB.
* **Reloj y Control:** Circuito del oscilador de cristal de precisión requerido por el PHY del controlador.

## Casos de uso del archivo
* **Revisiones de Diseño (Design Reviews):** Permite compartir fácilmente la lógica del circuito con otros ingenieros o revisores técnicos.
* **Auditoría Rápida:** Ideal para buscar rápidamente componentes específicos (*RefDes*) o seguir la ruta de una señal utilizando la función de búsqueda de cualquier lector de PDF.
* **Referencia de Ensamblaje y Pruebas:** Útil como guía de referencia rápida en el laboratorio al momento de hacer *debugging* o verificar voltajes en la placa física.
