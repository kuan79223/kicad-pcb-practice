# KiCad PCB Design Practice

Hands-on learning exercises in **schematic design, footprint selection, PCB layout, ERC/DRC, 3D review, and fabrication-file generation** using KiCad.

This repository contains **practice designs, not production-qualified or physically tested hardware**.

## Projects

| Project | Focus | Status | Details |
| --- | --- | --- | --- |
| **01 · Zener Voltage Regulator** | 12 V input, nominal 5.1 V Zener shunt regulator; schematic, PCB layout, Gerber/Drill | PCB design exercise completed; fabrication and physical verification pending | [View project](Zener_Regulator/README.md) |

### Project 01 preview

[![Zener regulator PCB layout](Zener_Regulator/images/02_PCB_Layout.png)](Zener_Regulator/README.md)

For circuit diagrams, component selection, design-rule checks, 3D previews, fabrication files, and open verification items, open the project page above.

## Repository organization

```text
kicad-pcb-practice/
├── README.md                   # Short project index
├── .gitignore
└── Zener_Regulator/
    ├── README.md               # Detailed design notes and screenshots
    ├── W02_K01_Zener_Regulator.kicad_pro
    ├── W02_K01_Zener_Regulator.kicad_sch
    ├── W02_K01_Zener_Regulator.kicad_pcb
    ├── images/
    └── fab/                    # Gerber / Excellon drill files
```

## Workflow

`Schematic → ERC → Footprint → PCB Layout → DRC → 3D Review → Gerber/Drill`

**Note:** A passing software check is not a substitute for component datasheet review, power/thermal analysis, manufacturing checks, or measurements on assembled hardware.
