## Chapter 11 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### Section 11.2.2

In Example 11.2 it will be included the command "AT+CWJAP?" between "AT+CWMODE=1" and "AT+CWJAP".  
This command is used to determine if the ESP-01 had already automatically connected to a Wi-Fi network.  
This automatic connection may happen because the ESP-01 remembers the credentials to all the networks he used.  
Therefore, if the ESP-01 is already connected to the network, then it is not necessary to use the command AT+CWJAP".  
All this is explained here: [link](https://docs.google.com/presentation/d/1LC9KGRfBXfGQugeZ5rdJuvzB9CJMEDoq/edit?pli=1#slide=id.g2448787e015_0_32). By now, the explanation is in Spanish, but it can be translated into English using free tools, as Google Translator.

---

### Example 11.1

A diagram of the FSM that is implemented in this example is available here: [link](https://docs.google.com/presentation/d/1LC9KGRfBXfGQugeZ5rdJuvzB9CJMEDoq/edit?pli=1#slide=id.g2448787e015_0_780).

---

Pending items to be considered in a future:

- Example 11.1 primero dice 5 segundos y luego dice 10 segundos. Revisar: "Summary of the Expected Behavior" y "Test the Proposed Solution on the Board" la FSM?
- Code 11.6: pensar si la linea 18 es clara o si sería mejor crear y utilizar por ejemplo nonBlockingDelayInit()
- Code 11.10: linea 19 quizás sería mejor que la función se llame Show en lugar de Get
