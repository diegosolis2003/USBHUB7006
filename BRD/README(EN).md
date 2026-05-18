# PCB Layout Design - USB 3.2 Gen 1 Hub

## Folder Description

This folder contains the physical design file (PCB Layout) for the USB Hub. The main objective of this stage was to translate the schematic into a functional board, prioritizing a compact form factor similar to a commercial product without sacrificing signal integrity.

The design work on this board (Layout) focused on the following engineering challenges:

* **High-Speed Routing:** Meticulous tracing of 5Gbps SuperSpeed signals. This required strict differential impedance control on the TX and RX traces of the USB 3.2 ports.
* **Differential Pair Management:** Application of length matching and phase control techniques to prevent attenuation, reflections, and crosstalk between the data lines of the 6 ports.
* **Placement Strategy:** Positioning of high-density components to minimize the overall board area, placing decoupling capacitors and ESD protections as close as possible to the connectors and the **USB7006** IC.
* **Thermal and Power Management:** Design of internal copper planes for efficient power distribution (VDD/GND) and thermal dissipation of the main controller.

## Included Files

* **`tarea1.brd`**: Final printed circuit board file, ready for manufacturing file generation.

## Tools Used

* **OrCAD Allegro PCB Designer**: Used for component placement, differential pair routing, Design Rule Checking (DRC) definition, and copper plane management.