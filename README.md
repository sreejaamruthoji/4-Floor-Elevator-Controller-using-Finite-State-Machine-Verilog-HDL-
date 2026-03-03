# 4-Floor Elevator Controller using FSM (Verilog HDL)

## 📌 Overview
This project implements a 4-floor Elevator Controller using a Finite State Machine (FSM) in Verilog HDL.  
The design handles floor requests, movement control (up/down), idle state, and emergency stop functionality.

The controller prioritizes lower floor numbers when multiple floor requests are active.

---

## 🎯 Features
- 4-floor support (0 to 3)
- FSM-based design
- Priority-based floor selection
- Move Up / Move Down control
- Emergency Stop handling
- Synchronous floor tracking
- Complete Testbench included

---

## 🏗️ FSM States

| State       | Description |
|-------------|------------|
| IDLE        | Elevator stopped and waiting |
| MOVE_UP     | Elevator moving upward |
| MOVE_DOWN   | Elevator moving downward |
| EMERGENCY   | Emergency stop activated |

---

## ⚙️ Inputs & Outputs

### Inputs
- `clk` – System clock  
- `reset` – Asynchronous reset  
- `floor_req[3:0]` – Floor request buttons  
- `emergency_stop` – Emergency signal  

### Outputs
- `move_up` – Motor up control  
- `move_down` – Motor down control  
- `motor_stop` – Stop signal  
- `current_floor[1:0]` – Current elevator position  

---

## 🧠 Working Principle

1. Elevator starts at Floor 0 after reset.
2. Checks floor request inputs.
3. Moves UP if target floor > current floor.
4. Moves DOWN if target floor < current floor.
5. Stops when destination is reached.
6. If emergency is triggered:
   - Immediately enters EMERGENCY state
   - Motor stops
   - Returns to IDLE after emergency is cleared.

---

## 🧪 Simulation

Simulation verifies:

- Upward movement
- Downward movement
- Multiple request priority handling
- Emergency stop behavior

---

## Tools Used

- Xilinx Vivado
---

