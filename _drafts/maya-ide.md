# Maya IDEs

I have tried many IDE's and tend to always stay up to date with the most helpful Integrated Development Environments. Whenever a new project comes around, it comes accompanied with the opportunity to try a new IDE. This has lead me to use Eclipse, Sublime, Atom, Visual Studio (Code, Community, Professional), PyCharm, MonoDevelop and more specialized IDE's such as VrmlPad, etc.

For Maya specific development, I started with Eclipse. There are some straightforward tutorials on how to set it up with Maya and I was familiar with Eclipse from my Java programming days. However, I missed some sleek features of more modern IDE's such as Sublime and Atom. Eventually, after frequently programing C++ plugins for Maya, I decided to move both my C++ and Python projects to Visual Studio Community and I love it! However, if you are only going to do Python development with Maya, I highly recommend using PyCharm.

This small article explains how I configure Visual Studio and PyCharm to work effectively with Maya. I often find myself going over these notes and tweaking them to the latest standard, so you might also find them useful.

## Visual Studio Community 2017 for Maya Development

### Configuring Visual Studio Community
1. Get Visual Studio (VS) -> [Download here](https://www.visualstudio.com/vs/community/)
2. Install Visual Studio with C++ and Python Development (select python development within the installer with either Python 2 or Anaconda 2 [x64])
4. Set up Visual Studio for python projects -> [Step by step tutorial by Michael M.](http://cgmike.com/wordpress/?p=163)
5. Set up Visual Studio for C++ projects -> [Step by step tutorial by Chad Vernon](http://www.chadvernon.com/blog/resources/maya-api-programming/introduction/)
6. Set up Visual Studio syntax highlight support for mel
  * Download a custom [usertype]("{{ site.url }}/downloads/usertype.dat") for syntax highlighting (as of Maya 2017).
  * Place the _usertype.dat_ file under `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE`.
  * Within Visual Studio > Tools > Options... > Text Editor > File Extension. Add `mel` as the extension and `Microsoft Visual C++` as the editor.
  * Hit `Add` and `OK` and restart Visual Studio.
  * Mel files should have syntax highlighting now.

Now that Visual Studio and its basic functionality with autocomplete(python and C++) are up and running, its time to tune Visual Studio.

### Get the most out of Visual Studio
1. Change the theme to Dark (unless you are in an extremely bright room) -> `Within VS > Tools > Options > Environment - Visual Experience - Color theme` - Dark
2. Turn on line numbers -> `Within VS > Tools > Options > Text Editor > All Languages - Settings` - Line Numbering
3. Turn on Minimap -> `Within VS > Right click on the scroll bar > Scroll Bar Options... - Behavior` - Use map mode for vertical scroll bar
4. Install productivity tools -> `Within VS > Tools > Extensions and Updates...` > Search for and install Productivity Power Tools
5. Turn off code structure in the margin (spacehog in minimap) -> `Within VS -> Tools > Options > Productivity Power Tools > Other extensions` - Structure visualizer options - Show code structure in the margin

### Debugging with Visual Studio
Siew Yi Liang has already written an excellent blog post about [debugging Maya plugins in Visual Studio](http://www.sonictk.com/debugging-maya-plugins-cross-platform/#1479007462493-1f9f5931-5df7)


## PyCharm for Maya development

### Getting PyCharm
1.  [Download PyCharm Edu](https://www.jetbrains.com/pycharm-edu/download/#section=windows).
2.  Install PyCharm and make sure Python 2.7 is set as your Python version.

### Configuring PyCharm
#### Setting up the interpreter
1. To set up the interpreter go to: `File -> Settings -> Project Interpreter -> click on the gear icon to the top right -> Add Local`.
2. Choose the `mayapy.exe` interpreter, usually found under: `C:\Program Files\Autodesk\Maya2017\bin\mayapy.exe`.
3. To rename the interpreter that we just added, just click on the `gear icon to the top right -> More`, select the mayapy.exe interpreter that was just added and edit it (pencil to the right) to your desired name.

#### Setting up autocomplete
4. To set up autocomplete, click again on the `gear icon to the top right -> More`, select the previously renamed interpreter and select edit the _interpreter paths_ (the last icon on the right pane)
5. Click on the plus icon to the right and add either:
  * The folder with autocompletion files that you can download [here](http://artineering.io/downloads/maya-completion.zip).
  * The path in the Maya devkit that you have previously [downloaded](https://apps.autodesk.com/MAYA/en/Detail/Index?id=6303159649350432165&os=Win64&appLang=en) and extracted: `C:\Program Files\Autodesk\Maya2017\devkit\other\pymel\extras\completion\py`.
  You will have to manually enable autocomplete for the Maya Python API 2.0 using this alternative. To do so, make sure to add the following 4 lines of code to the following file: `C:\Program Files\Autodesk\Maya2017\devkit\other\pymel\extras\completion\py\maya\api\__init__.py`.
  ```
    from _OpenMaya_py2 import *
    from _OpenMayaAnim_py2 import *
    from _OpenMayaRender_py2 import *
    from _OpenMayaUI_py2 import *
  ```
7. To avoid any potential autocomplete clashes with Maya's Python interpreter, also remove the site-packages path from the interpreter paths:  `C:\Program Files\Autodesk\Maya2017\devkit\other\pymel\extras\completion\py`

### Customizing PyCharm
1. Customize Docstrings `File -> Settings -> Tools -> Python Integrated Tools -> Docstrings -> Docstring format:` to 'Google'
2. Customize the Theme `File -> Settings -> Appearance & Behavior -> Appearance -> UI Options -> Theme:` to 'Darcula'
3. Add minimap  `File -> Settings -> Pluggins`, search for CodeGlance and install it.

## Coding Tips
* Make use of [ASCII Text Generator](http://patorjk.com/software/taag/) to create headers which organize your code (Minimaps are great for these).
  * Python ([header1](http://patorjk.com/software/taag/#p=display&c=bash&f=Univers&t=UI) | [header2](http://patorjk.com/software/taag/#p=display&c=bash&f=Ivrit&t=get))
  * C++([header1](http://patorjk.com/software/taag/#p=display&c=c%2B%2B&f=Univers&t=UI) | [header2](http://patorjk.com/software/taag/#p=display&c=c%2B%2B&f=Ivrit&t=get%0A))

## Concluding remarks

I hope you find this small article useful. I definitely will the next time I need to set up Visual Studio and PyCharm!

Please let me know if you have any suggestions for me to try out regarding VS, PyCharm or other IDEs for Maya development!
