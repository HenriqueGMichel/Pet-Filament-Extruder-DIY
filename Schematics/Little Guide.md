#  Electronics Wiring Guide

This document details the connection logic between the Arduino, the Stepper Driver, and the peripherals.

##  Component Pinout Map

### 1. Power Supply (12V 2A)
The heart of the system.
* **V+ (12V):** Connected to the **VMOT** pin on the A4988 Driver and Arduino Vin.
* **GND:** Shared ground (Common Ground) for Arduino and Driver.

### 2. A4988 Stepper Driver
Controls the Nema 17 motor.
* **VMOT:** 12V from Power Supply.
* **VDD:** 5V from Arduino.
* **GND:** Connected to Common Ground.
* **1A / 1B:** Connected to Nema 17 Coil A.
* **2A / 2B:** Connected to Nema 17 Coil B.
* **STEP:** Connected to Arduino Digital Pin (e.g., D3).
* **DIR:** Connected to Arduino Digital Pin (e.g., D4).
* **SLEEP / RESET:** Bridged together (Connected to each other to enable the driver).

### 3. Potentiometer (Speed Control)
Used to vary the pulse delay sent to the stepper.
* **Pin 1:** 5V (Arduino).
* **Pin 2 (Wiper):** Connected to Arduino Analog Pin **A0**.
* **Pin 3:** GND.

##  Logic Flow
1.  **Read:** Arduino reads the voltage at Pin **A0** (0-1023 value).
2.  **Map:** Code converts this value into a time delay (milliseconds/microseconds).
3.  **Act:** Arduino sends a HIGH/LOW pulse to the **STEP** pin of the A4988 using that delay.
4.  **Result:** The motor turns faster or slower based on the potentiometer knob position.

  ##  Chassis & Construction Dimensions
The machine is built on a custom woodwork frame designed for stability and vibration dampening.

* *Main Base (36cm x 16cm):*
     Material: Wood.
     Function: Serves as the foundation for the heating assembly, the bottle cutter, and the electronics.
* *Spool Tower Support (36cm x 7cm):*
     Function: An elevated, narrower board mounted vertically/parallel to hold the spool axle and the transmission gears.
