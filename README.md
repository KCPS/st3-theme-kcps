st3-theme-kcps
==============

Sublime Text 3 (ST3) Settings and Theme for Kanone Consulting and Professional Services Inc.

Based on an examination of the default theme and tm settings, I decided to use a white background, and improve a couple of controls.  A number of people have commented on the lack of contrast between the scroll bar pucks and the bars themselves (both vertical and horizontal).  There are two ways the contrast can be improved.  One is to edit the two graphic files that provided the puck templates (normal_thumb_vertical.png and normal_thumb_horizontal.png) with a graphics editor.  In the .sublime-theme file, these are referenced by the "layer0.texture" property in the "puck_control" objects, and the filenames are supplied to the texture property as values.

To get at the puck and other files, it is helpful to understand how ST3 organizes its various files, referred to as 'resources'.  For specificity and to maintain consistency in the use of terms used by programmers, I'll use the language of Unix.  However, the description and remards which follow are specific to Windows XP as that is the OS I currently use.

This README is directed to users who have a small amount of exposure to ST2 or ST3, possibly having just installed it, played around for an hour or two, and maybe poked around the Sublime Forum or other sites and blogs proffering advice about the editor.  For the newbie, customizing ST3 can be a frustrating experience as official documentation is very scant, advice from amateurs often flat-out wrong, and what decent how-tos and good articles as exist for the most part assume a familiarity the newbie does not yet possess.

When ST2 is installed, it creates a Packages directory in the Application Data directory of the Windows username and in Packages installs sub-directories for each package containing the package's files. ST3, however, creates the Packages directory in the Sublime Text 3 directory which lives in Program Files where application software is installed in Windows.  In this Packages directory you will find a number of archive files in .zip format ('PKZIP') referred to as 'packages', and bearing the suffix 'sublime-package'.  These packages control the appearance of source code text, the appearance of the user interface and certain of the functionality of ST3.  Some of the packages are specific to programming and text editing languages, and are named accordingly: JavaScript.sublime-package, SQL.sublime-package, LaTeX.sublime-package, Python.sublime-package, etc.

Now navigate to this Packages directory and direct your attention to the archive "Color Scheme - Default.sublime-package".  Open it with an archive tool such as WinZip, ExpressZip or similar.  (Note that some tools such as ExpressZip follow the annoying protocol of insisting on a .zip suffix to the filename before they will attempt to open the file.  This makes it tedious to edit ST3 packages as the user will be constantly converting between suffixes .sublime-package and .zip.)  There is nothing magical or novel about packages; they are just that - a package of files bundled uncompressed into an archive.  in the default color scheme archive the files are suffixed .tmTheme.  Each file is an XML file whose tags specify the colour and font styles of various text categories of source code files.  Examples are the colours and styles in Javascript of comments, keywords, library methods, class names, variables etc.  ST3 uses the Monokai text theme as the default.  

Any of the dozen and a half other themes supplied in the Color Scheme - Default package can be chosen by replacing the "color_scheme" setting value with the name of another theme file in the archive.  Because of its popularity, ST2&3 have a strong user base, many of whom have created their own text themes, and published them on the Internet.  Look around and see what you like.  

If you do find a text them you like, here are the steps to install it.  Recall above I mentioned ST3 creating another Packages directory in the user space under directory Sublime Text 3 in Windows Appliction Data area.  Under THIS Packages directory you will also find sub-directory User.  Copy your text theme file into User.  Open ST3 and from the Preferences menu select Settings - User.  This will open an editing tab or 'pane' in ST-ese entitled "Preferences.sublime-settings | User".  Let's say your then file is named Freesia.tmTheme, currently quite popular with ST users (https://github.com/nilium/st-theme-freesia).  Copy the following entry onto a line in the editing space:


	// Sets the colors used within the text area
 	"color_scheme": "Packages/User/Fessia.tmTheme",

