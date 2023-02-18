## Chapter 4 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### New version of Chapter 4

After publishing the textbook some relevant improvements were made to Chapter 4, for example:

- It was decided to remove the buttons from the breadboard at once, instead of gradually removing them along the chapter. In this way the code becomes easier to understand.
- The explanation of Finite-states Machines (FSMs) diagrams was moved from the Under the Hood section to Example 4.1 and 4.2, to better explain the code of those examples.
- The debugging capability of the Keil Studio Cloud, included in Keil Studio Cloud after publishing the textbook, was explained in the Under the Hood section.

These changes among others are available on the [Chapter 4 - New Version.pdf](https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter4/Chapter-4-New-Version.pdf) file.

**It is strongly recommended to read this new version of Chapter 4 instead of reading the version available in the published textbook.**

The projects of the Examples of this new version are avaiable here:

- https://github.com/armBookCodeExamples/example_4-1-new/
- https://github.com/armBookCodeExamples/example_4-2-new/
- https://github.com/armBookCodeExamples/example_4-3-new/
- https://github.com/armBookCodeExamples/example_4-4-new/

---

### Table 4.2

The following text:

> lm35ReadingsArrayInit()

Should be added also in:

> Function inputsInit()

---

### Code 4.4

In Code 4.4 there is a bug. It can be seen by means of following the next steps:

1. Turn on the Alarm by pressing the button connected to D2.
2. Turn off the Alarm by pressing in the keypad "A", next "B" and by last "#".
3. Turn on the Alarm by pressing the button connected to D2.
4. Press only the key "#". The alarm will turn off, even though no code has been entered.
 
This issue will be fixed in a new version of this chapter to be published soon here.

---

### Code 4.8

In Code 4.8 there is a bug. It can be seen by means of following the next steps:

1. Turn on the Alarm by pressing the BUTTON1 button.
2. Turn off the Alarm by entering in the keypad “1”, “8”, “0”, “5”' and by last "#".
3. Turn on the Alarm by pressing the BUTTON1 button.
4. Press only the key "#". The alarm will turn off, even though no code has been entered.

This issue will be fixed in a new version of this chapter to be published soon here.

---

### Code 4.9

In the following section:

> case '5':
>     uartUsb.write( "Please enter the new four digits numeric code ", 46 );
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

Is missing to write the values of *receivedChar* into the array *codeSequence*. 
This issue will be fixed in a new version of this chapter to be published soon here.

---

### Figure 4.9

Over the arrow that goes from BUTTON_RISSING again into BUTTON_RISSING, where it says:

> accumulatedDebounceTime **>=** DEBOUNCE_BUTTON_TIME_MS

It should say:

> accumulatedDebounceTime **<** DEBOUNCE_BUTTON_TIME_MS

The same is valid for the arrow that goes from BUTTON_FALLING again into BUTTON_FALLING.

---

### Figure 4.10

Over the arrow that goes from MATRIX_KEYPAD_DEBOUNCE again into MATRIX_KEYPAD_DEBOUNCE, where it says:

> accumulatedDebounceMatrixKeyapadTime **>=** DEBOUNCE_BUTTON_TIME_MS

It should say:

> accumulatedDebounceMatrixKeyapadTime **<** DEBOUNCE_BUTTON_TIME_MS
