#  DIY PET Filament Extruder (Glue Gun Mod)

A robust, low-cost machine designed to recycle plastic bottles into usable 3D printing filament. This project focuses on accessibility by repurposing common household items and 3D printed mechanics.

###  Precision Calibration (The Nozzle Mod)
The secret to achieving the industry-standard **1.75mm filament diameter** lies in the nozzle modification.
* I took the standard glue gun nozzle and performed a precision drilling operation using a **1.75mm HSS (High-Speed Steel) drill bit**.
* This effectively turns the nozzle into a calibration die, ensuring the plastic exits at the exact dimensional tolerance required for 3D printing.

##  Mechanical & Hardware Specs

### 1. Drive System (High Torque)
To ensure consistent pulling force without stalling, I designed a custom reduction gearbox.
* **Motor:** Nema 17 Stepper.
* **Transmission:** A small drive gear on the motor transfers power to a large, custom-modeled gear integrated directly into the spool's flange.
* **Result:** Significant torque increase, allowing the machine to pull the PET strip through the heated nozzle smoothly.

### 2. The Filamentizer (Bottle Cutter)
The strip cutter is a separate module mounted on the same wooden baseboard.
* **Design:** Based on the standard community-proven design involving a **threaded rod**, **two bearings**, and a **pencil sharpener blade**.
* **Accessibility:** This design was chosen because the parts are widely available and easy to adjust for different strip widths.

### 3. Electronics & Logic
* **Controller:** Arduino Uno (Legacy version).
* **Driver:** A4988 Stepper Driver.
* **Input:** Potentiometer for real-time speed adjustment (PWM-like control).
* **Power Supply:** 12V 2A (for the motor and logic).

##  Construction
The entire assembly is mounted on a dual-board wooden chassis:
1.  **Main Base:** Houses the electronics, the cutter, and the heating assembly.
2.  **Spool Tower:** A narrower vertical board that supports the axle for the large spool and gear system.

---

##  Roadmap & Future Upgrades: The IoT Step

Currently, the machine operates on an open-loop system (manual speed control, fixed temperature). The next phase involves modernizing the control logic.

### planned Upgrade: ESP32 + Touch Screen
I am developing an upgrade to replace the Arduino with an **ESP32**, adding a Touch Screen interface. This will enable:
* Precise RPM monitoring.
* Digital Start/Stop control.
* Future temperature monitoring (adding a thermistor).

**Reference Architecture:**
This upgrade will utilize the same UI/UX logic I am developing for my logistics dashboard. You can check the code structure and interface concepts here:
👉 **[SalesPulse-IoT](https://github.com/SEU-USUARIO/SalesPulse-IoT)** *(An ESP32-based dashboard for E-commerce monitoring)*.
