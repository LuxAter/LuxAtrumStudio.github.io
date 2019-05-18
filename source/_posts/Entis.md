title: Entis
author: Arden Rasmussen
tags:
  - C
categories:
  - CS
  - Graphics
date: 2019-01-02 13:59:00
---
Entis is a C based graphics engine. This is a very low level library for graphics rendering, providing interfaces for basic graphics primatives, text rendering using True Type fonts, and some very minimal image saving and rendering with PNG images.

[![GitHub Link](https://img.shields.io/badge/Github-Entis-blue.svg?style=for-the-badge)](https://github.com/LuxAtrumStudio/entis) ![](https://img.shields.io/github/repo-size/LuxAtrumStudio/entis.svg?style=for-the-badge)

<!-- more -->

# Library #

The library has one compleated interface, and two more interfaces under development. These interfaces are described below.

## Standard ##

The standard interface is to simply include the header file and the core library, then write the code using the base Entis functions. This is the most powerful interface, as it gives the closest connection to the underlying modules that are providing the rendering of the graphics, and the event interfaces. However, it is also significantly more complecated than the other interfaces. Everything must be explicitly done by the user and all event calls have to be controled.

## FPT ##

This interface is a simplification and renaming of the core interface. Some methods are removed, and combined with other methods. This is done to simplify the system, and reduce the more technical functions that are required for a basic program to function. This interface is very simple and easy to use.

## Loop-Based ##

This interface is very different from the other interfaces. Instead of the user writing the ``main`` function, it is already included in the library. The user has the ability to write a specific set of functions that will be called by the ``main`` function if they exists.

* ``void setup()`` This is called after the modules have been initialized, but before any other user code.
* ``void draw()`` This is called every frame
* ``void destroy()`` This is called at the termination of the program, but before the termination of the modules.
* ``void onKeyPress()`` This is called every time a key has been released.
* ``void onButtonPress()`` This is called every time a mouse button has been released.

This interface automaticaly constructs, renders, and terminates the core window. It also handles all user interface calls, all the data from the user interface will be saved into globaly available variables, such as ``mouseX`` and ``mouseY``. These can be accessed by any user function, allowing users to do as they wish with the data.

# Modules #

There are several core modules of the Entis graphics engine that are described below.

## Frame Buffer ##

The entis library stores an internal framebuffer, which all graphics calls are rendered to. This internal framebuffer can be saved to a PNG image, or loaded from some PNG image.

## XCB ##

Entis implements and controls an XCB connection to the X server. Thus it can handle all XCB connection info, such as input and rendering. If this module is initialized, then all rendering calls are also made to the XCB connection, inorder to display them to the user window.

### Input ###

User input can be enabled if the XCB module is initialized. The event system provides multiple interface options inorder to be able to ``wait`` or ``poll`` for events. The events that are enabled are;

* ``mouse_press``
* ``mouse_release``
* ``mouse_motion``
* ``enter_window``
* ``leave_window``
* ``key_press``
* ``key_release``
* ``window_resize``

All of these event types are accessable by the user, and any internal information about the event is parsed and inserted into the event class that is returned.

## Planned ##

As the XCB connection is only valid on Linux based system (And is being droped for wayland), work is being done to implement different low level graphics interfaces for Wayland on linux and OSX and Windows operating systems. This will allow implementation of the Entis library on most modern operating systems.