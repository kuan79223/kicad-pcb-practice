[← Back to project index](../README.md)

# Project 01 — Zener Diode Voltage Regulator

**Objective:** Design a simple Zener shunt-regulator PCB with a 12 V DC input and a nominal 5.1 V output. The project covers schematic capture, footprint assignment, PCB layout, electrical/design rule checks, 3D inspection, and fabrication-file export.

### Design overview

| Item | Configuration |
| --- | --- |
| EDA tool | KiCad 10.0.7 |
| Input | 12 V DC (J1, 2-pin terminal block) |
| Output | Nominal 5.1 V (J2, 2-pin terminal block) |
| R1 | 470 Ω, series current-limiting resistor |
| R2 | 1 kΩ, demonstration load |
| D1 | 1N4733A, 5.1 V nominal Zener diode |
| J1 / J2 | 2-position, 5.08 mm pitch terminal-block footprints |
| PCB | Routed PCB design with front copper and Gerber/Excellon exports |

**Circuit principle:** R1 limits current from the 12 V input; D1 is connected in reverse bias across the output and R2 represents a load. Regulation depends on the supply voltage, load current and the actual Zener characteristics; 5.1 V is a nominal target, **not a guaranteed measured output**.

### 1. Schematic
![Schematic](images/Schematic.png)

### 2. PCB Layout
![PCB Layout](images/PCB%20Layout%20%2B%20Silkscreen.png)

### 3. PCB 3D
![PCB 3D](images/PCB%203D.png)

### 4. DRC Result
![DRC Result](images/DRC%20Result.png)

### 5. Gerber Viewer
![Gerber Viewer](images/Gerber%20Viewer.png)

The captured KiCad check showed:

| Check | Result |
| --- | --- |
| DRC violations | 0 |
| Unconnected items | 0 |
| Schematic / PCB parity violations | 0 |
| Documented exclusions | 2 (J1/J2 footprint-filter mismatches) |
| Ignored test categories | 3 (see check settings) |

**Interpretation:** No violations were reported by the enabled checks at the time of the screenshot. This does not certify physical dimensions, electrical safety, or manufacturability. Two footprint-filter exceptions were documented; the exact ordered parts must still be checked against their datasheets.

## 5. Gerber and drill-file review

![GerbView with Gerber and drill layers loaded](images/Gerber%20Viewer.png)

Gerber (`.gbr`) and Excellon drill (`.drl`) files were generated and reviewed locally using KiCad GerbView.

Fabrication files are not included in this repository. They are practice outputs, not released manufacturing files.


