## Chapter 3 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### Text before Code 3.11

The following text:

> In Code 3.11, the new implementation of alarmActivationUpdate() is shown, with the following
modified lines:
> - The lines regarding the potentiometer were all removed (lines 3 to 10 of Code 3.7).
> - Lines 6 to 17: the calculation of the temperature is implemented. The analog input is read and
stored in the current position of the lm35ReadingsArray on line 6. The index is incremented (line
7), and it is set to 0 if it is beyond the last position of the array (lines 8 and 9). Then, all the array
positions are summed (lines 12 to 15), the average value is computed (line 16), and the value of
lm35TempC is obtained (line 17).

Should be replaced by:

> In Code 3.11, the new implementation of alarmActivationUpdate() is shown, with the following
modified lines:
> - The lines regarding the potentiometer were all removed (lines 3 to 10 of Code 3.7).
> - **Lines 3 and 4: the variables *lm35SampleIndex* and *i* are declared and initialized. Notice that the reserved word *static* indicates**
> - Variables declared as static inside a function (as in Code 5.29 and Table 6.14) are local variables that retain their values as explained,
> - Lines 6 to 17: the calculation of the temperature is implemented. The analog input is read and
stored in the current position of the lm35ReadingsArray on line 6. The index is incremented (line
7), and it is set to 0 if it is beyond the last position of the array (lines 8 and 9). Then, all the array
positions are summed (lines 12 to 15), the average value is computed (line 16), and the value of
lm35TempC is obtained (line 17).

---

### Text after Code 3.11

The following note:

> "This issue lasts for only one second and is addressed in the Proposed Exercise of this example."

Should be replaced by:

> "This issue lasts for only 0,1 second and is addressed in the Proposed Exercise of this example."

---

### Caption of Code 3.18

The text should be:

> Implementation of the main() function.

---

### Table 3.5

The following text:

> accumulatedTime

Should be replaced by:

> accumulatedTimeAlarm

---

### Table 3.16

The following text:

> int lm35SampleIndex = 0;

Should be removed, because this variable is declared in *alarmActivationUpdate()*
