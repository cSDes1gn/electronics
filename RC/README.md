# RC Circuits

All electrical systems have a time delay when voltage, signal, DC or AC is applied to it. This time delay is called the circuit's time constant (τ) which represents the time response of the circuit when a step voltage or signal is applied.

## Capacitor Rules
Initially as voltage is applied to the capacitor it behaves like a short circuit drawing an infinitely large sum of current @ t=0. Over time the capcacitor draws charging current and charges up causing an exponential decrease in the rate of the capacitor charge.  When the voltage is reduced the capacitor begins to discharge in the opposite direction. The charging and discharging of a capacitor is never instant but takes some amount of time to occur within a certain percent of its max capacity. The time it takes is the time constant τ.

## RC Charging
If a resistor and capacitor are in series the capacitor will charge through the resistor until the voltage across the capacitor is equal to the supply voltage. The time it takes for the capacitor to fully charge is 5τ. The time it takes for a capacitor to charge 63% of its capacity is equal to τ due to the exponential decay of voltage across the capacitor as it charges.

From AspenCore Inc:\
[![img](img/RC_charging.png)](https://www.electronics-tutorials.ws/rc/rc_1.html)

## Time Constant
The time constant is given by:
<p align="center">
    <i>τ = RC</i>
</p>
Where R is the resistance in Ohms and C is the capacitance in Farads.

## Instantaneous Voltage Across Capacitor
The instantaneous voltage over the capcitor during the charge cycle is given by:
<p align="center">
    <i>V<sub>c</sub> = V<sub>s</sub>(1-e<sup>(-t/τ)</sup>)</i>
</p>
Where V<sub>c</sub> is the voltage across the capcitor, V<sub>s</sub> is the supply voltage, t is the instantaneous time since voltage application and τ is the time constant of the circuit.

## Capacitor Charge Voltage and Current
From AspenCore Inc.:\
[![img](img/cap_discharge.png)](https://www.electronics-tutorials.ws/rc/rc_1.html)

After 4τ the capacitor is virtually charged and is said to be steady state. Therefore the interval [0, 4τ] is the transient period.


## RC Discharging
If a fully charged capacitor is disconnected from its supply voltage it will hold its charge indefinitely (assuming ideal conditions) until it is discharged. If we take the RC charging circuit and short the battery and close the switch we have an RC discharging circuit.
From AspenCore Inc.:\
[![img](img/RC_discharging.png)](https://www.electronics-tutorials.ws/rc/rc_2.html)

Similarily to the charging case the time it takes for the capacitor to fully discharge is 5τ. The time it takes for a capacitor to discharge 63% of its capacity is equal to τ due to the exponential decay of voltage across the capacitor as it discharge.

## Instantaneous Voltage Across Capacitor
The instantaneous voltage over the capcitor during the charge cycle is given by:
<p align="center">
    <i>V<sub>c</sub> = V<sub>s</sub>(e<sup>(-t/τ)</sup>)</i>
</p>
Where V<sub>c</sub> is the voltage across the capcitor, V<sub>s</sub> is the supply voltage, t is the instantaneous time since V<sub>c</sub> drain and τ is the time constant of the circuit.

## Capacitor Discharge Voltage and Current
From AspenCore Inc.:\
[![img](img/cap_charge.png)](https://www.electronics-tutorials.ws/rc/rc_2.html)



## Practical Problem
Generate a 100ns active low WRITE ENABLE pulse for an EEPROM chip using an RC circuit.

First we know we have to create an active low pulse. To simulate this we can use the transient property of discharged capacitors. When a voltage is applied across a discharged capacitor it behaves like a short circuit this will cause our signal to immediately drop to GND. Then using an RC time constant we can retain our source voltage in 5τ.


<p align="center">
    <i>τ = 100ns / 5</i><br>
    <i>R / C = 100ns / 5</i>
</p>

Any value of R and C to fit the ratio will work but for simplicity lets make R 5Ω and C 100nF. We have our RC circuit here with our voltage probe to WRITE ENABLE:

![img](img/WE1.png)

In order for this circuit to be reusable we need to discharge the capacitor after each voltage application so it will behave like a short circuit. We do this by an arbitrary size discharge resistor creating a closed circuit between the capacitor and Vcc.

![img](img/WE2.png)

Now we can apply a voltage across the discharged capacitor by closing the switch causing the voltage across the capacitor to drop to 0V instantaneously then charging using the time constant determined by R9 and C8. Based on the values chosen the capacitor will reach steady state @ 100ns since the switch was closed. After the switch is opened, the capacitor will discharge through R10 resetting the circuit.