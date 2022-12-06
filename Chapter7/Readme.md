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
