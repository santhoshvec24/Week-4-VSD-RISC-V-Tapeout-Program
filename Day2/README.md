# Velocity Saturation and basics of CMOS inverter VTC

From the graph, we can able to observe that it has two different areas which is identified using the Vds = Vgs - Vt. 

**Linear region:**
- The drain current is linear function of the drain-source voltage (when drain-source voltage is not exceed Vds)
- It is defined for Vds < (Vgs -Vt)

**Saturation region:**
- The drain current (Id) depends on channel length modulation and Vds.
- It is defined for Vds ≥ (Vgs - Vt).

- The region before Vds = Vgs - Vt is the Linear Region, where Id varies linearly with Vds.
- The region after Vds = Vgs - Vt is the Saturation Region, where Id is influenced by channel length modulation and Vds.

<img width="1162" height="719" alt="image" src="https://github.com/user-attachments/assets/d3ff32c8-789c-4ea2-b72f-e2934a87b4f7" />

**Observation 1: Long Channel Vs Short Channel for NMOS**
The plot below compares NMOS output characteristics for long channel and short channel devices with same W/L ratio:

<img width="1376" height="582" alt="image" src="https://github.com/user-attachments/assets/1603b648-9bd3-48c5-985c-887d8b6c33f7" />

In the figure, the left plot shows a long-channel NMOS transistor with W = 1.8 μm and L = 1.2 μm, while the right plot shows a short-channel transistor sized at W = 0.375 μm and L = 0.25 μm.

Since the channel length of the second device is below 0.25 μm, it falls into the short-channel MOSFET category.

Even though both transistors have the **same W/L ratio**, their actual width and length values are different. This setup helps us fairly compare how device behavior changes when the channel is scaled down, without letting the W/L ratio influence the results.

**Long Channel**
- There is a quadratic dependencies on gate voltage.
- In this, the drain current is in quadratic function of the gate voltage always.
- In long-channel devices, carriers accelerate freely, giving higher Id.

**Short Channel**
- There is a linear dependence on gate voltage.
- One of the short channel effect is the Voltage Saturation Effect.
- In the short-channel device, the drain current is quadratic with gate voltage at lower Vgs values, but at higher Vgs, it becomes almost linear.

When Vds is fixed and we gradually increase Vgs:

- For long-channel MOSFETs, the drain current (Id) increases in a smooth, quadratic way as Vgs rises. This matches the ideal MOSFET behavior described in basic theory.
- For short-channel MOSFETs, Id initially follows the same quadratic pattern at lower values of Vgs. But as Vgs continues to increase, the curve starts to level off and becomes more linear instead of quadratic.

This happens because of velocity saturation. At high electric fields, the electrons in the channel reach their maximum speed. Even if Vgs increases further, the electrons can’t move any faster, so the current stops following the ideal quadratic law and grows more slowly — almost linearly.

So, the plot clearly shows how in short-channel devices, velocity saturation changes the Id–Vgs behavior, making it shift from quadratic to linear at higher gate voltages.


For Short Channels, there are totally four regions.
So first of all, we gonna see the voltage saturation effect,

- At the lower electric fields, velocity is the linear function of the electric fields
- After some point, at the higher electric fields, it is saturated that's the velocity becomes constant due to *Scattering Effect*
  
<img width="1387" height="595" alt="image" src="https://github.com/user-attachments/assets/58ab16db-c7b9-4bcb-ae47-fdc0a045c701" />

for continuity, we put E=Ec and we get the value of critical electric field value is as follows
<img width="1025" height="606" alt="image" src="https://github.com/user-attachments/assets/925edd97-2b2a-401f-b709-38da88266ea3" />

After substitute the value of Vn to drain current, we got a complex equation

<img width="1238" height="369" alt="image" src="https://github.com/user-attachments/assets/0fd6237a-7e0e-456b-98f3-53313ae58544" />

Now let's dive into Voltage Saturation Effect,

<img width="986" height="496" alt="image" src="https://github.com/user-attachments/assets/9101f0bc-b9b2-4e6c-8dd9-4d3ff2290c1b" />

Let's analyse that when the value of Vgt is minimum, the transistor will be in the saturation region.
For Saturation region which is higher voltage for Vds operation, the value of drain current is
<img width="455" height="195" alt="image" src="https://github.com/user-attachments/assets/38ce5e0c-ec4f-42b4-984a-b6cd20701744" />

Now for the value of Vds is minimum, then the transistor is in resistive or linear region of operation.  
<img width="422" height="92" alt="image" src="https://github.com/user-attachments/assets/8da164f9-01df-4ebc-8e3c-dcaa78573d1f" />
then the third term which has [1+λ Vds] will be approx. equal to one.

Now in the short channel, when the Vsat is minimum
<img width="932" height="131" alt="image" src="https://github.com/user-attachments/assets/de20c8bf-6b9d-4181-94fc-e1558529659a" />

### Observation 2

- from this, we can able to see that for short channel, the peak current is low compared with the long channel.
- This is due to Voltage Saturation Effect causes the device to saturate early.
- So that's why for the same W/L ratio, there is two different cases.

Left Plot: W = 1.8μm, L = 1.2μm → Long-channel device
    - Peak current = 410 μA
    
Right Plot: W = 0.375μm, L = 0.25μm → Short-channel device
    - Peak current = 210 μA

Although short-channel devices offer faster switching and smaller dimensions, their maximum drain current (Id) is lower compared to long-channel devices.



```bash
vim day2_nfet_idvds_L015_W039.spice
```

<img width="1129" height="704" alt="Screenshot from 2025-10-18 10-33-46" src="https://github.com/user-attachments/assets/e6974de7-0bc4-4d87-b7f5-a33da162f228" />

plot the waveform in ngspice
```bash
ngspice day2_nfet_idvds_L015_W039.spice
plot -vdd#branch
exit
```

<img width="1348" height="905" alt="image" src="https://github.com/user-attachments/assets/6c8d3c02-b94f-4728-b02c-fa104ca96faf" />

The plot of Ids vs Vds over constant Vgs:

<img width="695" height="613" alt="image" src="https://github.com/user-attachments/assets/e54f1a8a-c39c-4e39-9be9-052a52486161" />

plot the waveform in ngspice

```bash
ngspice day2_nfet_idvgs_L015_W039.spice
plot -vdd#branch
```
The plot of Ids vs Vgs over constant Vds:

<img width="695" height="613" alt="image" src="https://github.com/user-attachments/assets/02756cd6-ee2f-47a0-8fe0-cbb4a84a4328" />




