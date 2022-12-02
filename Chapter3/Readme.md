## Chapter 3 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)
---

### Example 3.1 - Discussion of the Proposed Solution

In the step "Discussion of the Proposed Solution" of Example 3.1 it is stated:

> The proposed solution is based on the delay() function defined in the arm_book_lib.h library. This
function is based on the Mbed OS thread_sleep_for() function and pauses the execution of the program,
causing a delay

Although there is no error in doing it this way, this can be tackled in a simpler way by means of using the Mbed OS function *wait_ms()* [[Mbed OS Reference | wait_api functions](https://os.mbed.com/docs/mbed-os/v6.15/feature-i2c-doxy/group__platform__wait__api.html)]. At the time of writing the book we chosed not to use *wait_ms()* and decided to use an implementation based on *thread_sleep_for()* because we read in a forum that *wait_ms()* might be deprecated soon. However *wait_ms()* was never deprecated and now we regret not having used *wait_ms()* because that choice would have led to a more straightforward and simpler implementation.

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

### Caption of Code 3.18

The text should be:

> Implementation of the *main()* function.
