## Chapter 1 Erratum

The following comments refer to the file [arm-designing-embedded-system-application-on-cortex-m.pdf](https://armkeil.blob.core.windows.net/developer/Files/pdf/ebook/arm-designing-embedded-system-application-cortex-m.pdf)

---

### 1.2.3 Getting Ready to Program the First Implementation of the Smart Home System

Some USB cables are able to supply power but not data link, while other USB cables can provide both. The NUCLEO board indicates whether the USB cable is appropriate to be used to load the program onto the board or not, as shown in these videos: 

<div align="left">
      <a href="https://www.youtube.com/watch?v=3_Q2ejlwJ04">
         <img src="https://img.youtube.com/vi/3_Q2ejlwJ04/0.jpg" style="width:25%;">
      </a>
</div>

Video credits: María Carina Roldán.

<div align="left">
      <a href="https://www.youtube.com/watch?v=kiywIUJCdq0">
           <img src="https://img.youtube.com/vi/kiywIUJCdq0/0.jpg" style="width:25%;">
      </a>
</div>

Video credits: María Carina Roldán.

---

### 1.2.3 Getting Ready to Program the First Implementation of the Smart Home System

Due to Keil Studio Cloud change from "Import Project" to "Clone" that was made after the textbook was published, the following text:

> First, the reader must copy the URL of the repository of the “Subsection 1.2.3” program that is available in [10]. Then, in the “File” menu of Keil Studio Cloud, select **“Import project”**. **The “Import project” window will be displayed in the web browser. Press “Add project” without modifying any of the configurations,** and a new project named “Subsection 1.2.3” will be added to the list of available projects as the active project.

Should be replaced by:

> First, the reader must copy the URL of the repository of the “Subsection 1.2.3” program that is available in [10]. Then, in the “File” menu of Keil Studio Cloud, select **“Clone”**. **The “Clone” window will be displayed in the web browser. Paste the URL of the repository of the “Subsection 1.2.3” program in the "URL" field, enter the name “subsection_1-2-3” in the "Project name" field, select "Make this the active project" and press “Add project”,** and a new project named “Subsection 1.2.3” will be added to the list of available projects as the active project.

---

### 1.2.3 Getting Ready to Program the First Implementation of the Smart Home System

In order to be able to save the changes you made to programs in Keil Studio Cloud you should have a [Github](https://github.com/) account and follow these steps:

##### 1) Open in the [Directory](https://github.com/armBookCodeExamples/Directory/blob/main/README.md) the repository of the example you want to work with and select "Create a new fork".
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step1.jpg" width="50%">

##### 2) Write a description and click on "Create fork" button.
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step2.jpg" width="50%">

##### 3) You will see the fork on your Github account.
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step3.jpg" width="50%">

##### 4) Clone your fork in Keil Studio Cloud by copying the URL from your repository.
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step4.jpg" width="50%">

##### 5) When you are ready to save the changes, select "Stage All Changes".
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step5.jpg" width="30%">

##### 6) Next, select commit and enter a description message.
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step6.jpg" width="30%">

##### 7) Next, select commit again to commit the changes to your repository.
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step7.jpg" width="30%">

##### 8) Finally, push the changes to your repository.
<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Step8.jpg" width="45%">


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

In the textbook there is an else missing on line 18. The code should be as follows:

<img src="https://github.com/armBookCodeExamples/Erratum/blob/main/Chapter1/Code1-2.png" width="600">

---
