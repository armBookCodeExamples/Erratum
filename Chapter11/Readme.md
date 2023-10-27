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

### Caption of Figure 11.18

The text should be:

> The ESP-01 module indicates that 52 bytes were received correctly

---

### Example 11.1

A diagram of the FSM that is implemented in this example is available here: [link](https://docs.google.com/presentation/d/1LC9KGRfBXfGQugeZ5rdJuvzB9CJMEDoq/edit?pli=1#slide=id.g2448787e015_0_780).

---

### Example 11.1

In "Summary of the Expected Behavior" it says:

> If this message is not received within 10 seconds, then “AT command not responded correctly” will be shown on the serial terminal.  

In "Test the Proposed Solution on the Board" it says:

> the message “AT command responded correctly” should appear on the serial terminal after 10 seconds.  

It can be seen here that the delay in the program code is 5 seconds: [link](https://github.com/armBookCodeExamples/example_11-1/blob/7226b7a6dedb30e0005e58f9a75d071126c04d39/modules/wifi_com/wifi_com.cpp#L12).

---

### Example 11.1

It is important to mention that messages as "AT" and "OK", as shown in Figure 11.7, are not printed in the serial terminal anymore. 

---

### Example 11.1

In the initialization of the non blocking delay in Code 11.6 it is used the function *nonBlockingDelayWrite()* in line 18, line 26 and line 33. The code might be clearer if this function is renamed in such a way that its role becomes easier to understand.

---

### Example 11.2

It is important to explain the "Summary of the Expected Behavior" for each of the available commands:

> With the 'd' command you will be able to configure the Wi-Fi SSID  
> With the 'r' command you will be able to configure the Wi-Fi pass  
> With the command 'a' we will try to get an IP for the ESP-01  
>  If 'a' is not pressed, wifiComUpdate() executes the same  
> With the 'p' command you will obtain the IP assigned to ESP-01  

---

### Code 11.10

In line 19 it might be better to call this function *commandShowWifiComAssignedIp()* instead of *commandGetWifiComAssignedIp()*.

---


