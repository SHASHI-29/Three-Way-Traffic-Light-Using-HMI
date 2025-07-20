# 🚦 Three-Way Traffic Light Using HMI (PLC + HMI Project)

This project implements an automated **three-way traffic signal system** using a **Siemens PLC (S7-1200)** and a **Human-Machine Interface (HMI)** developed in **TIA Portal**. It demonstrates real-time traffic light control logic through ladder programming and visual feedback on an HMI screen.

---

## 🧠 Project Objective

Design and implement a **traffic light controller** for a 3-way intersection that:
- Uses PLC timers and ladder logic to automate signal transitions
- Provides real-time visual feedback via an HMI
- Includes manual override and emergency controls

---

## ⚙️ Technologies & Tools

- **PLC Platform:** Siemens S7-1200
- **Programming Software:** TIA Portal (Ladder Logic + HMI Designer)
- **HMI Interface:** WinCC Runtime Advanced
- **Simulation Tools:** PLCSIM and HMI Sim
- **Control Logic:** Timers, counters, memory bits, and I/O mapping

---

## 🔧 Components Used

| Component                     | Description                                    |
|------------------------------|------------------------------------------------|
| Siemens PLC (S7-1200)        | Core controller for executing ladder logic     |
| Signal Lamps / LEDs          | Indicate red, yellow, green signals            |
| Push Buttons (optional)      | Manual override, start/stop                    |
| Power Supply (24V DC)        | For powering PLC and I/O devices               |
| TIA Portal Software          | For PLC programming and HMI design             |
| HMI Panel or Software        | To visualize traffic light operation           |

---

## 🛠️ Working Principle

- Each direction (North, East, West) cycles through **green → yellow → red**.
- **Timers** (TP blocks) manage phase durations (e.g., green = 15s, yellow = 5s).
- Signals are interlocked to **prevent conflicting greens**.
- The HMI displays current signal states and allows manual control.
- The system loops continuously and can be overridden if needed.

---

## 📋 Implementation Steps

1. **PLC Setup:**
   - Configure S7-1200 hardware in TIA Portal.
   - Define inputs/outputs (e.g., M0.0 for North Green).

2. **Ladder Logic Programming:**
   - Write control logic using timers and memory bits.
   - Sequence the traffic lights safely and cyclically.

3. **HMI Design:**
   - Create a screen showing signal states using colored indicators.
   - Add buttons for manual override and reset.
   - Link PLC memory bits to HMI tags.

4. **Simulation:**
   - Test the PLC logic with PLCSIM.
   - Test HMI interaction with WinCC Runtime.
   - Validate traffic signal transitions and override features.

---

## 📷 Sample Output Screens (HMI)

- **East Green Signal Display**
- **West Green / Yellow Signal**
- **North Green Signal**
> *(screenshots of HMI screens are in `/images` folder)*

---

## ✅ Results

- Successfully executed a time-based traffic control sequence.
- HMI displayed accurate signal states and allowed manual control.
- Demonstrated a scalable and practical model of traffic automation.

---

## 🔮 Future Enhancements

- Add **real-time traffic sensors** for dynamic green/yellow timing.
- Integrate **countdown timers** on HMI.
- Expand to **4-way or pedestrian-based traffic control**.
- Implement **wireless monitoring** or **data logging** via IoT modules.
- Use **machine learning** for traffic prediction and optimization.

