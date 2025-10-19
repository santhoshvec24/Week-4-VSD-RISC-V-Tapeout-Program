# CMOS Switching Threshold and Dynamic Simulation

The VTC is the plot of Vout (y-axis) vs Vin (x-axis) when Vin is slowly swept from 0 to VDD. It fully characterizes the static switching behavior of the inverter.
  - `Vout = fn(Vin)`

You gradually increase the input voltage (Vin) from 0 to VDD and record the corresponding steady-state output (Vout). The resulting VTC curve can be divided into three distinct regions:

Low input region (Vin ≈ 0) :
The PMOS transistor is fully ON, and the NMOS is OFF. As a result, the output voltage remains close to VDD.

Transition region: As Vin increases, both transistors conduct partially. The output voltage starts to drop from VDD toward 0 V. This is the region where the inverter switches states, and the switching threshold (Vm) is located here — the point where Vin = Vout.

High input region (Vin ≈ VDD):
The NMOS transistor is fully `ON`, the PMOS is `OFF`, and the output voltage settles near 0 V.

The S-shaped VTC curve appears because the NMOS and PMOS transistors take turns controlling the output as the input voltage changes.

**When Vin is low:**
The NMOS is completely `OFF`, and the PMOS is fully on. This creates a strong path from VDD to the output, keeping Vout `close to VDD`.

**As Vin starts to rise:**
The NMOS begins to turn `ON` while the PMOS gradually turns `OFF`. In this region, both transistors are partially conducting, and the output voltage depends on their relative strengths — similar to a voltage divider.

**Around the midpoint:**
Both transistors conduct about `equally`. This causes the output voltage to drop rapidly, creating the steep middle section of the curve. This is where the inverter switches state and exhibits high gain.

**When Vin is high:**
The PMOS is completely `OFF`, and the NMOS fully conducts, pulling the output down to ground (`0 V`).

---

## SPICE simulation for CMOS inverter

<img width="1304" height="599" alt="image" src="https://github.com/user-attachments/assets/145433fe-e20b-44be-8ad8-b52ab0ab535e" />

This image shows how to create a SPICE deck for a CMOS inverter.

To build it, you need to:

**Connect the components**: Define how the PMOS (M1), NMOS (M2), power supply (VDD), ground (VSS), input (Vin), and output (Vout) are connected in the circuit.

**Set component values**: Specify details like transistor sizes (W/L), supply voltage (e.g., 2.5V), and the load capacitor (e.g., Cload = 10 fF).

**Identify circuit nodes**: Understand the key nodes in the circuit — for example, `in`, `out`, `VDD`, `VSS`, and the terminals of each transistor.

**Assign names to the nodes**: Give each node a clear and consistent name to make the netlist easier to write, simulate, and interpret.

By doing this, you create a clean and accurate SPICE netlist that can be used to simulate the CMOS inverter correctly.






```bash
vim day3_inv_vtc_Wp084_Wn036.spice
```
<img width="1062" height="756" alt="image" src="https://github.com/user-attachments/assets/abb1cfd1-22ae-4096-9073-a6d9d6a6ac65" />

to plot the graph 
```bash
ngspice day3_inv_vtc_Wp084_Wn036.spice
plot out vs in
```

<img width="708" height="616" alt="image" src="https://github.com/user-attachments/assets/263b8064-f82c-404e-a965-e91e9822bdb0" />

```bash
vim day3_inv_tran_Wp084_Wn036.spice 
```
<img width="997" height="651" alt="image" src="https://github.com/user-attachments/assets/6930d02d-a161-402a-b95e-e22a8138141f" />

```bash
ngspice day3_inv_tran_Wp084_Wn036.spice 
plot out vs time in
exit
```
<img width="701" height="611" alt="Screenshot from 2025-10-18 16-50-16" src="https://github.com/user-attachments/assets/dd96d174-b40c-467b-a0b0-a9800841acd6" />

