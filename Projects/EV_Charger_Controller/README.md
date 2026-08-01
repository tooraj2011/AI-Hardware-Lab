# EV Charger Controller Design Package

## Purpose

This directory consolidates the advanced hardware design package for the AI Smart EV Charger Controller project. It brings together requirements, architecture, circuit strategy, BOM direction, validation planning, and the KiCad prototype deliverables into a single engineering workspace.

## Main Deliverables

- System requirements and project context
- Integrated hardware architecture and circuit strategy
- Preliminary BOM and component direction
- Advanced design package for review and publication
- KiCad prototype project for schematic and PCB visualization

## Key Documents

- [PROJECT_CONTEXT.md](PROJECT_CONTEXT.md)
- [01_Requirement/system_requirement.md](01_Requirement/system_requirement.md)
- [03_Hardware/Design_Notes/integrated_hardware_design.md](03_Hardware/Design_Notes/integrated_hardware_design.md)
- [03_Hardware/Design_Notes/detailed_circuit_design.md](03_Hardware/Design_Notes/detailed_circuit_design.md)
- [03_Hardware/BOM/master_bom.md](03_Hardware/BOM/master_bom.md)
- [06_Documentation/advanced_hardware_design_package.md](06_Documentation/advanced_hardware_design_package.md)

## Prototype and Visualization

- KiCad prototype project: [EV_Charger_KiCad_Prototype](../../EV_Charger_KiCad_Prototype)

## Design Status

- Architecture: modular and safety-centered
- Control domain: STM32H7-based main controller
- Safety domain: independent supervisor path
- Communication: CAN, Ethernet, RS485, USB, vehicle interface support
- Validation: schematic review, layout guidance, EMC and thermal considerations
