## Chapter 6 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

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

### Figure 6.24

The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-24.png" width="800">

---

### Figure 6.26

The figure should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter6/Figure%206-26.png" width="800">

---

### Text before Figure 6.33

The following text:

> Finally, it should be noted that, unlike the I2C bus, the SPI bus does not have a start **bit**, a stop **bit**, or an ACK bit.

Should be replaced by:

> Finally, it should be noted that, unlike the I2C bus, the SPI bus does not have a start **condition**, a stop **condition**, or an ACK bit.. 

---
