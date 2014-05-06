st3-theme-kcps
==============

Text and user interface appearance ("themes") - size, style, colour etc. for source code editor Sublime Text 3 (ST3).  Corporate standard for Kanone Consulting and Professional Services Inc.  

This project's releases are labelled according to the versioning protocol Semantic Versioning 2.0.0 (SM200 - http://www.semver.org/), and their semantic content may be inferred by the rules stated in SM200.)

My name is Edgar Duncan George, and I live in Ontario Canada.  I am a systems design engineer with an extensive academic and business career in control systems, software design and application, IT project management, and business re-engineering.  My writing is in the formal style of AT&T's 1970s era Bell Labs, located to this day in Murray Hill, NJ.  This style of expression was introduced by (the late) Dennis Ritchie and Brian Kernighan in the Book on 'C', and the Unix V7 manual, but was widely practiced within Bell Labs.  If you want to learn my practical style of engineering, be prepared to read slowly and carefully what follows.  I do not subscribe to social media, so expect to find no 140 character thoughts in what follows.  

Based on an examination of the default theme for editor Sublime Text 3 with its text ("Monokai.tmTheme") settings, I decided I preferred dark text on a white background, despite having been weaned using vi on DEC VT100 and successor computer terminals.  For you youngsters, these terminals were always configured with standard video (white foreground text on a black background), in order to minimize activation of the CRT phosphorus target screen coating.  The later use of so-called inverse video - black on white ...okay, don't go there... - began in the late 1980s with the emergence of the science of user interface design, and the realization that white on black places extra effort on the brain to attend to the textual content).  By that time, phosphorus coatings were hardier and terminal prices had come down.  These developments lead to the Apple and Microsoft white background WYSIWYG interfaces which rested tired eyes at low cost.  

I also wanted to improve a couple of controls.  A number of people have commented in the ST user forums on the lack of contrast between ST3's scroll bar pucks and the scroll bar races (both vertical and horizontal).  There are two ways the contrast can be improved.  One is to edit the two graphic files that provide the puck templates (normal_thumb_vertical.png and normal_thumb_horizontal.png) using a graphics editor.  In the .sublime-theme file, these are referenced by the "layer0.texture" property in the "puck_control" objects, and the filenames are supplied to the texture property as values.

To get at the puck and other files, it is helpful to understand how ST3 organizes its various files, referred to as 'resources'.  In what follows, I'll avoid the use of ST speak - "resources", "tmTheme" etc. - and, in the interests of specificity and to maintain consistency with the use of vocabulary in general use by professional programmers, adopt the language of Unix documentation in this article.  However, the description and remarks which follow are specific to Windows XP as that is the OS I currently use.  Eventually, st3-theme-kcps and successors will be expanded to other operating systems.

This README is directed toward users who have a small amount of exposure to ST2 or ST3, possibly having just installed it, played with it using some text file for an hour or two, and maybe poked around the Sublime Forum, or other sites and blogs proffering advice about the editor.  For the newbie, customizing ST3 can be a frustrating experience as official documentation is very scant, advice from amateurs often flat-out wrong, and what decent how-tos and good articles as exist for the most part assume a familiarity the newbie does not yet possess.

When ST2 is installed, it creates a Packages directory in the Application Data directory of the Windows username and, in Packages, installs sub-directories for each package containing the package's files. ST3, however, creates the Packages directory in the Sublime Text 3 directory which lives in Program Files where application software is installed in Windows.  In this Packages directory you will find a number of archive files in .zip format ('PKZIP') referred to as 'packages', and bearing the dot suffix 'sublime-package'.  These packages control the appearance of source code text, the appearance of the Sublime Text user interface, and certain of the functionality of ST3.  Some of the packages are specific to programming and text editing languages, and are named accordingly: JavaScript.sublime-package, SQL.sublime-package, LaTeX.sublime-package, Python.sublime-package, etc.

Now navigate to this Packages directory and direct your attention to the archive "Color Scheme - Default.sublime-package".  Open it with an archive tool such as WinZip, ExpressZip or similar.  (Note that some tools such as ExpressZip follow the annoying protocol of insisting on a .zip suffix to the filename before they will attempt to open the file.  This makes it tedious to edit ST3 packages as the user will be constantly converting between suffixes .sublime-package and .zip.)  There is nothing magical or novel about packages; they are just that - a package of files bundled uncompressed into an archive.  In the default color scheme archive, its filenames are suffixed with .tmTheme.  Each file is an XML file whose tags specify the colour and font styles of various text categories of source code files.  Examples of these categories are the colours and styles in Javascript of comments, keywords, library methods, class names, variables etc.  ST3 uses the Monokai text theme as the default.  

