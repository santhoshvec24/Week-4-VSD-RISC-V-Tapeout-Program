# Day-1 Basics of NMOS Drain(id) Vs Drain-to-source Voltage(Vds)

A comprehensive guide to understanding CMOS transistor behavior, circuit analysis, and practical SPICE simulation using Sky130 technology.

---

### Installation

#### Clone the workshop repository:
```bash
git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git
cd sky130CircuitDesignWorkshop
cd design
```
<img width="733" height="509" alt="image" src="https://github.com/user-attachments/assets/f1fef053-c169-4285-9be8-5e3ab3f2028c" />

**Install ngspice (open-source SPICE simulator):**
```bash
sudo apt-get update
sudo apt-get install ngspice
```

#### Running Your First Simulation
**Execute a SPICE Netlist:**
```bash
ngspice day1_nfet_idvds_L2_W5.spice
```
**Generate Plots and for Saving Waveform Data**
```bash
plot -vdd#branch
write output.raw
wrdata output.csv -vdd
quit
less output.csv

```
<img width="698" height="615" alt="Screenshot from 2025-10-17 19-40-47" src="https://github.com/user-attachments/assets/60579b30-e904-4373-b722-e74ef3f76af5" />

at desgin directory

```bash
vim day1_nfet_idvds_L2_W5.spice
```
