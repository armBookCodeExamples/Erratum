## Chapter 5 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m-v3.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-on-cortex-m-v3.pdf)

---

### Table 5.3 to Table 5.13

In the text before Table 5.3 it is stated

> It is important to note that in Tables 5.2 to 5.13, there is a bold line to separate functions that are
called by other modules from functions that are used only within the module itself.

However, this bold line is missing in the tables. This bold line should be for example as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter5/Table%205-3.png" width="600">

---

### Caption of Table 5.7 and Table 5.12

Instead of:

> "Main functionality of"

The text should be:

> "Functions of"

---

### Code 5.8

In line 13 the word "codeMatch" should be in blue color.

---

### Code 5.9

In line 21 the word "false" should be in green color.

---

### Code 5.13

The following line in *fireAlarmInit()* is not strictly necessary:

> alarmTestButton.mode(PullDown); 

as the Alarm Test Button is implemented by means of the B1 User button, and this button is already connected to an external pull-down resistor placed in the NUCLEO board, as explained in Example 1.3.

---

### Code 5.19: FSM implemented in pcSerialComUpdate()

It might be useful to illustrate the FSM that is implemented by means of *pcSerialComUpdate()* and some other functions in the *pc_serial_com* module:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter5/FSM%20Figure%20Code%205-19.jpg" width="500">

---

### Code 5.19: Implementation of pcSerialComStringWrite()

It can be argued that the implementation of the function *pcSerialComStringWrite()* is prone to unexpected behaviors. This is due to the fact that *pcSerialComStringWrite()* is a public function and given its implementation any other module that uses this function might write any message in the serial monitor without any control of the pcSerialCom module. In this way these messages might interfere with other messages that are written in the serial monitor, leading to messages coming from different modules to be printed in an unexpected order in the serial monitor, resulting in a confusing set of messages for the user.

On the other hand, this implementation of *pcSerialComStringWrite()* noticeably simplifies the implementation of the pcSerialCom module and the usage of this function in particular. For this reason this implementation is not considered an error, but a simplification.

In chapter 12 it is shown how to implement public functions in such a way that they do not directly interfere with the resources that are the responsibility of other modules (as it is in this case), but request the corresponding modules to implement some actions over those resources, delegating those modules the responsibility of handling those request properly.

---

### Figure 5.8

It can be argued that for the sake of scalability it might be better to organize the files as shown in the following new version of Figure 5.8:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter5/New%20Figure%205-8.jpg" width="700">

This alternative organization proposed for the smart home system code is available [here](https://github.com/alutenberg/subsection_5-4-2)

**Note**: This alternative organization works exactly the same way as the original organization, because Keil Studio Cloud do not care about folders organization.

---
