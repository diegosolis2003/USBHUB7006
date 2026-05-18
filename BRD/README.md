# Diseño de la Placa (Layout) - USB Hub 3.2 Gen 1

## Descripción de la carpeta
Esta carpeta contiene el archivo de diseño físico (PCB Layout) del Hub USB. El objetivo principal de esta etapa fue traducir el esquemático a una placa funcional, priorizando un factor de forma (Form Factor) compacto similar al de un producto comercial, sin sacrificar la integridad de la señal.

El trabajo de diseño en esta placa (Layout) se centró en los siguientes retos de ingeniería:
* **Ruteo de Alta Velocidad (High-Speed):** Trazado meticuloso de las señales SuperSpeed a 5Gbps. Esto requirió un estricto control de impedancia diferencial en las pistas de TX y RX de los puertos USB 3.2.
* **Manejo de Pares Diferenciales:** Aplicación de técnicas de *length matching* (igualación de longitudes) y control de fase para evitar atenuación, reflexiones y *crosstalk* entre las líneas de datos de los 6 puertos.
* **Estrategia de Placement:** Ubicación de componentes de alta densidad para reducir el área total de la tarjeta, posicionando los capacitores de desacoplo y protecciones ESD lo más cerca posible de los conectores y del IC **USB7006**.
* **Gestión Térmica y de Potencia:** Diseño de planos de cobre internos para una distribución eficiente de la energía (VDD/GND) y disipación térmica del controlador principal.

## Archivos incluidos
* **`tarea1.brd`**: Archivo final de la placa de circuito impreso, listo para la generación de archivos de manufactura (Gerbers).

## Herramientas utilizadas
* **OrCAD Allegro PCB Designer**: Utilizado para el *placement* de componentes, ruteo de pares diferenciales, definición de reglas de diseño (DRC) y manejo de planos de cobre.