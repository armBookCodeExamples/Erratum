## Chapter 6 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### Code 6.13

The following code:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Code%206-13%20original.png" width="400">

Should be replaced by:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Code%206-13%20new.png" width="400">

It is also worth mentioning that on line 4 the expression *str++ is treated as *(str++) as the precedence of postfix ++ is higher than *.


---

### Table 6.5

The caption states "Address reference of the PCF8574 module. The addresses used in the proposed setup are highlighted." but the highlight is missing. It should be in the following way:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Table%206-5.png" width="400">

---

### Figure 6.21

Dotted square does not indicate the appropriate part of the signal and the text is incorrect.  
The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-21.png" width="300">

---

### Text before Figure 6.21

The following text:

> When a device is not transmitting, it does not establish either a low or high state in its SDA and SCL pins. If no device is transmitting, the SDA and SCL lines are in high state, because of the pull-up resistors (Rp1 and Rp2) that can be seen in Figure 6.20. Therefore, a manager that wants to transmit data establishes a start **bit condition** on the bus by setting SDA to a low state when the signal in SCL is high, as can be seen in Figure 6.21. The same figure also shows how the stop **bit condition** is established.

Should be replaced by:

> When a device is not transmitting, it does not establish either a low or high state in its SDA and SCL pins. If no device is transmitting, the SDA and SCL lines are in high state, because of the pull-up resistors (Rp1 and Rp2) that can be seen in Figure 6.20. Therefore, a manager that wants to transmit data establishes a start **condition** on the bus by setting SDA to a low state when the signal in SCL is high, as can be seen in Figure 6.21. The same figure also shows how the stop **condition** is established.

---

### Figure 6.23

The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-23.png" width="800">

---

### Text before Figure 6.23

The following text:

> Figure 6.23 shows the typical sequence of an I2C communication. Firstly, the device that starts the communication, called the manager device, establishes the **start sequence**, followed by the address message corresponding to another I2C device, called the subordinate. 

Should be replaced by:

> Figure 6.23 shows the typical sequence of an I2C communication. Firstly, the device that starts the communication, called the manager device, establishes the **start condition**, followed by the address message corresponding to another I2C device, called the subordinate. 

---

### Text before Figure 6.23

The following text:

> Note that this is followed by another start **bit** without any prior stop bit, after which the manager repeats the address of the subordinate, using the R/W bit to indicate that a read operation is being made. After that, the subordinate writes the 8 bits (indicated in blue) corresponding to the register data following the SCL pulses that are established by the manager. Finally, the manager generates the ACK bit (indicated in brown) and the stop **bit**.

Should be replaced by:

> Note that this is followed by another start **condition** without any prior stop bit, after which the manager repeats the address of the subordinate, using the R/W bit to indicate that a read operation is being made. After that, the subordinate writes the 8 bits (indicated in blue) corresponding to the register data following the SCL pulses that are established by the manager. Finally, the manager generates the ACK bit (indicated in brown) and the stop **condition**. 

---

### Text before Figure 6.24

The following text:

> Figure 6.24 shows the sequence to write the port pins value of the PCF8574 LCD module. The first four bits of the address, 1000, are fixed and cannot be changed. The next three bits, 111, correspond to A2, A1, and A0, as explained above. The last bit, 0, indicates that it is a write operation. In this way, the 8-bit address value **0b10001110** is obtained, which corresponds to 78 (in decimal notation). Lastly, it can be seen in Figure 6.24 that the port pin values are written (P7–P0). In this way, the display pins D7–D4, A, E, R/W, and RS are established.

Should be replaced by:

> Figure 6.24 shows the sequence to write the port pins value of the PCF8574 LCD module. The first four bits of the address, 1000, are fixed and cannot be changed. The next three bits, 111, correspond to A2, A1, and A0, as explained above. The last bit, 0, indicates that it is a write operation. In this way, the 8-bit address value **0b01001110** is obtained, which corresponds to 78 (in decimal notation). Lastly, it can be seen in Figure 6.24 that the port pin values are written (P7–P0). In this way, the display pins D7–D4, A, E, R/W, and RS are established.

---
### Figure 6.24

The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-24b.png" width="800">

---

### Figure 6.24 obtained using a logic analyzer

Using a logic analyzer (as the one shown in Figure 2.14) the signal shown in Figure 6.24 can be obtained:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/i2cCapture.png" width="800">

Notice: it can be seen that the signal value shown in Figure 6.24 between ACK and P7 is not correct.

---

### Figure 6.26

The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-26.png" width="800">

---

### Figure 6.28 obtained using a logic analyzer

Using a logic analyzer (as the one shown in Figure 2.14) the signal shown in Figure 6.28 can be obtained:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/SPICapture.png" width="800">

---

### Text before Figure 6.33

The following text:

> Finally, it should be noted that, unlike the I2C bus, the SPI bus does not have a start **bit**, a stop **bit**, or an ACK bit.

Should be replaced by:

> Finally, it should be noted that, unlike the I2C bus, the SPI bus does not have a start **condition**, a stop **condition**, or an ACK bit.

---

### Code 6.31

It can be argued that:

> #define SPI1_CS PD_14

Should be replaced by:

> #define SPI1_SS PD_14

Given that the signal is named Subordinate Select (see Table 6.8). However, in many integrated circuits the pin that is connected to the signal Subordinate Select is labeled as "CS" (Chip Select) so it make sense to use the name "SPI1_CS" in the definition.

---

### Code 6.41 and Code 6.45

An image is missing in the book of "Report page" in the graphic display. The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-xx%20-%20GLCD%20text%20Temp,%20gas%20and%20alarm.png" width="400">

---
