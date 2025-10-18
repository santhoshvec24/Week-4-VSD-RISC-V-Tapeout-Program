# CMOS Switching Threshold and Dynamic Simulation

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

