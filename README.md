# GPS-Tracker-using-STM32

A custom PCB design for an STM32-based GPS tracking system using the SIM808 GPS/GPRS module.

This project is based on the concept of a GPS tracker using an STM32 microcontroller and SIM808 module. The main focus of this project is the **schematic design, component selection, PCB layout, routing, and design-rule verification using KiCad**.

> ⚠️ **Project Status:** PCB design completed in KiCad.  
> The PCB has **not been manufactured or physically tested yet**.


## 📌 Project Overview

The objective of this project is to design a compact custom PCB capable of integrating the main hardware required for a GPS tracking system.

The PCB is designed around:

- STM32 microcontroller
- SIM808 GPS/GPRS module
- DC-DC power regulation
- GPS and GSM/GPRS antenna interfaces
- SIM card interface
- UART communication
- Programming/debugging interface
- Status indicators
- Supporting capacitors, resistors, and protection components

The complete PCB was designed using **KiCad EDA**.

---

## 🧠 System Architecture

```text
                  ┌──────────────────────┐
                  │      POWER INPUT     │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │   POWER REGULATION   │
                  │      DC-DC / LDO     │
                  └──────────┬───────────┘
                             │
                             ▼
        ┌────────────────────┴────────────────────┐
        │                                         │
        ▼                                         ▼
┌─────────────────┐                     ┌─────────────────┐
│     STM32 MCU   │◄────── UART ───────►│     SIM808      │
│                 │                     │  GPS + GPRS     │
└────────┬────────┘                     └───────┬─────────┘
         │                                      │
         │                                      ├── GPS Antenna
         │                                      │
         │                                      ├── GSM Antenna
         │                                      │
         │                                      └── SIM Card
         │
         ├── Status LEDs
         │
         ├── Reset / User Button
         │
         └── SWD / Debug Interface





⚡ Power Supply Section

The PCB contains a dedicated power regulation section intended to provide the required voltage rails for the STM32 and SIM808 circuitry.

The design includes:

Input power protection
DC-DC voltage conversion
Decoupling capacitors
Filtering
Power distribution to the main circuit

The power section was designed with the high-current requirements of the SIM808 module in mind.

Note: The power circuit has not been physically validated because this PCB has not yet been manufactured.

📡 SIM808 GPS/GPRS Section

The SIM808 module provides:

GPS positioning
GPRS cellular connectivity
UART communication with the STM32
SIM card interface

🧠 STM32 Microcontroller Section

The STM32 acts as the main controller of the GPS tracker.

The PCB includes supporting circuitry such as:

MCU decoupling capacitors
Crystal oscillator
Reset circuit
User button
Status LEDs
SWD programming/debugging interface
UART connection to SIM808

The STM32 communicates with the SIM808 module through UART.

📶 Antenna Interfaces

The PCB provides dedicated interfaces for:

GPS antenna
GSM/GPRS antenna

These interfaces are routed separately to support the GPS and cellular communication sections.

Special attention was given to the routing of the antenna-related signals during PCB layout.

Note: RF performance has not been experimentally validated because the PCB has not been manufactured.

💾 SIM Card Interface

A SIM card interface is included for cellular network connectivity through the SIM808 module.

The PCB provides the required connections between the SIM card holder and the SIM808 module.

🛠️ PCB Design

The PCB was designed using KiCad.

PCB design process
Circuit Concept
      ↓
Schematic Design
      ↓
Component Selection
      ↓
Footprint Assignment
      ↓
PCB Placement
      ↓
PCB Routing
      ↓
Ground Plane
      ↓
Design Rule Check
      ↓
Gerber Generation

KiCad Design
Schematic

The schematic contains the complete electrical design of the GPS tracker, including:

Power supply
STM32
SIM808
SIM interface
Antenna interfaces
LEDs
Buttons
Crystal oscillator
Debug/programming interface
PCB Layout

The PCB layout includes:

Component placement
Signal routing
Power routing
Ground plane
Through-hole and SMD components
Connector interfaces
Antenna connections
📐 Design Considerations

During PCB design, attention was given to:

Component placement
Signal routing
Power distribution
Grounding
Decoupling
Clearance rules
Track widths
Via placement
Connector accessibility
Antenna routing

Design Rule Check (DRC) was used to identify PCB layout issues before manufacturing.

🚧 Current Limitations

This project currently represents the PCB design stage only.

The PCB has not yet been:

Manufactured
Assembled
Powered
Programmed
Tested with a SIM808 module
Tested with a GPS antenna
Tested on a cellular network

Therefore, the electrical and RF performance of the physical board has not yet been experimentally verified.

🔮 Future Work

Future improvements and validation can include:

Manufacturing the PCB
PCB assembly
STM32 firmware development
SIM808 AT-command integration
GPS position acquisition
GPRS communication
MQTT integration
GPS data logging
Vehicle testing
Power-consumption testing
RF performance testing
Hardware debugging and revision
