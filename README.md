st3-theme-kcps
==============

Sublime Text 3 (ST3) Settings and Theme for Kanone Consulting and Professional Services Inc.

Based on an examination of the default theme and tm settings, I decided to use a white background, and improve a couple of controls.  A number of people have commented on the lack of contrast between the scroll bar pucks and the bars themselves (both vertical and horizontal).  There are two ways the contrast can be improved.  One is to edit the two graphic files that provided the puck templates (normal_thumb_vertical.png and normal_thumb_horizontal.png) with a graphics editor.  In the .sublime-theme file, these are referenced by the "layer0.texture" property in the "puck_control" objects, and the filenames are supplied to the texture property as values.

To get at the puck and other files, it is helpful to understand how ST3 organizes its various files, referred to as 'resources'.  For specificity and to maintain consistency in the use of terms used by programmers, I'll use the language of Unix.  However, the description and remards which follow are specific to Windows XP as that is the OS I currently use.When ST2 is installed, it creates a Packages directory in the Application Data directory of the Windows username and installs sub-directories for each package under it containing the package's files., ST3 is installed, 

other is to 
