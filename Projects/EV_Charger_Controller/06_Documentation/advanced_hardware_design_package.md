# Advanced Hardware Design Package

## 1. Purpose

This document consolidates the EV charger controller design into a publication-ready engineering package. It integrates the system requirements, hardware architecture, detailed circuit strategy, component selection direction, safety considerations, and prototype KiCad implementation into a single advanced design artifact.

## 2. Scope

The package covers the controller-side hardware concept for a 50 kW to 150 kW DC fast charger platform, with emphasis on:

- modular architecture
- independent safety supervision
- high-reliability control electronics
- communication interfaces
- sensing and protection strategy
- prototype KiCad delivery

## 3. Architecture Summary

The system is structured around five major domains:

1. Control domain
   - STM32H743-based main controller
   - firmware storage, boot, and reset management

2. Safety domain
   - STM32G071-based independent supervisor
   - watchdog, safe-state disable path, and fault containment

3. Power domain
   - fuse, surge protection, EMI filtering, regulators, isolators

4. Measurement domain
   - voltage sensing, current sensing, temperature monitoring, isolation monitoring

5. Communication domain
   - CAN, Ethernet, RS485, USB, and vehicle interface support

## 4. Design Decisions

### 4.1 Safety-first architecture
The design uses a dedicated and independent safety supervisor to enforce fail-safe operation and prevent uncontrolled power behavior during faults.

### 4.2 Modular hardware partitioning
The architecture splits control, safety, power, sensing, and communications into logical blocks to support review, testing, and future iteration.

### 4.3 Industrial-grade implementation approach
The concept is based on industrially available and automotive-grade component families where practical, with emphasis on reliability and manufacturability.

### 4.4 EMC-conscious layout strategy
The design incorporates connector protection, filtering, separation of noisy and sensitive domains, and controlled power return paths to reduce EMI and improve signal integrity.

## 5. Circuit Implementation Direction

The circuit design is built around the following implementation principles:

- main MCU with decoupling, reset, boot, and memory support
- independent watchdog and fault-latch circuitry
- isolated or filtered communication interfaces
- analog front-end for voltage, current, and temperature measurement
- power entry protections including fuse, TVS, and EMI filtering
- relay and contactor control interfaces with protection and status feedback

## 6. Preliminary BOM Direction

The preliminary BOM includes:

- main controller: STM32H743
- safety supervisor: STM32G071
- reset supervisor: STM6700-class device
- communication devices: SN65HVD230, LAN8742A, SN65HVD78
- isolation: ISO7762-class isolators
- measurement: INA240/INA226, ADS131M04
- protection: TVS, fuses, ferrites, RC filters

## 7. Prototype KiCad Delivery

A prototype KiCad project has been created to provide a visual schematic and PCB foundation for the design.

### Files

- [../../EV_Charger_KiCad_Prototype/EV_Charger_KiCad_Prototype.kicad_pro](../../EV_Charger_KiCad_Prototype/EV_Charger_KiCad_Prototype.kicad_pro)
- [../../EV_Charger_KiCad_Prototype/EV_Charger_KiCad_Prototype.kicad_sch](../../EV_Charger_KiCad_Prototype/EV_Charger_KiCad_Prototype.kicad_sch)
- [../../EV_Charger_KiCad_Prototype/EV_Charger_KiCad_Prototype.kicad_pcb](../../EV_Charger_KiCad_Prototype/EV_Charger_KiCad_Prototype.kicad_pcb)

## 8. Validation Plan

The following validation steps are recommended:

1. Schematic review against requirements
2. Electrical rule and design rule checks
3. Bench validation of rails, reset, communication buses, and fault logic
4. EMC and transient immunity verification
5. Thermal validation under operating conditions
6. Prototype assembly and reliability review

## 9. Risks and Mitigations

- EMC noise affecting analog measurements
- safety logic not being independently verified
- thermal performance and component derating
- supply stability and brownout risk

Mitigation relies on filtering, isolation, dedicated supervision, conservative component selection, and structured validation.

## 10. Summary

This package provides a more advanced, engineering-oriented hardware design foundation for the EV charger controller and is structured for review, documentation, and future PCB implementation.