(don't forget the comma!) and from the File menu select Save, or just press Ctrl+S.  Your text will instantly change to the new color scheme, and if you hadn't already created your own user settings, a file called "Preferences.sublime-settings" will have been created for you in Packages/User.  I'll say more about customizing the text theme later.

Before moving on, I will note that Packages/User is the directory where all user customizations are kept.  Preference settings such as the one we just altered are in a file there as are any text themes.  You can also keep custom versions of the user interface theme in files there, and the user interface is the topic to which I will next turn your attention.  But one last word about Packages/User.  Its importance is that it is never altered whenever you may install updates to the Sublime Text editor.  As a relatively recent application (created by Australian Jon Skinner c. 2007), updates adding features and correcting defects are still a frequent occurrence - 11, for example, in 2013.  After becoming familiar with ST3 you will likely accumulate a number of custom files which you will not want the next update to overwrite.  So stay out of the other directories that ST3 uses, keep to Packages/User.  Now to the user interface.

Despite the love and affection which has been lavished on ST3, evidenced by its rapid uptake by programmers both professional and otherwise, I have not heard one good word about the default scroll bar combination.  As you will by now I expect have installed and used ST3 out-of-the-box, you will have experienced what I am referring to: the vertical and horizontal scroll pucks are virtually indistinguishable from the scroll bar track.  As I mentioned when I first began, there are two ways to repair this state of affairs, and both are simple. Trying out each will be a worthwhile investment of your time as it will help you learn more about working with packages, and about modifying the user interface more to your liking. 

I mentioned the two puck files normal_thumb_vertical.png and normal_thumb_horizontal.png.  Where do they live? In package Theme - Default.sublime-package, installed along with the other packages in Program Files/Sublime Text 3/Packages.  Open the package in your archive tool and extract the two files into a working directory.  The images are very simple, so you can edit them with a simple graphics editor such as Microsoft Paint, which is what I did.  I blew up the images by a factor of 8 so that I could edit individual pixels easily, then re-coloured the image using three tones of turquoise.  After saving the modified file, you can add it back into the archive with your tool.  (You'll have to close ST3 first if it's open as it locks the packages it's using during execution.)  When you re-open ST3, you'll see the newly coloured pucks.

You can modify any of the image files in the Theme - Default file this way to suit yourself.  Unless you're into computer graphic art with top notch tools, you may find this a bit tedious and painstaking.  You might want first to try out some of the other ui theme packages for ST.  Most can can be found on Git Hub and installed with the ST add-on Package Control tool.  I'll show you how to install and load this tool later.  Meanwhile, there's a simple manual workaround you can use. If you haven't already, install git on your workstation and open a Git Bash shell.  Enter:

	$ cd /path/to/sublime/Packages  (e.g. /Program Files/Sublime Text 3/Packages - whatever your actual path is.)
	$ git clone git@github.com:nilium/st-theme-freesia.git

This will install directory 'st-theme-freesia' in Packages along with some sub-directories containing image files for the various widgets on the user interface.  With the freesia repository cloned, you can now hop into your preferences and set the theme key:

	{
	    // other preferences above...
	    "theme": "Freesia.sublime-theme"
	}

(Press Ctrl+S to save the change.)  "theme" is the setting attribute that refers to a file containing all the information about how the user interface appears on your monitor.  The default value is "Default.sublime-theme", and that file lives in the "Theme - Default.sublime-theme", along with the all the image files for the default theme.  You've just replaced the default user interface theme with the Freesia user interface theme, as defined in "Freesia.sublime-theme".  How do you like the new look?   This method is much faster than editing up to two dozen individual image files; your ST community has done much of the grunt work in creating new looks, tried them out and tweeked them to achieve an harmonious appearance for the user interface.  Many started out as you are now - trying to make the stock scroll puck stand out a little more, and in so doing became immersed in modifying other elements of the user interface until they had something they liked.

Recall I mentioned above that there are two methods to modifying the scroll bar and puck appearance (not counting wholesale replacement of ui theme package :-).  Extract file "Default.sublime-theme" from package "Theme - Default.sublime-theme" using your archive tool.  Remember, the .sublime-theme files control the appearance of the user interface.  Files with the suffix .tmTheme control the appearance or theme of the source code you edit.  Both are termed themes in the ST universe, so at first it may be confusing.

Now, you can open and modify the extracted file with ST3, or with some other editor such as Antechinus JavaScript Editor, Notepad++, Wordpad etc.  Since I was auditioning editors I used all three.  You will no doubt recognize that what you are looking at is JSON source.  Take a moment to look at it and see the patterns: each object has a name given in the "class" attribute, and many have various layer attributes (layer0. texture, layer0.opacity, layer0.inner_margin, etc.).  Since the text theme file is coded in XML, this gives you a good opportunity to compare the two encoding syntaxes.  I find JSON far more intuitive and easy to understand; I think Douglas Crawford has done those of us who program for the Internet a world of good. 

Scroll down to class "puck_control":

    {
        "class": "puck_control",
        "layer0.texture": "Theme - Default/normal_thumb_vertical.png",
        "layer0.opacity": 1.0,
        "layer0.inner_margin": [2, 3],
        "content_margin": [6, 0],
        "blur": true
    },

In this object you can see the use of the puck file you modified earlier, to be found in the "Theme - Default" package.  Now modify the object as follow:

    {

        "class": "puck_control",
	"layer0.texture": "",
	"layer0.tint": [192, 32, 32],
	"layer0.opacity": 1.0,
	"blur": false
    },

Notice that the texture file containing the puck template image is no longer being used.  Instead, the puck is simply tinted a medium red: RGB = [192, 32, 32].  More information is available at http://sublimetext.userecho.com/topic/116003-make-the-scrollbar-markerindicator-more-visible/# which also describes how to make the scroll bar wider or narrower, as you prefer.

Another change you can make is to the colour of the scroll bar race.  In class "scroll_bar_control" I've made the race a medium gray:

    {
        "class": "scroll_bar_control",
        "layer0.texture": "",			//Theme - Default/normal_bar_vertical.png",
        "layer0.opacity": 1.0,
        "layer0.tint": [100, 100, 100],
        "layer0.inner_margin": [0, 6],
        "blur": false
    },

(The scroll bar control object is just above the puck control object in the Default theme file.)

Both the text and the ui theme files contain quite a few settings.  While not an impossibly large number to learn, if you want to do much cusomization of yoru ST installation, you'll need to invest some time, probably a couple of weeks.  This learning curve, made shallow, by the paucity of documentation for both kinds of theme settings, is the only serious criticism I've run across of Sublime Theme.




