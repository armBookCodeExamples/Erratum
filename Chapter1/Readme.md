## Chapter 1 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-v2.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-v2.pdf)

---

### 1.2.3 Getting Ready to Program the First Implementation of the Smart Home System

Due to Keil Studio Cloud change from "Import Project" to "Clone" that was made after the textbook was published, the following text:

> First, the reader must copy the URL of the repository of the “Subsection 1.2.3” program that is available in [10]. Then, in the “File” menu of Keil Studio Cloud, select **“Import project”**. **The “Import project” window will be displayed in the web browser. Press “Add project” without modifying any of the configurations,** and a new project named “Subsection 1.2.3” will be added to the list of available projects as the active project.

Should be replaced by:

> First, the reader must copy the URL of the repository of the “Subsection 1.2.3” program that is available in [10]. Then, in the “File” menu of Keil Studio Cloud, select **“Clone”**. **The “Clone” window will be displayed in the web browser. Paste the URL of the repository of the “Subsection 1.2.3” program in the "URL" field, enter the name “subsection_1-2-3” in the "Project name" field, select "Make this the active project" and press “Add project”,** and a new project named “Subsection 1.2.3” will be added to the list of available projects as the active project.

---

### Comment regarding Code 1.1

It is worthy to mention that line 15 of Code 1.1:

> **15**  if ( gasDetector == ON ) {

Is the same as:

> **15**  if ( gasDetector.read() == true ) {

And it is also the same as:

> **15**  if ( gasDetector.read() ) {

And it is also the same as:

> **15**  if ( gasDetector ) {

---

### Code 1.2

There is an else missing on line 18. The code should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Code1-2.png" width="500">

---
