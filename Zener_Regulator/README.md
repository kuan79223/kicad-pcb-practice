[← Back to all projects](../README.md)

# Project 01 · Zener Diode Voltage Regulator

**Goal:** Practice the KiCad design flow for a simple Zener shunt-regulator PCB, using a 12 V DC input and a **nominal** 5.1 V output.

> **Learning exercise only.** The design has not been fabricated, assembled, or measured. The nominal 5.1 V is a component rating and design target, not a verified output voltage.

## 1. Circuit design

| Item | Design configuration |
| --- | --- |
| EDA software | KiCad 10.0.7 |
| Input | 12 V DC, connector J1 (2 pins) |
| Output | Nominal 5.1 V, connector J2 (2 pins) |
| R1 | 470 Ω, series current-limiting resistor |
| R2 | 1 kΩ, demonstration load |
| D1 | 1N4733A, nominal 5.1 V Zener diode |
| J1 / J2 | 2-position terminal-block footprints, 5.08 mm pitch |

![KiCad schematic with input, Zener regulator and output connectors](images/Schematic.png)

**Circuit principle:** R1 limits the input current. D1 is reverse-biased across the output, and R2 represents a load. The actual output depends on input voltage, load current, diode characteristics, and component tolerances.

## 2. PCB layout and 3D inspection

The exercise includes footprint assignment, component placement, copper routing, board outline, and silkscreen labels.

**PCB layout and silkscreen**

![PCB layout and silkscreen](images/PCB%20Layout%20%2B%20Silkscreen.png)

**3D preview**

![PCB 3D preview with connectors, diode and resistors](images/PCB%203D.png)

## 3. Design-rule check (DRC)

![KiCad DRC results](images/DRC%20Result.png)

| Check | Recorded result |
| --- | --- |
| DRC violations | 0 |
| Unconnected items | 0 |
| Schematic / PCB consistency violations | 0 |
| Documented exclusions | 2 (J1/J2 footprint-filter mismatch warnings) |
| Ignored test categories | 3 |

**Interpretation:** The enabled checks reported no violations in the captured result. The two connector footprint-filter exceptions and three ignored test categories still require review before fabrication. Passing DRC does **not** demonstrate electrical performance, safe operating margins, or manufacturing readiness.

## 4. Gerber and drill-file review

![GerbView with Gerber layers and Excellon drill files loaded](images/Gerber%20Viewer.png)

Gerber (`.gbr`) and Excellon drill (`.drl`) files were generated and inspected locally in KiCad GerbView. **Fabrication files are not included in this repository**, and no board has been ordered.

## 5. Editable KiCad source files

- [KiCad project settings (`.kicad_pro`)](W02_K01_Zener_Regulator.kicad_pro)
- [Schematic (`.kicad_sch`)](W02_K01_Zener_Regulator.kicad_sch)
- [PCB layout (`.kicad_pcb`)](W02_K01_Zener_Regulator.kicad_pcb)

Open the `.kicad_pro` file with KiCad Project Manager to inspect the project.

## 6. Limitations and next steps

- **No physical verification:** PCB fabrication, assembly, input/output voltage measurement, and load testing have not been performed.
- **Component selection:** Confirm manufacturer part numbers, terminal-block dimensions, drill sizes, diode orientation, and actual resistor power ratings against datasheets.
- **Electrical analysis:** Check worst-case resistor/Zener power dissipation, input-voltage range, load variation, and thermal margins.
- **Manufacturing review:** Confirm trace widths, clearances, board-edge spacing, solder-mask and silkscreen requirements with the intended fabrication service.
- **Design-rule review:** Revisit the two documented footprint-filter exclusions and three ignored test categories before any manufacturing release.

---

[← Back to project index](../README.md)
