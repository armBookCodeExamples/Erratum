xº## Chapter 7 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

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

### Example 7.3

The objective might be changed from:

> Introduce the reading of a PIR sensor using interrupts.

To:

> Introduce the reading of a PIR sensor using interrupts, configure different interrupts associated with the same signal, disable an interrupt service routine using program code.

---

### Code 7.18

Code 7.18 is already explained using Figure 7.11 and the text in pages 322 to 324, however a more detailed explanation will be included here soon.

---

### New version of Example 7.3

A new version of Example 7.3 is discussed here: [link](https://docs.google.com/presentation/d/14SRO7-GlrJdRlLTLZZcAXJT6EmPXtnlv/edit?pli=1#slide=id.g22e61df9a0a_1_473) and here: [link](https://docs.google.com/document/d/1K_GC4ALW6MTrbxhSVuZYqWkZdckkFsQCgjwE_RUhK2Q/edit?usp=sharing)

By now, the explanation is in Spanish, but it can be translated into English using free tools, as Google Translator.

The corresponding code is available in this repository: [link](https://github.com/alutenberg/example_7-3)

We consider it to be very convenient to use this new version of the example in any course based on the book. 

---

### Code 7.32

An image is missing of the "Intruder Detected" screen. It is shown here for reference:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter7/Figure%207-xx%20-%20Intruder%20detected%20bmp%20text.png" width="400">

---

### Intruder detected image improved

An improved image of the "Intruder Detected" screen can be obtained using the following file: <a href="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter7/IntruderDetectedScreenImproved.h">IntruderDetectedScreenImproved.h</a>

It is shown here for reference:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter7/Figure%207-xx%20-%20Intruder%20detected%20bmp%20picture.png" width="400">

---

### Table 7.24

The following line

> #include "GLCD_clear_screen.h"

Is not correct (should be removed from the table), because the variable *uint8_t GLCD_ClearScreen[1024]* is defined in *modules/display/GLCD_fire_alarm.h*

---
