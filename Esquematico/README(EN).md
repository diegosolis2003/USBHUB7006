# Schematic Design (PDF) - USB 3.2 Gen 1 Hub

## Folder Description

This folder contains the complete schematic diagram exported in PDF format for the 6-port USB Hub project, which is based on the **USB7006** controller. 

The purpose of providing this file is to facilitate efficient design reviews, auditing, and quick reference of the electronic design without requiring specialized CAD software (such as OrCAD Capture) to be installed.

## Included Files

* **`Esquematico.pdf`**: The primary document containing all schematic sheets for the project. The export preserves full vector clarity and legibility for components, net names, and technical annotations.

## Sections Available for Review

When exploring this document, the following critical engineering blocks can be visually audited:

* **USB7006 Configuration:** Pin mapping, hardware configuration straps, and logical routing for the SuperSpeed differential pairs.
* **Power Distribution Network (PDN):** Power stage design, including voltage regulators, power delivery/current management for the 6 downstream ports, and the decoupling capacitor matrix.
* **Protection and Filtering:** Placement of Transient Voltage Suppressor (TVS) diodes for Electrostatic Discharge (ESD) protection across all USB interfaces.
* **Clocking and Control:** Precision crystal oscillator circuitry required by the controller's internal PHY.

## File Use Cases

* **Design Reviews:** Easily share the circuit logic with peer engineers, manufacturing partners, or technical reviewers.
* **Rapid Auditing:** Ideal for quickly locating specific Reference Designators (*RefDes*) or tracing a signal path using the native search functionality of any PDF reader.
* **Assembly and Testing Reference:** Serves as a quick laboratory reference guide during hardware debugging, component assembly, or when probing voltages on the physical PCB.