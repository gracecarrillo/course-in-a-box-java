---
title: Setting Up Java
---

## What you need for this Crash Course:

For this Crash Course you don't need to install Java. We will use an online resource for running our programs. This is because installing Java takes time and we don't have much. 

We will use an online compiler you can find here: https://www.compilejava.net/

## Setting up the Java Environment

For performing the examples discussed in this tutorial in your own computer, you will need the following:

  - Linux 7.1 or Windows xp/7/8 operating system
  - Java JDK 8
  - Microsoft Notepad or any other text editor.

Java SE is freely available from the link [Download Java](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html). You can download the appropriate version based on your operating system.

Follow the instructions to download Java and run the *.exe* to install Java on your machine. Once you installed Java on your machine, you will need to set environment variables to point to correct installation directories.

### Setting Up the Path for Windows

Assuming you have installed Java in c:\Program Files\java\jdk directory: 

  - Right-click on 'My Computer' and select 'Properties'.
  - Click the 'Environment variables' button under the 'Advanced' tab.
  - Now, alter the 'Path' variable so that it also contains the path to the Java executable. Example, if the path is currently set to 'C:\WINDOWS\SYSTEM32', then change your path to read 'C:\WINDOWS\SYSTEM32;c:\Program Files\java\jdk\bin'.

**Note: Java is continually being improved. For the latest information on system requirements and installation instructions, see the [Java download page](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html).**

### Setting Up the Path for Linux, UNIX, Solaris, FreeBSD

- Environment variable PATH should be set to point to where the Java binaries have been installed. Refer to your shell documentation, if you have trouble doing this.

- Example, if you use bash as your shell, then you would add the following line to the end of your *'.bashrc: export PATH = /path/to/java:$PATH'*.

### Popular Java Editors

To write your Java programs, you will need a text editor. There are even more sophisticated IDEs available in the market. But for now, you can consider one of the following:

  - Notepad − On Windows machine, you can use any simple text editor like Notepad or TextPad.
  - Netbeans − A Java IDE that is open-source and free which can be downloaded from https://www.netbeans.org/index.html.
  - Eclipse − A Java IDE developed by the eclipse open-source community and can be downloaded from https://www.eclipse.org/.

**Troubleshooting: If you run into problems with your installation, see the [Java Troubleshoot.](https://www.java.com/es/download/help/troubleshoot_java.xml)**
