# Solar-Powered Plant Alarm 

## Project Objective
The primary objective of this project is to develop a PCB design for a solar-powered soil moisture warning system that operates entirely without the need for external batteries. The system is powered by a 6V solar cell, which provides sufficient voltage to drive the entire circuit during daylight hours. This eliminates the ongoing costs and environmental waste associated with disposable batteries while maintaining a high degree of reliability.

## How It Works
The circuit relies on the interaction between a moisture sensor (two metal probes) and a transistor-based logic gate to trigger an alarm under dry conditions. 

* **Sensing:** The metal probes inserted into the soil act as a variable resistor whose value changes significantly depending on the water content. 
* **Power Indication:** When the solar panel generates at least 4V, current flows through a current-limiting resistor and two series LEDs to provide visual confirmation of the power supply status.
* **Logic & Alarm:** If the soil is wet, the low resistance between the probes allows current to flow to the base of the first NPN transistor (2N3904), turning it on and effectively pulling the base of the second transistor to ground. In this state, the piezoelectric buzzer remains silent. When the soil dries out, the resistance increases, deactivating the first transistor. This inverts the signal, turning on the second transistor and completing the circuit to sound the buzzer.
* **Calibration:** The specific detection threshold is calibrated using a 50kΩ potentiometer, ensuring the alarm only sounds when the moisture level is truly inadequate for the specific plant.

## Visuals
*(Note: Upload your exported images to your repository and replace the filenames below if necessary)*

**Electrical Schematic** ![Electrical Schematic](./Schematic.png)

**PCB Assembly & Routing** ![Top Copper Layer](./Top_Copper.png)

## Repository Contents
* **`/Capture CIS`**: Contains the raw Cadence OrCAD schematic database (`.dsn`) and project files.
* **`/PCB designer`**: Contains the final Allegro board layout file (`.brd`).
* **`/CEM-1606`**: Custom library files (symbol and footprints) for the magnetic buzzer.
* **`/Gerbers`**: Manufacturing outputs (RS-274X Gerbers, NC Drill files, and Drill Chart) ready for fabrication.
* **`BOM.csv`**: Full Bill of Materials.
* **`Project_Report.pdf`**: Complete academic documentation, including DRC, Net verification, and cross-references.

## Conclusion
This project illustrates a successful integration of simple electronic principles to solve a practical everyday problem. By utilizing basic components like NPN transistors and resistors to create a logic inverter, it proves that complex integrated circuits are not always necessary to achieve effective automation in gardening applications.
