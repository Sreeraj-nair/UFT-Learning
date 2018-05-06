# UFT-Learning

UFT Checkpoints - Have very limited or no use in UFT. 

Most of the times we use VBScript features instead of Checkpoints. 

What is Checkpoint? 
It is a verification point, takes expected Result from the user, compares with the actual result during execution 
and provides Test Result. 

Types of Checkpoints 
1) Standard Checkpoint - 
It checks object properties values. 
Eg. Object is button, if you want to checked Enabled property of button
Eg. Object is Edit box, if property is text, Check whether value is "John" or not. 
-----------------------------

2) Text Checkpoint - 
It checks text value of an object in different ways. 
It is specialized checkpoint for checking text, exact match, match case, ignore space etc options are available. 
-----------------------------

3) Text Area Checkpoint - 
It checks text area present in the application in different ways. 
-----------------------------

4) Bitmap Checkpoint -
It compares two bitmaps. What is Bitmap - Bitmap is made of pixels and no functionality like digital signature etc. 
Corresponds to one or more bits of information, eg the information used to control the display of a computer screen. 
 
Image is different. 
-----------------------------

5) Database Checkpoint  - 
It checks the content of the database cell-wise. 
-----------------------------

6) Accessibility Checkpoint - 
It checks whether the web page was developed using W3 Standards or not. Accessbility testing. 
-----------------------------

7) XML Checkpoint (from Application) - 
It checks content of the XML page. 
-----------------------------

8) XML Checkpoint (from resource) - 
It checks content of the XML file. 
-----------------------------

9) File Content Checkpoint - 
It is not available in QTP, available only in UFT. 
It checks content of a flat file, eg a text file. 
-----------------------------

10) Page Checkpoint - 
It checks number of links, and number of images present on a web page. 
-----------------------------

11) Image Checkpoint - 
It checks Image object property values. 
-----------------------------

12) Table Checkpoint - 
It checks the content of a web table cell-wise. 
-----------------------------

Note: 
i) Non Record Mode - Database Checkpoint, XML Checkpoint from Resource, and File Content Checkpoints are back-end Checkpoints. No recording more is required. 
Go to Design > Checkpoint > 1) Database Checkpoint, 2) XML Checkpoint (From Resource), and  3) File Content Checkpoint are available. 

ii) Select Record Mode - 
Go to Design > Checkpoint > 1) Standard Checkpoint, 2) Text Checkpoint, 3) Text Area Checkpoint, 4) Bitmap Checkpoint, 5) Database Checkpoint, 
6) Accessibility Checkpoint, 7) XML Checkpoint (From Application), 8) XML Checkpoint (From Resource), 9) File Content Checkpoint. 

iii) Page, Image and Table Checkpoints, are hidden checkpoints. These checkpoints are inserted using Standard Checkpoints. 

iv) We can insert multiple Checkpoints. 

v) We can Insert or Create, Edit and Delete Checkpoints. 

How to Insert Checkpoints -
1) Standard Checkpoint - 

VB Scripting - 

Dim Before, After
SystemUtil.Run "C:\Program Files\HP... exe"
Before = WpfWindow("HP MyFlight Sample Application").WpfButton("OK").GetROProperty("enabled")

If Before = False Then
Reporter.ReportEven micPass or 0, "Result 1", "OK button is in disabled state"
Else
Reporter.ReportEvent micFail or 1, "Result 1", "OK button is in enabled state" 
End If

WpfWindow("HP MyFlight Sample Application").WpfEdit("agentName").Set "john"
WpfWindow("HP MyFlight Sample Application").WpfEdit("password").SetSecure "232233222e3"

If After = True Then
Reporter.ReportEven micPass or 0, "Result 2", "OK button is in enabled state"
Else
Reporter.ReportEvent micFail or 1, "Result 2", "OK button is in disabled state" 
End If

