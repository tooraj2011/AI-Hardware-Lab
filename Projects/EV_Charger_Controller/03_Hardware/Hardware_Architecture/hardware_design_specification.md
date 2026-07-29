# Hardware Design Specification

## 1. Project Overview

This document defines the hardware design specification for an intelligent EV charger controller targeting 50 kW to 150 kW DC fast charging applications. The design is aligned with the embedded architecture and supports real-time charging control, power management, safety monitoring, and communication with vehicles and external systems.

## 2. Design Objectives

- Deliver deterministic control for high-power DC charging
- Support industrial reliability and fault tolerance
- Provide modular hardware architecture for future enhancements
- Support CCS2 and GB/T vehicle communication
- Enable CAN, Ethernet, RS485, and USB connectivity
- Integrate protective functions for over-voltage, over-current, temperature, and isolation faults

## 3. System Architecture Summary

### 3.1 Functional Blocks
- Main control unit
- Power sensing and conditioning block
- Safety and protection block
- Communication interface block
- Power supply and distribution block
- Thermal management block

### 3.2 Primary Controller
- MCU: STM32H7 family
- Role: charging state control, communication management, protection logic, diagnostics, and secure firmware update handling

### 3.3 Safety Companion Controller
- MCU: STM32G0 or equivalent
- Role: independent watchdog handling, emergency shutdown supervision, fault latch control, and safety monitoring

## 4. Hardware Functional Requirements

### 4.1 Control Electronics
- High-performance MCU with sufficient timer channels for PWM and control loops
- Multiple ADC channels for voltage, current, and temperature sampling
- External flash and RAM for firmware and logging
- Secure boot and cryptographic support where feasible

### 4.2 Sensing and Measurement
- Isolated current sensing for DC output and AC input
- Voltage measurement interfaces for AC and DC rails
- Temperature sensing near power semiconductors and heat sinks
- Insulation monitoring interface
- High-resolution ADC front-end with filtering

### 4.3 Power Interface
- Gate driver interface for IGBT or MOSFET power modules
- Pre-charge and contactor drive circuits
- Protected power rails for logic and analog subsystems
- EMI suppression and transient protection

### 4.4 Communication Interfaces
- CAN transceiver for vehicle and power module communication
- Ethernet PHY and magnetics for network connectivity
- RS485 transceiver for industrial field interfaces
- USB interface for service and debugging

### 4.5 Safety and Protection
- Independent hardware watchdog
- Emergency stop input and safe-state output
- Fault latch and reset logic
- Hardware interlocks for high-voltage sections
- Isolation barrier for safety-critical interfaces

## 5. Hardware Architecture

### 5.1 Main Control Board
The main control board shall host:
- STM32H7 microcontroller
- Voltage and current sensing front-end
- CAN, Ethernet, RS485, and USB transceivers
- Memory devices
- Debug and programming interface
- Power management circuitry

### 5.2 Safety Board
The safety board shall host:
- Independent safety MCU
- Watchdog and fault monitoring circuits
- Emergency shutdown interface
- Safe-state relay control
- Interlock logic

### 5.3 Power Interface Board
The power interface board shall host:
- Gate driver circuits
- Pre-charge and contactor interface
- Current/voltage conditioning networks
- Protection components and transient suppressors

## 6. Electrical Design Considerations

### 6.1 Power Supply
- Separate analog and digital power rails
- Low-noise regulator for ADC and analog front-end
- Isolated supply for communication interfaces where required
- Bulk capacitance and transient suppression on input rails

### 6.2 Signal Integrity
- Controlled impedance routing for high-speed interfaces where required
- Proper grounding strategy for analog and digital domains
- EMC mitigation with filtering and shielding practices
- Separation of high-voltage and low-voltage sections

### 6.3 Thermal Design
- Thermal path from power devices to heatsinks
- Temperature monitoring near hot spots
- Adequate copper area for current carrying capability
- Thermal relief and airflow considerations for enclosure design

## 7. Mechanical and Packaging Considerations

- Modular PCB architecture with clearly separated control, power, and safety sections
- Mechanical support for connectors, heatsinks, and contactors
- Safe spacing for high-voltage insulation requirements
- Clear labeling for service and maintenance access

## 8. Reliability and Safety Requirements

- Fail-safe behavior on communication loss
- Independent detection of critical faults
- Watchdog recovery behavior
- Fault logging and diagnostic capability
- Robust over-temperature and short-circuit handling

## 9. Validation and Test Plan

### 9.1 Functional Tests
- MCU boot and firmware loading
- ADC measurement accuracy checks
- Communication interface verification
- Protection threshold testing

### 9.2 Environmental Tests
- Temperature cycling
- EMI/EMC validation
- Vibration and shock considerations for industrial use
- Humidity and ingress protection review

### 9.3 Safety Tests
- Emergency stop response validation
- Fault injection testing
- Isolation monitoring verification
- Safe shutdown behavior confirmation

## 10. Deliverables

- Schematic capture
- PCB layout files
- Bill of materials
- Gerber outputs
- Test procedure and validation report
- Safety and compliance checklist

## 11. Summary

The proposed hardware design specification defines a modular, safety-focused architecture for an EV charger controller. It is structured to support real-time charging control, robust protection, industrial communications, and future scalability.
