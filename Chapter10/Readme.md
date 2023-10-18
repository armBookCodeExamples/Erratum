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

Pending items to be considered in a future:
- Code 10.14: resaltar que debo inicializar el ticker.
- Code 10.14: resaltar que puede haber varias nonBlockingDelayInit() asociadas a una sola tickInit()
- Code 10.17: Mostrar cálculo de cuánto es el máximo de uint64_t si contamos cada 1 ms.
- Code 10.17: Comentar que  poner directamente uint64t en lugar de tick_t podría ser una opción.
- Code 10.16: mencionar que nonBlockingDelayWrite() se podría borrar, pero se usa en el Chapter 11.
- Code 10.16: Explicar que puede haber varias nonBlockingDelayRead()
- Code 10.16: Explicar que nonBlockingDelayRead() también lo arranca; eso quizás se podría hacer en nonBlockingDelayStart()
- Code 10.18: en lugar de durationMs para ser consistente debería/podría ser durationValue
