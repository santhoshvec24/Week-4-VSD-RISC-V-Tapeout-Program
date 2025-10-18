# Velocity Saturation and basics of CMOS inverter VTC

```bash
vim day2_nfet_idvds_L015_W039.spice
```

<img width="1129" height="704" alt="Screenshot from 2025-10-18 10-33-46" src="https://github.com/user-attachments/assets/e6974de7-0bc4-4d87-b7f5-a33da162f228" />

```bash
ngspice day2_nfet_idvds_L015_W039.spice
plot -vdd#branch
exit
```
<img width="1348" height="905" alt="image" src="https://github.com/user-attachments/assets/6c8d3c02-b94f-4728-b02c-fa104ca96faf" />

now you can able to see the graph for vds
<img width="695" height="613" alt="image" src="https://github.com/user-attachments/assets/e54f1a8a-c39c-4e39-9be9-052a52486161" />

```bash
ngspice day2_nfet_idvgs_L015_W039.spice
plot -vdd#branch
```
now you can able to see the graph for vgs 
<img width="695" height="613" alt="image" src="https://github.com/user-attachments/assets/02756cd6-ee2f-47a0-8fe0-cbb4a84a4328" />
