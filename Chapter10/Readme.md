## Chapter 10 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### Caption of Code 10.2

The text should be:

> Details of the implementation of the file ble_com.cpp.

---

### Caption of Code 10.10

The text should be:

> Details of the implementation of eventLogUpdate().

---

### Example 10.4 - Implementation of the Proposed Solution

Given the new version of Example 8.1, the text:

> This function is based on a ticker, in a very similar way to the brightControlInit() function that was introduced in Example 8.1, as discussed below. 

Should be:

> This function is based on a ticker, in a very similar as in Example 8.1, as discussed below. 

---

### Table 10.10

This declaration:

> static nonBlockingDelay_t smartHomeSystemDelay;

Should not be in the section *"Declaration and initialization of public global objects"*, but in the section *"Declaration and initialization of private global objects"*, because *nonBlockingDelay_t* is not an object, but a user defined data type, and this variable is declared as private by means of the reserved word *static*. 

---

### Code 10.15

On line 7 it is declared:

> static Ticker ticker;

This line should not be in the section *"Declaration and initialization of private global variables"*, but in a section *"Declaration and initialization of private global objects"*, because Ticker is not a data type, but an object class, and it is declared as private by means of the reserved word *static*. 

---

### Code 10.15

The declaration of the public data type *tick_t* used in line 8 in the declaration of the variable *tickCounter* is introduced in Code 10.17 as:

> typedef uint64_t tick_t;

The usage of uint64_t allows to account for 18446744073709551616 ms, what is equivalent to 584942417 years.  

---

### Code 10.16

The function nonBlockingDelayWrite() is not used in Chapter 10, but it is used many times in Chapter 11.

Notice there can be many instances of nonBlockingDelayRead(), each associated to different variables of type nonBlockingDelay_t.

Also notice that nonBlockingDelayRead() starts the counting of the delay (line 21).

---

### Code 10.18

It would be better to name "durationMs" as "durationValue", to be consistent with the naming used in the previous codes.

---
