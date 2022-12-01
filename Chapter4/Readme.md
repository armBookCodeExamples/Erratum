## Chapter 4 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### Table 4.2

The following text:

> lm35ReadingsArrayInit()

Should be added also in:

> Function inputsInit()

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
