---
layout: post
author: santy
title: Compiling .fx Shaders
type: Resource
excerpt: Compile a dx11Shader .fx shader into .fxo
categories: Resource
tags: [Maya, dx11Shader]
image:
  feature: chapter1/front.jpg
  credit: Siggraph Anaheim - USA 2013
  card: chapter1/card.jpg
  thumb:
comments: true
share: true
read_time: true
---

## Compiling FX shaders


When using the dx11Shader in Maya, you may want to distribute your .fx shaders to other Maya users. A good practice is to protect your source code.

However, the resources available on how to compile an .fx shader into an .fxo are quite confusing.

To ease future headaches of anyone looking to compile .fx shaders, here is how I do it in the command prompt.

  {% raw %}
  cd "C:\Program Files (x86)\Windows Kits\8.1\bin\x64\"
  fxc.exe /T fx_5_0 /Fo C:\shaders\shaderX.fxo C:\shaders\shaderX.fx
  {% endraw %}

To know what type of commands are available with the fx compiler, type the following:

  fxc.exe /?

Have fun compiling!
