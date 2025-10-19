# CMOS Power Supply and Device Variation Robustness Evaluation

Vary supply voltage ( Vdd ) and re-plot VTCs to observe how switching threshold shifts, Modify transistor sizing (e.g. W/L of PMOS or NMOS) to simulate device variation, and observe effects on VTC, noise margins, delays.

---

## Why Is This Important?

- **Ensures Reliable Operation:** Digital circuits can experience variations in supply voltage (V<sub>DD</sub>) or transistor parameters (threshold voltage, mobility, etc.) due to process, temperature, or aging. Studying these variations ensures the circuit functions correctly under all conditions.

- **Predicts Performance Impact:** Variations can change the **switching threshold (V<sub>M</sub>)**, noise margins, propagation delays, and power consumption. Understanding these effects helps designers anticipate how performance may shift.

- **Improves Circuit Robustness:** Simulating worst-case scenarios allows designers to **guarantee correct logic levels** and prevent failures from marginal conditions.

- **Supports Yield Optimization:** Differences in device characteristics across a wafer can cause some chips to fail specifications. Variation studies help **maximize yield** by designing circuits that tolerate these differences.

- **Guides Design Margins:** Helps designers **define safe operating margins** for voltage, timing, and current to ensure reliable operation even under stress.

- **Critical for High-Speed and Low-Power Designs:** Even small variations can significantly affect **timing and noise immunity**, making these studies essential in modern VLSI circuits.

---

## Simulation of `day5_inv_supplyvariation_Wp1_Wn036.spice` Netlist

to see the modular description
```bash
vim day5_inv_supplyvariation_Wp1_Wn036.spice
```
<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/fe86def6-a6cc-4e33-b028-77e8b05ca98b" />

plot the waveform in ngspice
```bash
ngspice day5_inv_supplyvariation_Wp1_Wn036.spice
```
<img width="700" height="620" alt="image" src="https://github.com/user-attachments/assets/9675dc94-214d-4650-8657-f50f3822371d" />




```bash
vim day5_inv_devicevariation_wp7_wn042.spice
```
<img width="926" height="791" alt="image" src="https://github.com/user-attachments/assets/2ecc166f-5572-46dd-8238-ca2145bd2777" />

plot the waveform using ngspice
```bash
ngspice day5_inv_devicevariation_wp7_wn042.spice
plot out vs in
```
<img width="926" height="791" alt="image" src="https://github.com/user-attachments/assets/24d9fa32-814f-4c48-89d1-a530a64e5600" />
