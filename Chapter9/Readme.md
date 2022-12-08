## Chapter 9 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### Table 9.1

In the table there is an extra blank space before PC_12, PC_10 and PC_11. This is just a typo and there is no reason for this blank space.

---

### Example 9.1 - Objective

The following text:

> Introduce the usage of filesystems and repositories.

Should be replaced by:

> Introduce the usage of filesystems.

---

### Code 9.4

It is pending for revision if it is okay to have included line 24 in the for loop:

> eventsStored = true;

This implementation does imply an error, but *eventsStored* is assigned *true* many times, what might be considered suboptimal.

---
