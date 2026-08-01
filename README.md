# AI Hardware Lab

## Overview

AI-assisted hardware engineering laboratory for intelligent design, simulation, firmware development, PCB design, and embedded systems. The repository now includes an advanced EV charger controller design package intended for technical review, documentation, and future hardware implementation.

## Objectives

- AI-assisted circuit design
- MCU and FPGA development
- PCB design automation
- Firmware generation and validation
- Hardware documentation automation
- Engineering workflow automation using AI agents

## Main Project

### EV Charger Controller

The primary project in this repository is an AI Smart EV Charger Controller targeting a 50 kW to 150 kW DC fast charging platform.

Key deliverables:
- Advanced system requirements and project context
- Integrated hardware architecture and circuit strategy
- Preliminary BOM and component selection direction
- Prototype KiCad schematic and PCB workspace
- Documentation package for design review and publication

## Project Structure

### Hardware
Contains electronic design files:
- KiCad projects
- PCB layouts
- BOM files

### Firmware
Embedded software:
- STM32
- ESP32
- FPGA HDL projects

### Simulation
Simulation environments:
- SPICE
- FPGA simulation

### AI_Agents
Engineering AI agents:
- Design Agent
- Review Agent
- Test Agent

### Prompts
Prompt library for AI engineering workflows.

### Docs
Engineering documentation:
- Architecture
- Datasheets
- Standards
- Design notes

## Key Documents

- [Projects/EV_Charger_Controller/PROJECT_CONTEXT.md](Projects/EV_Charger_Controller/PROJECT_CONTEXT.md)
- [Projects/EV_Charger_Controller/01_Requirement/system_requirement.md](Projects/EV_Charger_Controller/01_Requirement/system_requirement.md)
- [Projects/EV_Charger_Controller/03_Hardware/Design_Notes/integrated_hardware_design.md](Projects/EV_Charger_Controller/03_Hardware/Design_Notes/integrated_hardware_design.md)
- [Projects/EV_Charger_Controller/03_Hardware/Design_Notes/detailed_circuit_design.md](Projects/EV_Charger_Controller/03_Hardware/Design_Notes/detailed_circuit_design.md)
- [Projects/EV_Charger_Controller/03_Hardware/BOM/master_bom.md](Projects/EV_Charger_Controller/03_Hardware/BOM/master_bom.md)
- [Projects/EV_Charger_Controller/06_Documentation/advanced_hardware_design_package.md](Projects/EV_Charger_Controller/06_Documentation/advanced_hardware_design_package.md)

## Prototype KiCad Project

- [EV_Charger_KiCad_Prototype](EV_Charger_KiCad_Prototype)

## Tools

Planned and used tools:

- KiCad
- STM32CubeIDE
- Vivado
- VS Code
- PlatformIO
- LTspice
- Python
- AI engineering agents

## Workflow

Requirement → Architecture → Simulation → Design → Firmware → Testing → Documentation