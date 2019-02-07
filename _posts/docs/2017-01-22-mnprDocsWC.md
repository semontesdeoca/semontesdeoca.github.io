---
layout: publication
categories: docs
title: MNPR Watercolor Documentation
authors: santy
type: Docs
excerpt: MNPR Watercolor Documentation - Tutorials, FAQ, API
tags: [Docs, NPR, Real-time, Watercolor, Art-directed, Research, Maya, Software]
image:
  feature: headers/wcDocs.jpg
  credit: "Stylized by Joan Cabot using MNPR - Watercolor"
  card: cards/wcDocs.jpg
  thumb:
comments: true
share: true
schema: SoftwareApplication
---

Documentation for the watercolor stylization system using [MNPR - Watercolor](../../projects/Maya-Watercolor).

* Table of Contents
{:toc}

## Requirements
* Maya 2016 Ext. 2 [SP2] or Maya 2017
* Microsoft Windows (7, 8.1, 10)
* Graphics Card supporting DirectX 11

## Installation
<figure class="single">
<iframe width="560" height="315" src="https://www.youtube.com/embed/aEL7xupnn7E" frameborder="0" allowfullscreen></iframe>
</figure><br>

## The WC Shelf and Tools
The shelf tools all possess tooltips describing their use and workflow. These tooltips contain the following:

1. Watercolor Information -> opens browser with this website
2. _prep_, opens the preparation shelf -> used to prepare selected polygonal meshes into watercolor ready meshes and assigning the object-space painterly shader
3. _conf_, selects configuration node -> used to control render globals
4. _pass_, opens the system render settings -> used to enable/disable certain operations and show different framebuffers (targets in Maya)
5. _paint_, opens watercolorFX -> used to paint and art-direct the effects on selected geometry
6. Viewport render, opens the render UI -> used to save screenshots or playblasts
7. Material editor, shows the material of selected objects -> used to tweak the watercolor object-space shader
8. Create ambient light
9. Create directional light
10. Create point light
11. Create spot light
12. Creates a simple default test scene
13. Feedback, opens browser with a feedback platform -> please try to make it as constructive as possible

## Tutorials
Several tutorials have been created to ease the learning curve of users. These tutorials are embedded next:

**Creating and manipulating the object-space shaders**
<figure class="single">
<iframe width="560" height="315" src="https://www.youtube.com/embed/I44vHdyVyDM" frameborder="0" allowfullscreen></iframe>
</figure><br>

**Manipulating the global stylization values**
<figure class="single">
<iframe width="560" height="315" src="https://www.youtube.com/embed/XwkV8IpQ5X4" frameborder="0" allowfullscreen></iframe>
</figure><br>

**Painting and manipulating the hybrid-space, localized effects**
<figure class="single">
<iframe width="560" height="315" src="https://www.youtube.com/embed/vxQ67nQ91Os" frameborder="0" allowfullscreen></iframe>
</figure><br>

## Example Scenes
A test scene has been prepared, to load the scene within Maya (once the system has been installed) follow the next procedures:

1. Set your Maya project to the projects folder in the watercolor system directory `Menu, File->Set Project`
2. Open fruitPlate.ma scene `Menu, File->Open`
3. The objects might appear green, as the object-shaders are not found in your machine. To fix this, in the WC shelf, right click on the prep shelf button and select _"reload all shaders"_.


## FAQ
_**Is there any version for Mac or will there be any in the future?**_<br>
Unfortunately not, unless someone decides to sponsor me a Mac and I get enough time to translate the HLSL shader code to GLSL. It is highly unlikely to see a Mac version in the near future.

_**I prep my objects, but they come out white, what can I do?**_<br>
This issue happens when the dimensions of the scene are too big, and the atmosphere color fully kicks in (which by default is white). It will be fixed in future versions, but you can change the atmosphere limits in your `Object-space shader -> Additional Object-Space Effects -> Atmosphere Start/End_`. If you set the atmosphere _start_ higher than the _end_, no atmosphere color should affect the shader.

_**I can't get the system to install using the install.mel file, what can I do?**_<br>
There are two ways of manually installing the stylization system

_Solution 1: Temporarily remove the content in the Maya environment file_

1. Copy the existing content of Maya.env to another file
2. Clear all the environment variables (which you have copied over already for backup) and save the file
3. Drag and drop the install.mel file again into the Maya viewport -> it should install successfully then
4. Merge the other environment variables with the new ones in the Maya.env file and save.
5. Restart Maya

_Solution 2: Insert the system paths manually to the Maya environment_

* Enter the following environment variables into Maya (make sure the shelf path is the first environment variable)

> ```python
MAYA_SHELF_PATH=C:\%YOURWCSYSPATH%\shelves;
MAYA_PLUG_IN_PATH=C:\%YOURWCSYSPATH%\plugins;
PYTHONPATH=C:\%YOURWCSYSPATH%\scripts;
MAYA_SCRIPT_PATH=C:\%YOURWCSYSPATH%\scripts;
XBMLANGPATH=C:\%YOURWCSYSPATH%\icons;
MAYA_VP2_USE_GPU_MAX_TARGET_SIZE=1;
```

* Run this mel script: `setRenderingEngineInModelPanel "DirectX11"`
* Restart Maya


<!-- ## License -->

## Release log
Version 0.2 - **User-study release** - _26 December 2016_

  * New algorithm for color bleeding
  * Created multiple tutorials and breakdowns of the stylization system
  * Revised config tool to manipulate global stylization values
  * Added support for custom substrate textures
  * Fixed painting for edge darkening
  * Fixed installation issues when sometimes a Maya.env file did not exist
  * Included project website in the shelf
  * Performance improvements
  * Other small bug fixes

<br>

Version 0.1 - **Initial Beta release** - _06 September 2016_
