# FlyBack Diodes and Kickback Protection

Flyback diodes are a commmon application of diodes for protecting circuit drivers from high voltage pulses that are produced from inductor kickback.

## Inductor Kickback
Inductors yield extremely high voltages across them as the current is cutoff from them instantaneously. Inductors dissipate high currents after its current source has dropped to 0. 
The voltage across the inductor is the product of its inductance and its change in current over time:
<p align="center">
    <img src="https://render.githubusercontent.com/render/math?math=\color{red} v = L{\dfrac{di}{dt}}">
</p>

Take this simple solenoid circuit: (Source in image link)\
[![img](/Applications/img/inductive-kickback-without-protection.webp)](https://www.allaboutcircuits.com/textbook/lsemiconductors/chpt-3/inductor-commutating-circuits/)

When the switch is opened there is an instantaneous drop in current over time which causes a massive negative voltage over the inductor. The inductor releases its current through the switch through an arc (often thousands of volts) as the switch travels to the open state. This is potentially harmful ESD to the driving circuitry. This effect is called inductor kickback.


## Kickback Prevention
Flyback diodes prevent arcing that occurs since they facilitate an avenue for inductor current flow during the kickback time. This is done by placing a diode in parrallel with the inductor where the anode is connected to the +VDC and the cathode to ground:(Source in image link)\
[![img](/Applications/img/inductive-kickback-with-protection.webp)](https://www.allaboutcircuits.com/textbook/semiconductors/chpt-3/inductor-commutating-circuits/)

When the current is flowing through the inductor in the positive direction the diode is open and is inactive. At the moment the switch is opened the diode becomes active and facilitates a closed loop current drain for the inductor to ground. This removes the possibility of arcing as a result of the current having nowhere to go protecting the driving circuitry.
