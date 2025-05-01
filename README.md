# CAD TECHNIQUES PROJECT

## Temperature Control Circuit in an Enclosure

**Author:** Cebanu Vitalie  

---

## Table of Contents
- Project Requirements
- Electrical Schematic
- Component Sizing
  - Current Mirror
  - Buffer
  - Differential Amplifier
  - Comparator
  - Relay and LED Signaling
- Simulations
  - Current Mirror
  - Buffer
  - Differential Amplifier
  - Comparator
  - LED Signaling
  - Relay
- Monte-Carlo / Worst-Case
- Bibliography

---

## Project Requirements

Design a temperature control system for an enclosure. The temperature sensor used:
- Measurable temperature range: **-30°C to +40°C**
- Maintained temperature range: **-10°C to 20°C**
- Sensor resistance: **13kΩ to 23kΩ**
- Circuit supply voltage: **13VDC**
- LED color: **purple**

### Block Diagram:
<pre> [Current Mirror]
        |
        v
[Impedance Matching]
        |
        v
 [Range Extension]
        |
        v
    [Comparator]
      /     \
     v       v
[Relay]   [LED Signaling]
</pre>
---

## Electrical Schematic

### Relay: FINDER 30.22.7.012.0010
- Coil resistance: 720Ω
- Coil current: 16mA
- Operating temperature: -40°C to +85°C

### Transistor: BC107A
- β = 50

---

## Component Sizing

### Current Mirror
- Selected current: **0.5mA**
- V_BE replaced by equivalent voltage source
- Transistor: **BC107A**  
  - Compact, low cost, reliable

### Buffer (Repeater)
- Op-amp used: **LM741**
- Provides input-output isolation (acts as a buffer)
- Can operate with single or dual supply voltages

### Differential Amplifier
- Reference voltage: **1.4V**
- Output voltage range: **0.1V to 5.1V**
- Required gain: **2.2**
- Resistors from E192 series used

### Comparator
- Thresholds calculated for -10°C and 20°C
- Resistors used: **2.87kΩ**, **1.04kΩ** (E192 series)
- Adjusted reference voltage and resistor ratios

### Relay and LED Signaling
- Comparator output toggles between 0V and Vcc
- LED and relay activated simultaneously
- LED current-limiting resistor: **300Ω** (E24, 5%)
- Transistor in saturation when output is high → relay activation

---

## Resistors Used
- 24.6kΩ, 49.9kΩ, 110kΩ, 1.04kΩ, 2.87kΩ, 300Ω
- 13kΩ, 7.23kΩ, 4.37kΩ, 1.4kΩ  
(Series: E192 / E24, Tolerances: 0.5% or 5%)

---

## Simulations

### Current Mirror
- Due to transistor imperfections, sensor branch current is not perfectly constant

### Buffer
- Output voltage ≈ input voltage

### Differential Amplifier
- Expands initial voltage variation from near 0V to ~5V

### Comparator
- Switching occurs around calculated thresholds

### LED Signaling
- Voltage stabilizes after LED turns on

### Relay
- Base current = 1mA → transistor saturation → relay activation

---

## Monte-Carlo / Worst-Case
(Statistical and worst-case scenario tests – details not included in document)

---

## Bibliography
1. CAD Techniques Course Notes  
2. Electronic Devices Course Notes  
3. [DE Lecture 6 - UTCN](http://www.bel.utcluj.ro/dce/didactic/de/DE_Curs6.pdf)  
4. [Purple LED Datasheet - SparkFun](https://cdn.sparkfun.com/datasheets/E-Textiles/Lilypad/Purple%20LEDs%20HT15-2102UPC.pdf)  
5. [Finder Relay - TME](https://www.tme.eu/ro/details/30.22.7.012.001/relee-electromagnetice-miniatura/finder/30-22-7-012-0010/)  
6. [E Series Standard Resistor Values](https://www.electronicsplanet.ch/en/resistor/e-series-of-standard-resistor-values.php)  
7. [ElectroBOOM YouTube](https://www.youtube.com/@ElectroBOOM)

---

