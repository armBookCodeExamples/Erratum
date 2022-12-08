## Chapter 9 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### Table 9.1

In the table there is an extra blank space before PC_12, PC_10 and PC_11. This is just a typo and there is no reason for this blank space.

Also, the second column label should be "SD card module" instead of "SD card".

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

### Code 9.6

It can be argued that line 22:

> #define **SPI3_CS** PA_4_ALT0

Should have been defined as:

> #define **SPI3_SS** PA_4_ALT0

The rationale would be that the SPI signal is named "Subordinate Select" and not "Chip Select". However, very often the corresponding pin of the SD card module is labeled as "CS", so it makes sense to use SPI3_CS.

---

### Code 9.13

The corresponding explanation states:

> Then, the list of files in the directory is retrieved by means of *readdir()* on line 10 and stored in sdCardDirectoryEntryPointer.

However, this is not correct, becasue *readdir()* on line 10 retrieves a pointer to one file, not the complete list of files in the directory.

In more technical words:

> The *readdir()* function shall return a pointer to a structure representing the directory entry at the current position in the directory stream specified by the argument dirp, and position the directory stream at the next entry. It shall return a null pointer upon reaching the end of the directory stream.

---

Pending items to be considered in a future:

- "Cerrar algo"
- ¿por qué usamos SD y no usamos memoria no volatl?
- Agregar link a documentación de los tres ,h de mbed que usamos
- ver pines alternativos Code 9.6 en linea 22
- Quizas cambiar nombres en lineas 26 y 28 de Code 9.6
- Chequear si Code 9.4 es tal como lo muestro
- En el Warning de la pag 30 agregar posibilidad de que la SD está llena
- En Proposed Exercise del 9.2 retocar para corregir el código.
- Ver si cambio naranja por blanco en la Code 9.13
- Usar otro color para filesNamesBuffer en Code 9.13
- Revisar mejor Diapo 52 Code 9.17
- Ver correo "Notas sobre FAT32 - Max File size y Max Drive Size"
