# Pull-up & Pull-down Resistors

When we read an input from a microcontroller pin it is not easy to detect whether the pin is high (pulled up to Vcc) or low (pulled down to GND). This is due to a phenomena known as pin floating.

## Floating

Imagine we want to measure the digital input off a microcontroller ADC pin using a simple SPST switch. We would start by trying to connect the switch to the microcontroller pin and tie the output to Vcc:

![img](/Applications/img/pd-1.png)

We would expect that when the switch is closed the input reads a digital 1 (which is correct) but also when the switch is open it would read a digital 0. But this is not the case because the gate is not connected to ground instead it is floating. The microcontroller may register a low, but it might just as well register a high. By not being connect to Vcc, or GND, the I/O pin is susceptible to electrical noise that makes the I/O randomly fluctuate between low and high. Such sources include thermal noise and electromagnetic interference (EMI) since the leads of the chip act like tiny antennas when they are floating.

To mitigate this the next logical step is to tie the microcontroller input to GND so that both the switch states have active references. However when the switch is closed the outputs will be shorted. All we have to do now is add a current limiting resistor to the MCU input pin and we have a pull-down resistor configuration with active high logic:

![img](/Applications/img/pd-2.png)

Or inversely the more common pull-up resistor configuration with active low logic:
![img](/Applications/img/pu-1.png)

## Pull-Up/Down Resistor Value

In general a 10KΩ resistor is suitable for a pull-up resistor configuration.

A low resistor value is called a strong pull-up (more current flows), a high resistor value is called a weak pull-up (less current flows).
The value of the pull-up resistor needs to be chosen to satisfy two conditions:
1. When the button is pressed, the input pin is pulled low. The value of resistor R1 controls how much current you want to flow from VCC, through the button, and then to ground.
2. When the button is not pressed, the input pin is pulled high. The value of the pull-up resistor controls the voltage on the input pin.

For condition 1, you don't want the resistor's value too low. The lower the resistance, the more power will be used when the button is hit. You generally want a large resistor value (10kΩ), but you don’t want it too large as to conflict with condition 2 and cause the voltage drop at the pin to be too low. For example a 4MΩ resistor might work as a pull-up, but its resistance is so large that it may not always provide a active high voltage drop.

### Internal MCU Pin Impedance

The MCUs pins commonly have an input impedance of 100K-1MΩ:
![img](/Applications/img/pu-2.png)

This creates a voltage divider on the MCU input pin where the voltage is read from. It is important that we meet the minimum threshold requirement for the high state while using the least current possible. As a general rule we should select a resistor value that is an order of magnitude less than the input impedance of the pin. So for an input impedance of 100K we should select a 10K pull-up resistor.

Some microcontrollers like the ATMEGA328 have firmware selectors for enabling/disabling internal pull-up/pull-down resistors.

## RC Time Analysis

The system that feeds the input of the MCU is essentially a capacitor coupled with a pull-up/pull-down resistor which creates an RC filter and an RC time constant. The cost to increasing the resistance is that the RC time constant will rise making the switching time at the MCU input slower. This is why you will often see strong pull-up (1k to 4.7KΩ) resistors on USB, I2C or other high speed signal lines.


## Sources
1. [Sparkfun](https://learn.sparkfun.com/tutorials/pull-up-resistors/all)
2. [Mouser](https://www.mouser.com/blog/dont-leave-your-pins-floating)