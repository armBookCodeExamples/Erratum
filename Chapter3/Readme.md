## Chapter 3 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m-v3.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-on-cortex-m-v3.pdf)

---

### Example 3.1 - Discussion of the Proposed Solution

In the step "Discussion of the Proposed Solution" of Example 3.1 it is stated:

> The proposed solution is based on the delay() function defined in the arm_book_lib.h library. This
function is based on the Mbed OS thread_sleep_for() function and pauses the execution of the program,
causing a delay

Although there is no error in doing it this way, many times it leads to confusion, because for the sake of simplicity the topic of threads is not included in the book. Sometimes people ask why not tackle this delay in a simpler way by using the Mbed OS function *wait_ms()* [[Mbed OS Reference | wait_api functions](https://os.mbed.com/docs/mbed-os/v6.15/feature-i2c-doxy/group__platform__wait__api.html)]. The reason is that in the abovementioned Mbed OS Reference on wait_api functions it is stated:

> **Deprecated:**
> 'wait_ms' is deprecated in favor of explicit sleep functions. To sleep, 'wait_ms' should be replaced by 'ThisThread::sleep_for' (C++) or 'thread_sleep_for' (C). If you wish to wait (without sleeping), call 'wait_us'. 'wait_us' is safe to call from ISR context.

---

### Table 3.5

The following text:

> accumulatedTime

Should be replaced by:

> accumulatedTimeAlarm

---

### Table 3.16

The following text:

> #define NUMBER_OF_AVG_SAMPLES **10**

Should be replaced by:

> #define NUMBER_OF_AVG_SAMPLES **100**

And the text:

> NUMBER_OF_AVG_SAMPLES has been defined as **10**

Should be replaced by:

> NUMBER_OF_AVG_SAMPLES has been defined as **100**

Also, the following text should be removed from Table 3.16, because *lm35SampleIndex* is declared in *alarmActivationUpdate()* (see the errata regarding "Text before Code 3.11" below):

> int lm35SampleIndex = 0;

---

### Text before Code 3.11

The following text:

> In Code 3.11, the new implementation of *alarmActivationUpdate()* is shown, with the following
modified lines:
> - The lines regarding the potentiometer were all removed (lines 3 to 10 of Code 3.7).
> - Lines 6 to 17: the calculation of the temperature is implemented. The analog input is read and
stored in the current position of the *lm35ReadingsArray* on line 6. The index is incremented (line
7), and it is set to 0 if it is beyond the last position of the array (lines 8 and 9). Then, all the array
positions are summed (lines 12 to 15), the average value is computed (line 16), and the value of
lm35TempC is obtained (line 17).

Should be replaced by:

> In Code 3.11, the new implementation of *alarmActivationUpdate()* is shown, with the following
modified lines:
> - The lines regarding the potentiometer were all removed (lines 3 to 10 of Code 3.7).
> - **Lines 3 and 4: the variables *lm35SampleIndex* and *i* are declared and initialized. Notice that the reserved word *static* used on line 3 indicates that this variable retain its value between calls of *alarmActivationUpdate()*. This is the first time in this book where this reserved word is used.**
> - Lines 6 to 17: the calculation of the temperature is implemented. The analog input is read and
stored in the current position of the *lm35ReadingsArray* on line 6. The index is incremented (line
7), and it is set to 0 if it is beyond the last position of the array (lines 8 and 9). Then, all the array
positions are summed (lines 12 to 15), the average value is computed (line 16), and the value of
lm35TempC is obtained (line 17).

---

### New version of Example 3.5

In the original version of Example 3.5 the main reason for using a DigitalInOut object to control the sirenPin is because in this way it is not necessary to use a transistor to drive the buzzer. However, we noticed that many times it is not clear for the reader how the DigitalInOut object is used to control the buzzer. Moreover, it can be argued that the appropriate way to drive a 5 V buzzer with a 3.3 V GPIO pin is by means of a transistor. For this reason the following circuit can be used to drive the transistor, as discussed in Chapter 5, where Figure 5.6 is introduced:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter3/Figure5-6.png" width="600">

In the circuit shown in Figure 5.6, the buzzer is turned on when 3.3 V is asserted in PE_10 and is turned off when 0 V is asserted in PE_10. As a consequence, the code should be modified if this circuit is used. The modified code is available here:

- https://github.com/armBookCodeExamples/example_3-5-new/

The changes made to the main.cpp file are as follows:

1. The following declaration:

> DigitalInOut sirenPin(PE_10);

Was replaced by:

> DigitalOut sirenPin(PE_10);

2. The following lines in inputsInit():

> sirenPin.mode(OpenDrain);
> sirenPin.input();

Were replaced by:

> sirenPin = LOW;

3. The following lines in alarmActivationUpdate():

> sirenPin.output();                                     
> sirenPin = LOW; 

Were replaced by:

> sirenPin = HIGH;

4. The following line in alarmActivationUpdate():

> sirenPin.input();                                     

Was replaced by:

> sirenPin = LOW; 
 
In this way:
- 1. Is used to declare sirenPin as a DigitalOut object
- 2. Is used to initialize sirenPin as LOW, so the buzzer is turned off.
- 3. Is used to set sirenPin to HIGH, so the buzzer is turned on.
- 4. Is used to set sirenPin to LOW, so the buzzer is turned off.

---

### Caption of Code 3.18

The text should be:

> Implementation of the *main()* function.
