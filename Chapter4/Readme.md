## Chapter 4 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### New version of Chapter 4

After publishing the textbook some relevant improvements were made to Chapter 4, for example:

- It was decided to remove the buttons from the breadboard at once, instead of gradually removing them along the chapter. In this way the code becomes easier to understand.
- The explanation of Finite-states Machines (FSMs) diagrams was moved from the Under the Hood section to Example 4.1 and 4.2, to better explain the code of those examples.
- The debugging capability of the Keil Studio Cloud, included in Keil Studio Cloud after publishing the textbook, was explained in the Under the Hood section.

These changes among others are available on the [Chapter 4 - New Version.pdf](https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter4/Chapter-4-New-Version.pdf) file.

**It is strongly recommended to read this new version of Chapter 4 instead of reading the version available in the published textbook.**

The projects of the Examples of this new version are available here:

- https://github.com/armBookCodeExamples/example_4-1-new/
- https://github.com/armBookCodeExamples/example_4-2-new/
- https://github.com/armBookCodeExamples/example_4-3-new/
- https://github.com/armBookCodeExamples/example_4-4-new/


---

### 4.2.2 Test the Operation of the Matrix Keypad and RTC

When following this instruction: 

> Press the “s” key and follow the instructions to set the current date and time for the RTC.

You may find that in the Keil Studio Cloud serial monitor, two characters will be echoed rather than one, as expected. For example, to set the year, you may type “2024” but find the serial monitor prints “22002244”, as shown below:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter4/Erratum_section422.png" width="45%">

This does not affect the process of setting the RTC, and the correct year (2024) will be stored. 

---

### Table 4.2

The following text:

> lm35ReadingsArrayInit()

Should be added also in:

> Function inputsInit()

This issue is fixed in the new version of this chapter that is now available (see above).

---

### Table 4.3

The following text:

> typedef enum {
> 
> BUTTON_UP
> 
> BUTTON_FALLING
> 
> BUTTON_DOWN
> 
> BUTTON_RISING
> 
> } buttonState_t;

Should be:

> typedef enum {
> 
> BUTTON_UP,
> 
> BUTTON_FALLING,
> 
> BUTTON_DOWN,
> 
> BUTTON_RISING
> 
> } buttonState_t;

---

### Code 4.3

There are some inconsistencies between Code 4.3 and Figure 4.6, Figure 4.8 and Figure 4.9. The new version of Chapter 4 that is now available (see above) is free of this inconsistencies. 

---

### Code 4.4

In Code 4.4 there is a bug. It can be seen by means of following the next steps:

1. Turn on the Alarm by pressing the button connected to D2.
2. Turn off the Alarm by pressing in the keypad "A", next "B" and by last "#".
3. Turn on the Alarm by pressing the button connected to D2.
4. Press only the key "#". The alarm will turn off, even though no code has been entered.
 
This issue is fixed in the new version of this chapter that is now available (see above).

---

### Code 4.8

In Code 4.8 there is a bug. It can be seen by means of following the next steps:

1. Turn on the Alarm by pressing the BUTTON1 button.
2. Turn off the Alarm by entering in the keypad “1”, “8”, “0”, “5”' and by last "#".
3. Turn on the Alarm by pressing the BUTTON1 button.
4. Press only the key "#". The alarm will turn off, even though no code has been entered.

This issue is fixed in the new version of this chapter that is now available (see above).

---

### Code 4.9

In the following section:

> case '5':
> 
>     uartUsb.write( "Please enter the new four digits numeric code ", 46 );
>     
>     uartUsb.write( "to deactivate the alarm: ", 25 );
>     
>     for ( keyBeingCompared = 0;
>           keyBeingCompared < NUMBER_OF_KEYS;
>           keyBeingCompared++) {
>         uartUsb.read( &receivedChar, 1 );
>         uartUsb.write( "*", 1 );
>     }
>     uartUsb.write( "\r\nNew code generated\r\n\r\n", 24 );
>     break;

Is missing code to write the values of *receivedChar* into the array *codeSequence*. 
This issue is fixed in the new version of this chapter that is now available (see above).

---

### Example 4.4

The following text:

> The smart home system should store up to 20 events, 

Should be:

> The smart home system should store up to **100** events, 

---

### Figure 4.9

Over the arrow that goes from BUTTON_RISSING again into BUTTON_RISSING, where it says:

> accumulatedDebounceTime **>=** DEBOUNCE_BUTTON_TIME_MS

It should say:

> accumulatedDebounceTime **<** DEBOUNCE_BUTTON_TIME_MS

The same is valid for the arrow that goes from BUTTON_FALLING again into BUTTON_FALLING.
This issue is fixed in the new version of this chapter that is now available (see above).

---

### Figure 4.10

Over the arrow that goes from MATRIX_KEYPAD_DEBOUNCE again into MATRIX_KEYPAD_DEBOUNCE, where it says:

> accumulatedDebounceMatrixKeyapadTime **>=** DEBOUNCE_BUTTON_TIME_MS

It should say:

> accumulatedDebounceMatrixKeyapadTime **<** DEBOUNCE_BUTTON_TIME_MS

This issue is fixed in the new version of this chapter that is now available (see above).

---

### 4.4 Case study

There is a delay missing in Code 4.22. There should be a delay as in Code 4.14 (i.e. delay(TIME_INCREMENT_MS);) so the debounce can be properly implemented.
