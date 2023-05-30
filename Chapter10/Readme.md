## Chapter 10 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### Caption of Code 10.2

The text should be:

> Details of the implementation of the file ble_com.cpp.

---

Pending items to be considered in a future:
- Code 10.5: revisar si efectivamente en la línea 6 corresponde "Garantiza que pasen al menos 10 ms entre mensajes (recordar que va a 9600 bps)" - revisar pag 23
- Code 10.8: comentar posible error de seguridad en usar strcpy en lugar de strncpy.
- Code 10.8: Mencionar que en las línea 18 state!=lastState podría ser una opción.
- Code 10.10: Caption no es ble_com.h sino eventLogUpdate
- Code 10.14: resaltar que debo inicializar el ticker.
- Code 10.14: resaltar que puede haber varias nonBlockingDelayInit() asociadas a una sola tickInit()
- Code 10.17: Mostrar cálculo de cuánto es el máximo de uint64_t si contamos cada 1 ms.
- Code 10.17: Comentar que  poner directamente uint64t en lugar de tick_t podría ser una opción.
- Code 10.16: mencionar que nonBlockingDelayWrite() se podría borrar, pero se usa en el Chapter 11.
- Code 10.16: Explicar que puede haber varias nonBlockingDelayRead()
- Code 10.16: Explicar que nonBlockingDelayRead() también lo arranca; eso quizás se podría hacer en nonBlockingDelayStart()
- Code 10.18: en lugar de durationMs para ser consistente debería/podría ser durationValue
