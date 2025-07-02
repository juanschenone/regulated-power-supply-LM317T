# Regulated Power Supply Project – LM317T & 7812

This repository contains the complete academic project developed for the final assignment of the "Electrónica 1" course (Electromechanical Engineering – UNSL, FICA). The project involved the design, simulation, thermal analysis, and technical documentation of a regulated dual-output DC power supply.

## Overview

The power supply delivers two outputs:

* **Fixed output**: 12 V / 48 W regulated by LM7812 and assisted by a PNP transistor.
* **Variable output**: 3–13 V / 13 W regulated by LM317T with external resistive tuning.

This project covers all stages:

1. **Transformation**: 220 V AC to 15 V AC using a toroidal transformer.
2. **Rectification**: Full-wave bridge using GBJ15005.
3. **Filtering**: Capacitor smoothing (5000 µF).
4. **Regulation**: Linear regulators with thermal and current protection.
5. **Protection**: Diodos HER601 antiparallel, fuses, and internal IC protections.

## Python Current Model – Capacitor Discharge

The file `grafico_de_corriente_capacitor.py` models the **real current behavior** during the capacitor discharge phase of the rectification stage. Unlike simplified rectangular pulse approximations, this script uses a hybrid waveform:

* **Charging**: When input voltage exceeds capacitor voltage, modeled as sinusoidal.
* **Discharging**: Modeled as an exponential decay with time constant $\tau = RC$.
* **Total current**: Calculated as $i(t) = C \cdot \frac{dV_C}{dt} + I_{carga}$, where $I_{carga} = V/R$.

This estimation provides a more realistic current profile, crucial for thermal and electrical component sizing.

## Tools Used

* **Proteus 8** – Full simulation of circuit and oscilloscope behavior.
* **Python / NumPy / Matplotlib** – Real capacitor current modeling.
* **KiCad** – PCB layout, routing, 3D rendering.
* **Excel** – Thermal analysis and cost calculations.

## File Structure

```
/
├── grafico_de_corriente_capacitor.py   # Python script for i(t)
├── TP Final Electronica 1.pdf          # Full academic report (in Spanish)
└── README.md                           # This file
```

## Notes

* All simulations and calculations are tailored to a 50 Hz mains supply.
* All thermal analyses consider worst-case operating conditions.
* This project is part of the 4th year coursework of the Electromechanical Engineering degree.

---

**Author:** Juan Manuel Magallanes Schenone
[LinkedIn](https://www.linkedin.com/in/juanmaga1302) · [juanmaga.1302@gmail.com](mailto:juanmaga.1302@gmail.com)
Villa Mercedes, San Luis – Argentina
