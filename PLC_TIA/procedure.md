# ⚙️ PROCEDURE: Three-Way Traffic Light Using HMI and Siemens PLC

This document outlines the complete step-by-step procedure for implementing a three-way traffic light control system using a **Siemens S7-1200 PLC** and a **Software HMI (WinCC Runtime Advanced)** via **TIA Portal**.

---

## 🟢 1. Define the Traffic Logic and Timing

### 🔸 Traffic Light Phases
- **Green:** 15 seconds
- **Yellow:** 5 seconds
- **Red:** Active while other directions have green/yellow

### 🔸 Sequence
- East → Green → Yellow → Red  
- North → Green → Yellow → Red  
- West → Green → Yellow → Red  

The cycle repeats for continuous operation.

### 🔸 Control Logic
Use **TP Timers** and **counters** in the PLC to control the duration of each light phase and ensure proper sequencing.

---

## 🧩 2. Hardware Configuration (Siemens PLC S7-1200)

### 🔧 PLC Setup
- **Controller:** Siemens S7-1200
- **Inputs:** Optional manual override buttons or vehicle presence sensors
- **Outputs:** Red, Yellow, and Green indicators (e.g., M1.0, M1.1, M1.2)

### 🔋 Power Supply
- Use a **24V DC** regulated power supply

### 🪛 Wiring
- Assign **PLC memory bits** (e.g., M0.0, M0.1) to control the outputs for each traffic light direction

---

## 💻 3. PLC Program Development

### 🧰 TIA Portal Project
- Create a new project and add the Siemens S7-1200 PLC
- Configure I/O modules (digital inputs/outputs or memory bits)

### 🔗 Ladder Logic Programming
- Implement green → yellow → red cycle using **TP timers**
- Prevent conflicting directions from being green simultaneously
- Use memory bits to represent light states

---

## 🖥️ 4. HMI Design (Software-Based)

### 🎛️ Add HMI
- Use **WinCC Runtime Advanced** inside TIA Portal
- Set up communication between PLC and HMI via Ethernet or Profinet

### 📊 HMI Screen Design
- Create one or more screens showing:
  - Red, Yellow, Green indicators for each direction
  - **Start / Stop / Reset** buttons
  - Text indicators (e.g., "North: Green")

### 🔗 Link HMI Tags
- Map each HMI element to a corresponding PLC bit:
  - `Green North` → M0.0
  - `Yellow North` → M0.1
  - ... and so on for each direction

---

## 🔄 5. PLC-HMI Communication

### 📡 Tag Mapping
- In the HMI settings, **link tags** to PLC memory addresses

### 🧭 Manual Controls
- Add **Start / Stop / Override** buttons on the HMI screen
- Use **write tags** to send control commands to the PLC

---

## 🧪 6. Simulation and Testing

### 🧷 Simulate PLC Logic
- Use **PLCSIM** to run the ladder program
- Observe phase transitions (green → yellow → red) in correct order

### 🧩 Simulate HMI
- Run **HMI Simulation** in WinCC
- Verify light status displays and button operations

---

## 📥 7. Download Program to PLC and HMI

### 🔌 Connect PLC
- Use Ethernet or USB to connect your PC to the Siemens PLC
- Download the ladder logic to the PLC

### 📲 Download to HMI
- Upload the HMI configuration from WinCC to the software HMI

### ▶️ Run the System
- Start both PLC and HMI systems
- Verify live synchronization and traffic signal control
- Test manual button overrides for functionality

---

## 🛠️ 8. Final Testing and Debugging

### ✅ Real Conditions Test
- Observe that each traffic light behaves as expected
- Ensure there’s **no green overlap** between conflicting directions

### 🧠 HMI Interaction
- Test all HMI elements (status indicators, manual controls)
- Fix any bugs in sequencing, timing, or display

### 📝 Documentation
- Capture screenshots of:
  - Ladder logic program
  - HMI screen layout
- Document I/O mapping and tag assignments
