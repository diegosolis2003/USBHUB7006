# Proyecto de Diseño Electrónico - USB Hub 3.2 Gen 1 (5Gbps) de 6 Puertos

<p align="center">
  <img src="PNG/Escudo-UNIS.png" alt="Escudo de la Universidad" width="200">
</p>
<p align="center">
  <em>Universidad del Istmo de Guatemala</em><br>
  <em>Facultad de Ingeniería</em><br>
  <em>Proyecto de Diseño Electrónico</em>
</p>
<p align="center">
  <em>Diego Fernando Solís López</em><br>
  <em>mayo de 2026</em>
</p>

---

## Descripción general
Este repositorio documenta el diseño, desarrollo y culminación de un hub USB completamente funcional con capacidades **USB 3.2 Gen 1 (5Gbps)**. El núcleo del sistema es el controlador **USB7006**, seleccionado por su robustez y capacidad para gestionar múltiples conexiones de alta velocidad de manera simultánea.

El objetivo principal fue desarrollar un dispositivo que no solo cumpliera con los requisitos técnicos de velocidad y conectividad, proporcionando **6 puertos de salida (downstream)**, sino que además se ajustara a un factor de forma (Form Factor) compacto. El diseño de la placa final (`.brd`) asimila las dimensiones, distribución y calidad de un producto comercial listo para el mercado. En este repositorio se incluyen los archivos finales del esquemático (`.dsn`) y del diseño de la PCB.

## Tabla de Contenido
1. [Descripción general](#descripción-general)
2. [Chip USB principal](#chip-usb-principal)
3. [Objetivos del proyecto](#objetivos-del-proyecto)
4. [Arquitectura general](#arquitectura-general)
5. [Bloques principales del diseño](#bloques-principales-del-diseño)
6. [Filosofía de diseño](#filosofía-de-diseño)
7. [Herramientas utilizadas](#herramientas-utilizadas)
8. [Estado actual](#estado-actual)
9. [Notas](#notas)

## Chip USB principal
El diseño está cimentado sobre el controlador **USB7006**, un IC hub orientado a aplicaciones SuperSpeed. Este componente fue crucial para lograr las metas del proyecto, encargándose de la gestión de tráfico de datos de alta velocidad y la distribución hacia los múltiples puertos.

**Características consideradas:**
* Soporte nativo para USB 3.2 Gen 1 (5Gbps).
* Gestión de energía avanzada para múltiples puertos downstream.
* Alta integración de componentes pasivos internos para reducir el área de la PCB.
* Interfaz PHY optimizada para integridad de señal.

## Objetivos del proyecto
* Diseñar y enrutar un hub USB 3.2 Gen 1 completamente funcional.
* Implementar un mínimo de 6 puertos downstream que operen a la máxima velocidad permitida por el estándar.
* Lograr un factor de forma compacto, asimilando el diseño físico y la densidad de componentes de un dispositivo comercial real.
* Aplicar técnicas avanzadas de integridad de señal y diseño de alta velocidad en la PCB.
* Entregar los archivos de manufactura y diseño (`.dsn` y `.brd`) listos y validados.

## Arquitectura general

```text
               Host PC (USB 3.2 Gen 1)
                       |
                  Upstream Port
                       |
            +----------------------+
            |    Controlador       |
            |      USB7006         |
            +----------------------+
             /   /   |   |   \   \
           P1  P2   P3  P4   P5  P6
           (6x Puertos Downstream)
```
*El controlador USB7006 centraliza la comunicación SuperSpeed desde el puerto Upstream y la distribuye eficientemente hacia los 6 puertos Downstream de manera simultánea.*

## Bloques principales del diseño

* **Interfaz Upstream:** Conexión principal tipo USB hacia el Host. Cuenta con protección contra descargas electrostáticas (ESD) y filtrado de ruido.
* **Núcleo USB7006:** El procesador central que negocia las velocidades y administra el tráfico de paquetes de datos.
* **Interfaces Downstream (x6):** Puertos de salida enrutados meticulosamente para mantener la impedancia diferencial necesaria para la transferencia a 5Gbps.
* **Arquitectura de potencia:** Red de distribución de energía (PDN) diseñada para soportar el consumo simultáneo de los 6 puertos, incorporando reguladores de voltaje eficientes y capacitores de desacoplo estratégicamente posicionados.
* **Circuito de reloj (Clocking):** Oscilador de cristal de precisión requerido por el PHY del USB7006 para la temporización de los datos.

## Filosofía de diseño

A diferencia de proyectos puramente académicos, este desarrollo se enfocó desde el día uno en un enfoque comercial y de producto final.

* **Densidad:** Minimizar el espacio en la PCB (`.brd`) para lograr un chasis pequeño.
* **Integridad de Señal (SI):** El ruteo de pares diferenciales fue la máxima prioridad para evitar reflexiones, atenuación y *crosstalk* a frecuencias de 5Gbps.
* **Confiabilidad:** Inclusión de protecciones ESD y manejo térmico adecuado.

## Herramientas utilizadas

* Capture CIS de OrCAD (Esquemáticos - `.dsn`)
* OrCAD Allegro (Diseño de PCB - `.brd`)
* Datasheets y Application Notes de la familia USB7006

## Estado actual

El proyecto se encuentra **100% completado y funcional**.

Se entregan los archivos finales de captura esquemática y el diseño de la placa. Este proyecto representó una curva de aprendizaje sumamente valiosa, destacando los siguientes logros técnicos:

* **Dominio del ruteo de Alta Velocidad (High-Speed):** Se logró un entendimiento profundo sobre el cálculo de impedancias y el trazado de señales SuperSpeed.
* **Manejo de Pares Diferenciales:** Aprendizaje práctico en la igualación de longitudes (length matching), control de fase y separación (spacing) estricta para las líneas TX y RX del estándar USB 3.2.
* **Diseño para Manufactura:** Transición exitosa de un concepto teórico a una placa lista para producción masiva.

## Notas

Este repositorio contiene la versión final del proyecto. Los archivos `.dsn` y `.brd` pueden ser abiertos e inspeccionados con la suite de herramientas de diseño de Cadence. Se recomienda revisar detenidamente el ruteo de las capas internas para analizar las técnicas de High-Speed implementadas.
