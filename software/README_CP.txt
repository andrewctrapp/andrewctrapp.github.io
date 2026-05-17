===
Instructions for using the code (hypertext links below have been tested on 9/12/2018). 
===

This project requires JRE 1.8.xxx or higher. If you don't have Java on your computer, first visit http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html to install Java. 

- The .zip file contains a standard Java project. It is complete except concerning the .jar of the Choco constraint programming solver. The choco-solver-3.3.3-with-dependencies.jar file (solver library) must be manually added to the project.

- The source code and data files are organized as follows:
1) The 'bench.gap' package contains the Java files related to the specific GAP benchmark.
The main is 'BenchPaper.java' (see the comments in file to run it).
2) GAP instances are stored in the 'gap' folder.
3) When the code is run, the results will be stored as text files in the 'res' folder.
4) The 'constraints' package contains the source of non standard constraints and propagators. 
5) The 'model' and 'onlinescheme' packages contain the – generic – diversity scheme (potentially usable on any constraint problem providing that appropriate quality notions are encoded).

===
Detailed example of use with the Eclipse IDE (Windows, OSX or Linux). 
===

1) Download and install eclipse:
https://www.eclipse.org/downloads/packages/release/oxygen/3a/eclipse-ide-java-developers

2) Download the two files: the .zip of the project and choco-solver-3.3.3-with-dependencies.jar 
Be sure to remember where they are located on your hard drive.

3) Run eclipse.
Click on File → import → General → Existing projects in your workspace → Next
A new window appears. Select the option 'Select archive file': Browse your hard drive and set the .zip file of the project. Click on 'Finish'

4) You should see the project on the left, with the red symbol '!' indicating that libraries is missing.
Place the mouse cursor on the project name, right click, and select 'Properties', then 'Java build path' and then 'Libraries'. 
There are one or two lines with a red cross. They mean that you need to indicate where are: 
- The JRE 1.8 folder. 
- The choco-solver-3.3.3-with-dependencies.jar file. 
For each one, click on 'Edit' to set the appropriate path on your hard drive (current paths correspond to the specific machine where the project was built). 

5) Click on OK. If the previous steps were correctly completed, there is no longer the red symbol '!'. You can run the project by opening the source file 'BenchPaper.java' in the 'bench.gap' folder and clicking on the green triangle. Remove/add comments in the code for selecting the instances you wish to run and the appropriate time limit (see the comments in the file). 

6) To visualize the results in the 'res' folder, select this folder on the left frame, right click and select 'Refresh'. You can now open the text files from Eclipse. 

