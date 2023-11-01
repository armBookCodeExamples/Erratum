## Chapter 12 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### Explanation of Table 12.4

For the sake of clarity, instead of:

> "The reader should note that alongside each is a simplified approach that is appropriate for many projects"

The text could be:

> "The reader should note that alongside each **element** is a simplified approach that is appropriate for many projects"

---

### Table 12.6

A requirement is missing

> "4.1.3 Show the current moisture level"

---

### Example 12.3

It might be a good idea to include at this point an schematic diagram of the circuit: _"a designed representation of the elements of a system using abstract, graphic symbols rather than realistic pictures"_, which is used extensively in electronics. For example, the following figure is a schematic diagram of an electronic design whose propose is not relevant to discuss here:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter12/Schematic-Diagram.png" width="600">

---

### Figure 12.3

There is a GND connection missing in the breadboard. The missing connection is shown in this figure:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter12/Figure12-3.png" width="600">

Also, if the system doesn't work fine, it is recommended to include a diodo in the solenoid, as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter12/Solenoid-Diode.png" width="200">

By last, if the system doesn't work fine it is suggested to use a independent 5 V power source to supply the relay module.

---

### Table 12.18 ###

Some elements are missing in the Bill of materials, as for example:
- 10 kΩ trimpot/potentiometer
- 1 kΩ resistor

However, these elements do not significantly alter the total cost.

---

### Example 12.4

Maybe it is better to change the order in the explanation.

Instead of:

> *Table 12.19 Functionalities and roles of the home irrigation system modules.*
> *Table 12.20 to Table 12.25 Private objects and variables of the modules.*
> *Table 12.26 to Table 12.32 Public functions of the modules.*
> *Figure 12.7 Diagram of the proposed FSM.*
> *Figure 12.8 to Figure 12.11 Layout of the LCD.*

It could be:

> *Table 12.19 Functionalities and roles of the home irrigation system modules.*
> *Figure 12.7 Diagram of the proposed FSM.*
> *Figure 12.8 to Figure 12.11 Layout of the LCD.*
> *Table 12.20 to Table 12.25 Private objects and variables of the modules.*
> *Table 12.26 to Table 12.32 Public functions of the modules.*

---

### Text in Table 12.30

Instead of:

> "*waitedTimeMustBeReset* and ***waitedTimeMustBeReset*** are set to true."

The text should be:

> "*waitedTimeMustBeReset* and ***irrigatedTimeMustBeReset*** are set to true."

---

### Figure 12.9

Current moisture level should be below 30% (it says 40%); otherwise the system will not irrigate.
  
---

### Code 12.5

Notice that in this program there is no need for a debounce on lines 38, 45, and 52 because the loop is executed every 100 miliseconds, as illustrated in Figure 12.4

---

### Note on Code 12.16

Regarding:

> **NOTE**: This same type of initialization and use was implemented in previous chapters to control the buzzer using the relay, given that buzzers are 5 V devices, and it is not advised to turn them on directly using a digitalOut object.

Is not absolutely precise, because the new version of Example 3-5 uses a DigitalOut object and a relay. The important fact is that a transistor is used in the new setup.

---

### Code 12.25

The following lines are incorrect:

> //=====[Declaration and initialization of public global objects]===============
>
> static DigitalInOut relayControlPin(PF_2);

Given that *relayControlPin* is declared using the reserved word +static*, it is not public, but private.

---

### Explanation of Code 12.25

Instead of:

> "Finally, the function *relayRead()* is shown on lines **57 to 61**"

The text should be:

> "Finally, the function *relayRead()* is shown on lines **58 to 60**"

---

### Tip on Code 12.27

Instead of:

> TO_HOUR

The text should be:

> TO_HOURS

---

### Example 12.9 - Example of verification

An example of verification could be if a requirement is defined as 

> "all the software modules must be properly encaspsulated"

Then in the verification it can be assessed if this requirement is fullfiled.
However, the user will not care about this, neither it will asses this requirement.

---

### Explanation of Figure 12.12 (working principle of HC-SR04 ultrasonic module)

Instead of:

> "The Trig pin is used to trigger a high-frequency sound. When the signal is reflected, the echo pin changes its state. The time between the transmission and reception of the signal allows us to calculate the distance to an object,..."

The text could be:

> "The Trig pin is used to trigger a high-frequency sound (a 40 kHz acoustic burst). The echo pin changes its state while this acoustic burst is travelling in between the sensor and the object to be detected. The time between the transmission and reception of the signal allows us to calculate the distance to an object,..."

This is shown in the following figure:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter12/HCSR04-Signals.png" width="600">

The formulae to be used to calculate the distance is:

> Distance in centimeters = echo_pulse_time(&micro;s)/58  
> Distance in inches = echo_pulse_time(&micro;s)/148

For example:

> 10 centimeters = echo_pulse_time of 580 &micro;s

---

### Figure 12.14

Instead of:

> "SCA"

The label should be

> "SDA"

Also, is worth mentioning that the digital barometric pressure module shown in Figure 12.14 is BMP180.

---

