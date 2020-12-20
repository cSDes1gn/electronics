# Pull-up & Pull-down Resistors

From (article)[https://learn.sparkfun.com/tutorials/pull-up-resistors/all] by sparkfun.

When we read an input from a microcontroller pin it is not easy to detect whether the pin is high (pulled up to Vcc) or low (pulled down to GND). This is due to a phenomena known as pin floating.

## Floating

Imagine we want to measure the digital input off a microcontroller ADC pin using a simple SPST switch. We would start by trying to connect the switch to the microcontroller pin and tie the output to Vcc:

![img](/Applications/img/pd-1.png)


We would expect that when the switch is closed the input reads a digital 1 (which is correct) but also when the switch is open it would read a digital 0. But this is not the case because the gate is not connected to ground instead it is floating. The microcontroller may register a low, but it might just as well register a high. By not being connect to Vcc, or GND, the I/O pin is susceptible to electrical noise that makes the I/O randomly fluctuate between low and high. Such sources include thermal noise and electromagnetic interference (EMI) since the leads of the chip act like tiny antennas when they are floating.

To mitigate this the next logical step is to tie the microcontroller input to GND so that both the switch states have active references. However when the switch is closed the outputs will be shorted. All we have to do now is add a current limiting resistor to the MCU input pin and we have a pull-down resistor configuration:
![img](/Applications/img/pd-2.png)

Or inversely the more common pull-up resistor configuration:
![img](/Applications/img/pu-1.png)