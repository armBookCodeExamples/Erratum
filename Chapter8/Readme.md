## Chapter 8 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m-v3.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-on-cortex-m-v3.pdf)

---

### Figure 8.5

We noticed that some readers get confused about the following note about Figure 8.5:

> NOTE: In Figure 8.5 it can be seen that PB_4, PA_0, and PD_12 are associated with
PWM3/1, PWM2/1, and PWM4/1, respectively, which means PWM timer 3/channel
1, PWM timer 2/channel 1, and PWM timer 4/channel 1. By connecting each LED to a
different PWM timer, it is possible to control their intensities independently, as will be
shown in the examples below

The four lines in Figure 8.5 do not indicate PB_4, PA_0, and PD_12 but the correspondence of CN7, CN8, CN9 and CN10.

---
