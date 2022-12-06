## Chapter 7 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### Caption of Figure 7.1

Instead of:

> "Figure 7.1 The smart home system is now connected to an LCD display"

The text should be:

> "Figure 7.1 The smart home system is now connected to a PIR sensor, a motor, four buttons and two LEDs"

---

### Code 7.3 - FSM

It would have been nice to include in the book the following diagram to illustrate the FSM implemented in Code 7.3:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter7/FSM%20Code%207-3.png" width="600">

---

### Example 7.2 - FSM

It would have been nice to include in the book the following diagram to illustrate the FSM implemented in Example 7.2:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter7/FSM%20Code%207-12.png" width="600">

Notice that this FSM is implemented from Code 7.9 to Code 7.12. Also notice that *gateOpenButton* and *gateCloseButton* belong to the *user_interface* module, while *gateOpenLimitSwitch* and *gateCloseLimitSwitch* belong to the *gate* module.

---

### Code 7.18

Code 7.18 is already explained using Figure 7.11 and the text in pages 322 to 324, however a more detailed explanation will be included here soon.

---

### Code 7.32

An image is missing of "Intruder Detected". It will be soon added here. (internal reference: page 72)

---

### Table 7.24

The following line

> #include "GLCD_clear_screen.h"

Is not correct, because the variable *uint8_t GLCD_ClearScreen[1024]* is defined in *modules/display/GLCD_fire_alarm.h*

---
