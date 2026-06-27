# 4-Bit Password Security System

A pure digital logic-based hardware security system designed using discrete integrated circuits (ICs). The system physically stores a 4-bit key and compares it against a user-entered password sequence to grant or deny access. This project was developed as part of the Digital Electronics Laboratory at NIT Agartala.

## 🚀 Features
* **Hardware Memory:** Utilizes a 7475 D-Latch to physically store a 4-bit master password sequence.
* **Bitwise Comparison:** Leverages 7486 XOR gates acting as hardware comparators to evaluate the input against the stored key.
* **Diode-OR Logic:** Employs 1N914 diodes to safely combine bit-mismatch signals at a single validation node without damaging the IC outputs.
* **Visual Status Indicators:** Features a dual-LED output layout—a Green LED for "Access Granted" and a Red LED for "Access Denied".
* **Master Lock Control:** Includes a physical keylock switch to control the Latch Enable pin, preventing unauthorized modification of the stored password.

## 🧠 System Architecture & Working Principle
1. **Password Setting:** When the Latch Enable pin is pulled HIGH via the keylock switch, the system captures a new password from the "Key Code Switch". Once pulled LOW, the latch freezes and preserves this code in hardware memory, even if the key code switch is subsequently altered.
2. **Access Evaluation:** When an individual enters a code on the "Data Entry Switch", it is immediately compared bit-by-bit against the latch's stored outputs via individual XOR gates. 
3. **Logic Verification:** * If any entered bit does not match the stored bit, that specific XOR gate outputs a HIGH signal. This flows through its isolation diode to pull the combined validation node HIGH, illuminating the **Red LED**.
   * If all 4 bits match perfectly, all XOR outputs remain LOW. The validation node drops LOW, satisfying the 7402 NOR gate logic network to illuminate the **Green LED**.

---

## 📐 Hardware Design & PCB Layout

The system was verified via software simulation and a physical breadboard layout before being transitioned into a custom printed circuit board (PCB) design. 

### 1. Circuit Schematic
The foundational logic schematic features pull-down resistor arrays to eliminate floating input states, signal-combining diodes, and dedicated logic IC configurations.
<img src="https://github.com/chandan1510/4-Bit-Password-Security-System/blob/main/4-Bit-Password-Security-System/Hardware/Schematic/SCH_Schematic2_1-P1_2026-01-31.PNG" width="75%" height ="50%" alt="Circuit Schematic">

### 2. 2D Board Layout
The 2D layout optimizes trace routing and path tracking to ensure clear isolation between power rails (VCC and GND) across the board footprint.
![2D PCB Layout](https://github.com/chandan1510/4-Bit-Password-Security-System/blob/main/4-Bit-Password-Security-System/Hardware/PCB_Layout/2D_PCB2_2026-01-31.png)

### 3. 3D Component Render
A 3D physical visualization showcasing component footprints, LED orientations, and structural connector placements for the final manufactured module.
![3D PCB Render](https://github.com/chandan1510/4-Bit-Password-Security-System/blob/main/4-Bit-Password-Security-System/Images/3D_PCB2_2026-01-31.png)

---

## 🛠️ Bill of Materials (BOM)
* **Logic ICs:** SN74HC75N (4-Bit Bistable Latch), 7486 (Quad 2-Input XOR), 7402 (Quad 2-Input NOR)
* **Passive Components:** 4x 1kΩ Resistors, 4x 10kΩ Resistors, 4x 1N914 Fast-Switching Diodes
* **Control & Indicators:** 2x 4-Position DIP Switches, 1x Keylock Switch, 1x Red LED, 1x Green LED
* **Power Source:** 4V–5V DC Battery Supply

## 📁 Repository Structure & Directory Map

To explore the design assets and engineering data associated with this system, navigate through the top-level **`4-Bit-Password-Security-System`** folder to find the following files:

* **`Documents/`**
  * `Project report_260110_095533.pdf`: Full laboratory academic engineering report documentation.
* **`Hardware/Schematic/`**
  * `SCH_Schematic2_1-P1_2026-01-31.PNG`: Full schematic design logic diagram.
* **`Hardware/PCB_Layout/`**
  * `2D_PCB2_2026-01-31.PNG`: Core trace layer and wiring layout preview.
  * `3D_PCB2_2026-01-31.jpg`: Textured 3D assembly module rendering.
* **`Hardware/Manufacturing/`**
  * `PickAndPlace_PCB2_2026-01-31.xlsx - PickAndPlace_PCB2_2026-01-31.csv`: SMT/Thru-hole target component coordinates for machine production assembly.
