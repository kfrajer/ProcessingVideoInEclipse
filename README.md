# ProcessingVideoInEclipse
Step by Step Guide: Running Processing's Video Library in Eclipse Mars2

As a reference: https://processing.org/tutorials/eclipse/ but not to helpful here. 

I have Win10 64bit, P3.3.4 64bit and Eclipse Mars 2.0
This is what I did. Open the example video>>Capture>>BrightnessTracking

Run the sketch. It works for me. I get some warnings related to the GStreamer-CRITICAL... Notice you will get those warnings on the other side.

Now I did this: I exported the library and I didn't check the 64 bit part[STEP1.png]. This step will produce two folders. Check **Export_BrightnessTracking_folderTree.docx**

![step1](https://forum.processing.org/two/uploads/imageupload/801/FIW82I4LBZ7T.png "step1")

This will create two folders,one for the 32 and another for the 64 bit version. In my machine, I tried running the 32 version and it didn't execute as I didn't get any video. On the other hand, the executable in the 64 but folder worked [!!!]. So I will be using these files in the rest of the steps. 

Now open eclipse and create a new Java Project which I named *briBriBri* (For a better name) [STEP2]:

![step2](https://forum.processing.org/two/uploads/imageupload/630/RP1304M4XZ2F.png "step2")

In this new project, add a new class called <u>BrightnessTracking</u> [STEP3].No need to add main as it will be replaced in the next step.

![step3](https://forum.processing.org/two/uploads/imageupload/197/G2W74UX6FCWQ.png "step3")

Now, go back to the 64 bit export folder and search for the BrightnessTracking.java file. Open it with a text editor (or Processing) and copy the entire content and paste it in this new generated class. Make sure you preserve the first line of the class, the o one that makes reference to the name of your project's package. In my case: `package briBriBri;`

[STEP4] shows all those red lines... let's fix that.

![step4](https://forum.processing.org/two/uploads/imageupload/030/KBZ21YLZ14PQ.png "step4")

[STEP5 and STEP6] Right click on your project and click on import, then on the dialog box click **File System**:

![step5](https://forum.processing.org/two/uploads/imageupload/199/2PGF44OEENNB.png "step5")

![step6](https://forum.processing.org/two/uploads/imageupload/459/J6CF28KI3BIK.png "step6")

In [STEP7] search for the location of the exported files that you get from step1. I decided to use library>>video>capture>BrigghtnessTracking>>application.windows64>>lib for reasons I commented above. Notice there is also a folder called plugins inside the lib folder. ![step7](https://forum.processing.org/two/uploads/imageupload/385/UZVQDRCQSODW.png "step7") 

Then you are back on the previous dialog box Title Import and Importing: File System. It will populated with <u>jar</u> and <u>dll</u> files on the right box. [STEP8] Click **select all**: 
![step8](https://forum.processing.org/two/uploads/imageupload/159/RTYH5WTV7UTS.png "step8")

Now, select all the jar files. Notice there is the **video.jar** file at the end of the list (It is not shown in the screen shot). Right click on the selection then select *Build Path>> Add To Build Path* [STEP9]

Step10 shows when I try running the code. Choose **Java Applet** and hit run.

![step10](https://forum.processing.org/two/uploads/imageupload/308/EI1X0MEY6MAV.png "step10")


Notice I got a warning shown in STEP11.png: ""Selection does not contain an Applet". Dismiss it:

![step11](https://forum.processing.org/two/uploads/imageupload/952/JP5QOMYNTZQD.png "step11")

Now you will get a bunch of warnings and the sketch should run. If it does not work, then go to *Build >> Clean* in the Eclipse's menu and try running again.

I attached an extra file showing the structure of the files and folders in the briBriBri project after i get everything running. The name of the file is **Export_BrightnessTracking_folderTree.docx**

I hope it works. 

Kf
