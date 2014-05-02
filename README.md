st3-theme-kcps
==============

Sublime Text 3 (ST3) Settings and Theme for Kanone Consulting and Professional Services Inc.

Based on an examination of the default theme and tm settings, I decided to use a white background, and improve a couple of controls.  A number of people have commented on the lack of contrast between the scroll bar pucks and the bars themselves (both vertical and horizontal).  There are two ways the contrast can be improved.  One is to edit the two graphic files that provided the puck templates (normal_thumb_vertical.png and normal_thumb_horizontal.png) with a graphics editor.  In the .sublime-theme file, these are referenced by the "layer0.texture" property in the "puck_control" objects, and the filenames are supplied to the texture property as values.

To get at the puck and other files, it is helpful to understand how ST3 organizes its various files, referred to as 'resources'.  For specificity and to maintain consistency in the use of terms used by programmers, I'll use the language of Unix.  However, the description and remards which follow are specific to Windows XP as that is the OS I currently use.

This README is directed to users who have a small amount of exposure to ST2 or ST3, possibly having just installed it, played around for an hour or two, and maybe poked around the Sublime Forum or other sites and blogs proffering advice about the editor.  For the newbie, customizing ST3 can be a frustrating experience as official documentation is very scant, advice from amateurs often flat-out wrong, and what decent how-tos and good articles as exist for the most part assume a familiarity the newbie does not yet possess.

When ST2 is installed, it creates a Packages directory in the Application Data directory of the Windows username and in Packages installs sub-directories for each package containing the package's files. ST3, however, creates the Packages directory in the Sublime Text 3 directory which lives in Program Files where application software is installed in Windows.  In this Packages directory you will find a number of archive files in .zip format ('PKZIP') referred to as 'packages', and bearing the suffix 'sublime-package'.  These packages control the appearance of source code text, the appearance of the user interface and certain of the functionality of ST3.  Some of the packages are specific to programming and text editing languages, and are named accordingly: JavaScript.sublime-package, SQL.sublime-package, LaTeX.sublime-package, Python.sublime-package, etc.


other is to 
