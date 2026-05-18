# Electronic Design Project - 6-Port USB 3.2 Gen 1 (5Gbps) Hub

<p align="center">
  <img src="PNG/Escudo-UNIS.png" alt="University Crest" width="200">
</p>
<p align="center">
  <em>Universidad del Istmo de Guatemala</em><br>
  <em>Faculty of Engineering</em><br>
  <em>Electronic Design Project</em>
</p>
<p align="center">
  <em>Diego Fernando Solís López</em><br>
  <em>May 2026</em>
</p>

---

## Overview
This repository documents the design, development, and completion of a fully functional USB hub with **USB 3.2 Gen 1 (5Gbps)** capabilities. The core of the system is the **USB7006** controller, selected for its robustness and ability to simultaneously manage multiple high-speed connections.

The main objective was to develop a device that not only met the technical requirements for speed and connectivity by providing **6 downstream ports**, but also adhered to a compact Form Factor. The final board design (`.brd`) mimics the dimensions, layout, and quality of a market-ready commercial product. This repository includes the final schematic (`.dsn`) and PCB design files.

## Table of Contents
1. [Overview](#overview)
2. [Main USB Controller](#main-usb-controller)
3. [Project Objectives](#project-objectives)
4. [General Architecture](#general-architecture)
5. [Main Design Blocks](#main-design-blocks)
6. [Design Philosophy](#design-philosophy)
7. [Tools Used](#tools-used)
8. [Current Status](#current-status)
9. [Notes](#notes)

## Main USB Controller
The design is built around the **USB7006** controller, a hub IC geared towards SuperSpeed applications. This component was crucial in achieving the project goals, handling high-speed data traffic management and distribution across multiple ports.

**Considered Features:**
* Native support for USB 3.2 Gen 1 (5Gbps).
* Advanced power management for multiple downstream ports.
* High integration of internal passive components to reduce PCB footprint.
* Optimized PHY interface for signal integrity.

## Project Objectives
* Design and route a fully functional USB 3.2 Gen 1 hub.
* Implement a minimum of 6 downstream ports operating at the maximum speed allowed by the standard.
* Achieve a compact form factor, mimicking the physical design and component density of a real commercial device.
* Apply advanced signal integrity and high-speed PCB design techniques.
* Deliver fully validated manufacturing and design files (`.dsn` and `.brd`).

## General Architecture

```text
               Host PC (USB 3.2 Gen 1)
                       |
                  Upstream Port
                       |
            +----------------------+
            |      Controller      |
            |       USB7006        |
            +----------------------+
             /   /   |   |   \   \
           P1  P2   P3  P4   P5  P6
           (6x Downstream Ports)
           
```
*The USB7006 controller centralizes SuperSpeed communication from the Upstream port and efficiently distributes it to the 6 Downstream ports simultaneously.*

## Main Design Blocks

* **Upstream Interface:** Main USB connection to the Host. It features Electrostatic Discharge (ESD) protection and noise filtering.
* **USB7006 Core:** The central processor that negotiates speeds and manages data packet traffic.
* **Downstream Interfaces (x6):** Output ports meticulously routed to maintain the differential impedance required for 5Gbps transfer rates.
* **Power Architecture:** Power Distribution Network (PDN) designed to support the simultaneous power consumption of all 6 ports, incorporating efficient voltage regulators and strategically placed decoupling capacitors.
* **Clocking Circuit:** Precision crystal oscillator required by the USB7006 PHY for data timing.

## Design Philosophy

Unlike purely academic projects, this development was driven from day one by a commercial and final-product approach.

* **Density:** Minimizing PCB space (`.brd`) to achieve a small chassis footprint.
* **Signal Integrity (SI):** Differential pair routing was the highest priority to prevent reflections, attenuation, and *crosstalk* at 5Gbps frequencies.
* **Reliability:** Inclusion of ESD protections and proper thermal management.

## Tools Used

* OrCAD Capture CIS (Schematics - `.dsn`)
* OrCAD Allegro (PCB Design - `.brd`)
* USB7006 Family Datasheets and Application Notes

## Current Status

The project is **100% completed and functional**.

The final schematic capture and board design files are delivered. This project represented a highly valuable learning curve, highlighting the following technical achievements:

* **High-Speed Routing Mastery:** Achieved a deep understanding of impedance calculations and SuperSpeed signal routing.
* **Differential Pair Management:** Practical learning in length matching, phase control, and strict spacing for the TX and RX lines of the USB 3.2 standard.
* **Design for Manufacturing (DFM):** Successful transition from a theoretical concept to a mass-production-ready board.

## Notes

This repository contains the final version of the project. The `.dsn` and `.brd` files can be opened and inspected using the Cadence design tool suite. It is highly recommended to carefully review the internal layer routing to analyze the implemented High-Speed techniques.