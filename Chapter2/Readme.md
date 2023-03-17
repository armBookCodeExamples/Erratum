## Chapter 2 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m-v3.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-on-cortex-m-v3.pdf)

---

### Code 2.16

The implementation of the command "4" accepts a code even if the alarm is not active.
To avoid accepting a code if the alarm is not active, Code 2.16 can be modified as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter2/Code2-16-Improved.png" width="600">

Notice that if five incorrect codes are entered then the System Blocked LED will turn on and then system can be unblocked only by means of reseting the NUCLEO board or by using this command "4" to enter the correct code. In this scenario if the command "4" is used and the correct code is entered then the System Blocked LED will not be turned off by the current version of the code.

---

### Table 2.4

The following text:

> char codeSequence[NUMBER_OF_KEYS] = {'1','1','0','0'};

Should be replaced by:

> int codeSequence[NUMBER_OF_KEYS] = { 1, 1, 0, 0 };

---

### 2.3 Under the Hood 

After the book was printed we realized that the reader would benefit if more insight on serial communications protocols based on UARTs is provided in this section.
The content added (see below) should be read after reading the TIP that states:

> TIP: Sequences like the one shown in Figure 2.13 can be seen each time the NUCLEO board and the PC exchange messages by means of connecting an oscilloscope or a logic analyzer to the pins Tx and Rx of CN5, as shown in Figure 2.14. It is not explained here how to use oscilloscopes and logic analyzers because that topic is beyond the scope of this book.

#### Content added:

The signal shown in Figure 2.14 has the voltage levels introduced in Figure 2.13 (i.e., high 3.3 volts and low 0 volts). However, if the signal is used to connect modules that not very close to each other, these voltage levels are quite low and prone to suffer electromagnetic interference. Therefore in many applications the RS-232 (Recommended Standard 232) is used. 

The RS-232 defines not only the Transmitted Data (TxD), Received Data (RxD) and Ground (GND) signals, but also a set of up to nine additional signals that are used in some implementations: Data Terminal Ready, Data Carrier Detect, Data Set Ready, Ring Indicator, Request To Send, Clear To Send, Transmitted Data, Received Data and Protective Ground. However, in most modern applications only the TxD, RxD and GND signals of RS-232 are used.

The typical RS-232 logic and voltage levels are as shown in Table 2.6. These higher voltages in comparison with 3.3 volts and 0 volts results in higher tolerance to electromagnetic interference.

**Table 2.6 RS-232 logic and voltage levels**

| Logic |   Voltage   |
| ----- | ----------- |
|   0   | +3 to +15 V |
|   1   | −15 to −3 V |

There are modules that can be used to adapt the 3.3 volts and 0 volts levels signal to the RS-232 standard voltage levels. Most of these modules are based on the MAX232 integrated circuit.

In some cases a larger distance should be covered in electrically noisy environments and many devices interconnected using as few cables as possible. In those scenarios the RS-485 standard can be used by means of modules based for example in the MAX485 integrated circuit. RS-485 has only two signals, namely A and B, and does not have a ground signal. In RS-485 the logic states 0 and 1 are signaled by means of setting a differential voltage between signals A and B, as shown in Table 2.7. The differential voltage between A and B should be at least 1.5 V.

**Table 2.7 RS-485 logic and voltage levels**

| Logic | A signal | B signal |
| ----- | -------- | -------- |
|   0   |   high   |   low    |
|   1   |   low    |   high   |
