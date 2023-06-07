# Spice-Simulation

Circuit Design using sky130(ngspice):
   ------

Day 1: Drain current and Drain to source voltage:
----
    
Why we need circuit design and spice simulation beacause we are making timing claculation,cts other timing information comes from the LUP table that will be updated by 
    
circuit design and spice simulation (by tuning the w/l ration of pmos and nmos)
    
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/933d4370-8dea-4b61-8a01-c4df2908cf6a)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/cc5afca5-461e-4b6b-94db-e2c7934e4847)

    
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7d54c32e-9da3-4996-89bb-b7c60752314a)


Cross-sectional view of nmos
--------
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d93e9c4f-32c5-41d8-a449-1569c04c2d2b)
   

Working of Nmos:
-----

1)Depletion
    
2)Accumulation
    
3)Strong inversion
    
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/4d44c886-d6ea-44af-bf65-80523c3bb780)

Bulk connected to other than gnd:
--------
    

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d25d8459-d787-498e-915a-a16547f9081a)

    
Regions of Operation:
-----
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d108df26-2c63-41a4-8ae5-b19343942cd5)
    
Drift currect and Diffusion:
-----

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/ac3b10d3-5285-4604-8d21-9ca44e35c00c)

Equation of Current:
-----
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/6b3a060c-9404-4a06-b7ed-dbf269e250fb)
 
Linear region:
------
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/02fb63a7-6038-4d71-b903-0dfd346e1d0b)
    
Saturation Region:
-----

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7942a388-af09-4293-8895-80ebdd34437e)

    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/26171963-70bc-4b12-b347-21e70a9134a9)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/93284b81-fcf2-406a-be8f-82ab382f77b0)

Introduction to Spice:
-------
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/dc65daa8-b1f2-4a3e-8205-01dc4092422b)

Ceating Spice nelist:
------
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/012bf35d-b85b-4a13-bee8-138226ec80dc)

Define Tecnology Parameter:
------

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/af2b816f-01d4-45c1-9736-45294831284a)
    
    
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3d444791-ccb0-47cc-a443-1a28391f0b33)

Day 2:Volocity Saturation:
---


![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/299605dd-0584-4111-b941-adffe9e3f98d)

source name.cir

run

setplot

dc1

display

plot -vdd#branch


![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/5c8486a6-7ac1-43bf-81d7-99d91c2f6318)

![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/4dff2944-0ec5-4647-95be-5f975a1f64ef)

![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/7a883475-d08f-4f69-b983-a6964f7822e7)

CMOS Voltage Charectristics:
----

![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/3d622982-0b8d-4ecd-b106-44918d62c3d7)


![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/59cea36f-58d0-4533-9191-a9294d27f387)


![image](https://github.com/sangamanathpuncham/Spice-Simulation/assets/132802184/0237d44e-88e9-4072-9d46-dffaefd37c52)


Day 3: Switching thresold and Dynamic simulation:
----

Wider the width:

The switching voltage Vm is that where Vin=Vout (nmos and pmos in saturation), and it defines the robustness of the CMOS.

It is derived by setting IdsP=-IdsN to get Vm=RVdd/(1+R) where R=(KpVdsatP)/(KnVdsatN) and where Kp=Wp/LpKp' and Kn=Wn/Ln*Kn'. 

Given target Vm, we can derive from the previous equation the needed W/L ratios.

When the pmos width is wider than that of nmos, the switching voltage of the VTC shifts to the right slightly (advantage). As width of pmos increases as an integer multiple of that of 

nmos (for same L), the rise delay and fall delay decreases rapidly (time to charge decreases as width is wider) and increases respectively. For one some sizing (factor of 2), we observe 

an equal rise and fall times (symmetric property which is a typical characteristic of a clock inverter/buffer where resistance of pmos is approximately equal to resistance of nmos in that

case due to the W/L ratios). Other sizing for inverters is used to get regular inverter/buffer that would be preferred in the data path.


Day 4: Noise margin 
----

When Vin<=VIL (logic 0), Vout is expected to ber VOH, and when Vin>=VIH (logic 1), vout is expected to be VOL (note that the slope at VIL and VIH is -1). The noise margin is defined as

VIH-VIL (undefined region: voltage ranges at which the logic does not differentiate between 0 and 1). Noise margin high (interpereted as logic 1) = VOH-VIH and noise margin low 

(interpreted as logic 0) = VIL-VOL. Ideally, we want a CMOS inverter to have a noise margin of 0. When the width of the pmos increases with respect to nmos width, noise margin high 

increases while noise margin low stays the same then drops as the pmos is responsible for the high value output. Digital design relies on the areas of noise margin high and noise margin 

low.

Day 5:Power supply and Etching variation:
----

CMOS inverter can operate at supply voltage of even 0.5v and advantages are: at 0.5v, the gain (rate of change of output as input changes, change in output voltage dibided by change in 

input voltage at slopes of -1) is huge (close to 50% compared to 2.5v) and energy consumed is 1/2*CV^2 so less energy is consumed (close to 90% improvement compared to 2.5v). Disadvantage 

of using 0.5 power supply: very slow operation as fall time and rise time are huge -> huge impact on performance.


Etching is the process of creating patterns on substrates, in which materials will be removed selectively from a thin film on a substrate. Variation in L and W takes place because of non-

ideal mask, which in turn impacts the drain current. Variation in oxide thickness is due to non-idealities in the fabriaction process that leads to non-ideal oxidation process, which in 

process affacts the drain current. In a chain of inverters, sources of variation affect the inverters on sides more severely. To mimic device variations, Wn and Wp were varied from a 

strong pmos-weak nmos to a weak pmos-strong nmos, and from the VTCs we could see that there is a small shift in Vm, the switching voltgae, and small variations in the noise margins (high 

and low) -> the CMOS inverter is highly robust to device variation.



