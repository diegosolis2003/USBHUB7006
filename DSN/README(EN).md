# Schematic Design - USB 3.2 Gen 1 Hub

## Folder Description

This folder contains the schematic capture file for the project, which defines all the electronic logic and connections for the 6-port USB Hub. 

The design of this schematic addressed the following critical blocks required for the operation of the **USB7006** controller:

* **Main IC Configuration:** Pin assignment and hardware configuration of the USB7006 to enable SuperSpeed (5Gbps) data rates.
* **Power Distribution Network (PDN):** Power stage design to support the simultaneous load of all 6 downstream ports, including the selection of voltage regulators and decoupling capacitors.
* **Protection and Filtering:** Implementation of Transient Voltage Suppressors (TVS) for ESD protection across all USB ports, along with noise filtering to maintain signal integrity.
* **Clock Circuit:** Configuration of the crystal oscillator required for the high-precision timing of the internal PHY.

## Included Files

* **`TAREA1.DSN`**: Master schematic file, hierarchically structured to facilitate the reading and navigation of the different circuit stages.

## Tools Used

* **OrCAD Capture CIS**: Used for component selection, logical interconnection, and *Netlist* generation for the PCB.