Any of the dozen and a half other themes supplied in the Color Scheme - Default package can be chosen by replacing the "color_scheme" setting's value in your user preferences with the name of another theme file in the archive.  Because of its popularity, ST2 & ST3 have a strong user base, many of whom have created their own text themes, and published them on the Internet.  Look around and see what you like.  

If you do find a text theme to your liking, here are the steps to install it.  Recall above I mentioned ST3 creating another Packages directory in the user space under directory Sublime Text 3 in Windows' username Appliction Data directory.  Under THIS Packages directory you will also find sub-directory User.  Copy your text theme file into User.  Open ST3 and from the Preferences menu select Settings - User.  This will open an editing tab, or 'pane' in ST-ese, entitled "Preferences.sublime-settings | User".  Let's say your file is named Freesia.tmTheme, currently quite popular with ST users (https://github.com/nilium/st-theme-freesia).  Copy the following entry onto a line in the editing space:


	// Sets the colors used within the text area
 	"color_scheme": "Packages/User/Fessia.tmTheme",

(don't forget the trailing comma!).  From the File menu select Save, or just press Ctrl+S.  Your text will instantly change to the new color scheme, and if you hadn't already created your own user settings, a file called "Preferences.sublime-settings" will have been created for you in Packages/User.  I'll say more about customizing the text theme later.

Before moving on to modifying the appearance of the user interface, I will note that Packages/User is the directory where all user customizations are kept.  Preference settings such as the one we just altered are in a file there, as are any text themes.  You can also keep custom versions of the user interface theme in files there; the user interface is the topic to which I will next turn your attention.  But one last word about Packages/User.  Its importance is that its contents are never altered whenever you install updates to the Sublime Text editor.  As a relatively recent application (created by Australian Jon Skinner c. 2007), updates adding features and correcting defects are still a frequent ST3 occurrence - 11, for example, in 2013.  After becoming familiar with ST3 you will likely accumulate a number of custom files which you will not want the next update to overwrite.  So stay out of the other directories that ST3 uses, and keep your modifications enscounced in Packages/User.  Now to the user interface.

Despite the love and affection which has been lavished on ST3, evidenced by its rapid uptake by programmers both professional and otherwise, I have not heard one good word about the default scroll bar.  As you will by now I expect have installed and used ST3 out-of-the-box, you will have experienced what I am referring to: the vertical and horizontal scroll pucks are virtually indistinguishable from the scroll bar track (or "race").  As I mentioned when I first began, there are two ways to repair this state of affairs, and both are simple. Trying out each will be a worthwhile investment of your time because it will help you learn more about working with packages, and much about modifying the user interface to your liking. 

I mentioned the two puck template files normal_thumb_vertical.png and normal_thumb_horizontal.png.  Where do they live? In package Theme - Default.sublime-package, installed along with the other packages in Program Files/Sublime Text 3/Packages.  Open the package in your archive tool and extract the two files into a working directory.  The images are very simple and, as such, you can edit them with a simple graphics editor such as Microsoft Paint, which is what I did.  I blew up the images by a factor of 8 so that I could edit individual pixels easily, then re-coloured the image using three tones of turquoise.  After saving the modified file, you can add it back into the archive with your tool.  (You'll have to close ST3 first if it's open as ST3 locks the packages it's using during execution.)  When you re-open ST3, you'll see the newly coloured pucks.

You can modify any of the image files in the Theme - Default file this way to suit yourself.  Unless you're into computer graphic art with top notch tools, you may find this a bit tedious and painstaking.  You might want first to try out some of the other ui theme packages for ST.  Most can can be found on Git Hub and installed with the ST add-on Package Control tool.  I'll show you how to install and load this tool later.  Meanwhile, there's a simple manual workaround you can use. If you haven't already, install Git on your workstation and open a Git Bash shell.  Enter:

	$ cd /path/to/sublime/Packages  (e.g. /Program Files/Sublime Text 3/Packages - whatever your actual path is.)
	$ git clone git@github.com:nilium/st-theme-freesia.git

This will install directory 'st-theme-freesia' in Packages along with some sub-directories containing image files for the various widgets on the user interface.  With the freesia repository cloned, you can now edit your user preferences file and set the theme key:

	{
	    // other preferences above...
	    "theme": "Freesia.sublime-theme"
	}

(Press Ctrl+S to save the change.)  "theme" is the setting attribute that refers to a file containing all the information about how the user interface appears on your monitor.  The default value following ST3's installation is "Default.sublime-theme", and that file lives in the "Theme - Default.sublime-theme" package, along with the all the image files for the default theme.  You've just replaced the default user interface theme with the Freesia user interface theme, as defined in "Freesia.sublime-theme".  

How do you like the new look?   Replacing the default theme with another is much faster than editing up to two dozen individual image files; your ST community has done much of the grunt work in creating new looks, tried them out and tweeked them to achieve an harmonious appearance for the user interface.  Many in the community started out as you are now - trying to make the stock scroll puck stand out a little more, and in so doing became immersed in modifying other elements of the user interface until they had something they liked.

Recall I mentioned above that there are two methods to modify the scroll bar and puck appearance (not counting wholesale replacement of ui theme package :-).  Extract file "Default.sublime-theme" from package "Theme - Default.sublime-theme" using your archive tool.  Remember, the .sublime-theme files control the appearance of the user interface.  Files with the suffix .tmTheme control the appearance or theme of the source code you edit.  Both are termed themes in the ST universe, so at first this joint use of the word 'theme' may be confusing.

Now, you can open and modify the extracted file with ST3, or with some other editor such as Antechinus JavaScript Editor, Notepad++, Wordpad etc.  (Since I was auditioning editors I used all three in order to compare them.)  You will no doubt recognize that what you are looking at is JSON source.  Take a moment to look it over and see the patterns: each object has a name given in the "class" attribute, and many have various layer attributes (layer0. texture, layer0.opacity, layer0.inner_margin, etc.).  Since the text theme file is coded in XML, this gives you a good opportunity to compare the two encoding syntaxes.  I find JSON more intuitive and easy to understand; I think Douglas Crawford has done those of us who program for the Internet a world of good. 

Scroll down to class "puck_control":

    {
        "class": "puck_control",
        "layer0.texture": "Theme - Default/normal_thumb_vertical.png",
        "layer0.opacity": 1.0,
        "layer0.inner_margin": [2, 3],
        "content_margin": [6, 0],
        "blur": true
    },

This object will show you the puck file you modified earlier, to be found in the "Theme - Default" package.  Now modify the object as follow:

    {

        "class": "puck_control",
	"layer0.texture": "",
	"layer0.tint": [192, 32, 32],
	"layer0.opacity": 1.0,
	"blur": false
    },

Notice that the texture file containing the puck template image is no longer being used.  Instead, the puck is simply tinted a medium red: RGB = [192, 32, 32].  More information is available at http://sublimetext.userecho.com/topic/116003-make-the-scrollbar-markerindicator-more-visible/#. The comment here also describes how to make the scroll bar wider or narrower, as you prefer.

Another change you can make is to the colour of the scroll bar race.  In class "scroll_bar_control" I've made the race a medium gray:

    {
        "class": "scroll_bar_control",
        "layer0.texture": "",			//Originally: Theme - Default/normal_bar_vertical.png",
        "layer0.opacity": 1.0,
        "layer0.tint": [100, 100, 100],
        "layer0.inner_margin": [0, 6],
        "blur": false
    },

(The scroll bar control object is just above the puck control object in the Default theme file.)

Both the text and the ui theme files contain quite a number of settings.  While not an impossibly large number to learn, if you want to do much customization of your ST installation, you'll need to invest some time, likely at least two or more weeks (be sure to allow time to thoroughly test and document your work, like any IT development these two aspects are critically important for long term manintenance.)  This learning curve, made shallow by the paucity of documentation for both kinds of theme settings, is the only serious criticism I've run across regarding Sublime Theme.

Tips & Tricks:
1. When modifying colours for either your text or your ui themes, a good colour picking tool is essential.  This allows you to look at a proposed colour for some widget and try out variations.  Here is the one I use: http://www.colorpicker.com.  Although the theme files use hexadecimal to specify colours, you can copy and paste a colour's hexadecimal value from a theme file directly into colorpicker, and it will spit out the colour in both RGB and HSB coordinates.  You can then adjust the colour coordinates until you get exactly what you want.  Each time you make a change, colorpicker will also give you the hexadecimal value.  Once you're satisfied, just copy the hex value and paste it back into the XML tag or the JSON object of the widget you're modifying. 

2. You are not compelled to respect the file suffixes which ST prescribes: '.tmTheme', '.subime-settings'.  The 'C' programming language introduced the convention that file suffixes denote the syntax encoding used: source_code.c, assembler_code.asm, archive.tar (tape archive), etc.  For st3-theme-kcps I have adopted the following file naming convention:

	* KCPS_text_theme.xml 	(conventionally named something like 'st3-theme-kcps.tmTheme')
	* KCPS_ui_theme.json  	(conventionally named something like 'st3-theme-kcps.sublime-settings')
	
	While the reasoning is obvious, one point deserves mention: the package name specifies the software application, version number, package application and identifying name (Sublime Text, version 3, visual presentation theme and KCPS).  Once a file is assigned to this particular package, the filename does not need to reference the other factors, other than the identifying name, in this case 'KCPS'.

3. Another tip (to keep the automated numbering going ...)
4. 
TEST