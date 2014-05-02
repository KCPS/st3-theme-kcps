st3-theme-kcps
==============

Sublime Text 3 (ST3) Settings and Theme for Kanone Consulting and Professional Services Inc.

Based on an examination of the default theme and tm settings, I decided to use a white background, and improve a couple of controls.  A number of people have commented on the lack of contrast between the scroll bar pucks and the bars themselves (both vertical and horizontal).  There are two ways the contrast can be improved.  One is to edit the two graphic files that provided the puck templates (normal_thumb_vertical.png and normal_thumb_horizontal.png) with a graphics editor.  In the .sublime-theme file, these are referenced by the "layer0.texture" property in the "puck_control" objects, and the filenames are supplied to the texture property as values.

To get at the puck and other files, it is helpful to understand how ST3 organizes its various files, referred to as 'resources'.  For specificity and to maintain consistency in the use of terms used by programmers, I'll use the language of Unix.  However, the description and remards which follow are specific to Windows XP as that is the OS I currently use.

This README is directed to users who have a small amount of exposure to ST2 or ST3, possibly having just installed it, played around for an hour or two, and maybe poked around the Sublime Forum or other sites and blogs proffering advice about the editor.  For the newbie, customizing ST3 can be a frustrating experience as official documentation is very scant, advice from amateurs often flat-out wrong, and what decent how-tos and good articles as exist for the most part assume a familiarity the newbie does not yet possess.

When ST2 is installed, it creates a Packages directory in the Application Data directory of the Windows username and in Packages installs sub-directories for each package containing the package's files. ST3, however, creates the Packages directory in the Sublime Text 3 directory which lives in Program Files where application software is installed in Windows.  In this Packages directory you will find a number of archive files in .zip format ('PKZIP') referred to as 'packages', and bearing the suffix 'sublime-package'.  These packages control the appearance of source code text, the appearance of the user interface and certain of the functionality of ST3.  Some of the packages are specific to programming and text editing languages, and are named accordingly: JavaScript.sublime-package, SQL.sublime-package, LaTeX.sublime-package, Python.sublime-package, etc.

Now navigate to this Packages directory and direct your attention to the archive "Color Scheme - Default.sublime-package".  Open it with an archive tool such as WinZip, ExpressZip or similar.  (Note that some tools such as ExpressZip follow the annoying protocol of insisting on a .zip suffix to the filename before they will attempt to open the file.  This makes it tedious to edit ST3 packages as the user will be constantly converting between suffixes .sublime-package and .zip.)  There is nothing magical or novel about packages; they are just that - a package of files bundled uncompressed into an archive.  in the default color scheme archive the files are suffixed .tmTheme.  Each file is an XML file whose tags specify the colour and font styles of various text categories of source code files.  Examples are the colours and styles in Javascript of comments, keywords, library methods, class names, variables etc.  ST3 uses the Monokai text theme as the default.  

Any of the dozen and a half other themes supplied in the Color Scheme - Default package can be chosen by replacing the "color_scheme" setting value with the name of another theme file in the archive.  Because of its popularity, ST2&3 have a strong user base, many of whom have created their own text themes, and published them on the Internet.  Look around and see what you like.  

If you do find a text them you like, here are the steps to install it.  Recall above I mentioned ST3 creating another Packages directory in the user space under directory Sublime Text 3 in Windows Appliction Data area.  Under THIS Packages directory you will also find sub-directory User.  Copy your text theme file into User.  Open ST3 and from the Preferences menu select Settings - User.  This will open an editing tab entitled "Preferences.sublime-settings | User".  Let's say your them file is name Fessia.tmTheme.  Copy the following entry into the onto a line in the editing space:


	// Sets the colors used within the text area
 	"color_scheme": "Packages/User/Fessia.tmTheme",

(don't forget the comma!) and from the File many select Save or press Ctrl+S.  Your text will instantly change to the new color scheme, and if you hadn't already created your own user settings, a file called "Preferences.sublime-settings" will have been created for you in Packages/User.  I'll say more about customizing the text theme later.

Before moving on, I will note that Packages/User is the directory where all user customizations are kept.  Preference settings such as the one we just altered are in a file there as are any text themes.  You can also keep custom versions of the user interface theme in files there, and the user interface is the topic to which I will next turn your attention.  But one last word about Packages/User.  Its importance is that is never altered whenever you may install updates to the Sublime Text editor.  As a relatively recent application (c. 



other is to 
