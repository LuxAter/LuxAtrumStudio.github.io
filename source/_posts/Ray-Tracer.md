title: Ray Tracer
author: Arden Rasmussen
tags:
  - C++
categories:
  - CS
  - Graphics
thumbnail: /gallery/thumbnails/ray-tracer.png
date: 2018-04-29 21:52:00
---
This ray tracer implements the basis of a ray tracing rendering engine in C++. It is posible to render still images, or sequences of images. Multithreading has also been implemented allowing for significantly faster render times.


[![GitHub Link](https://img.shields.io/badge/Github-Ray_Tracer-blue.svg?style=for-the-badge)](https://github.com/LuxAtrumStudio/RayTracer) ![](https://img.shields.io/github/repo-size/LuxAtrumStudio/RayTracer.svg?style=for-the-badge)


<!-- more -->

The ability to create multiple object of *sphere*, *triangle*, *plane*, *circle*, or *mesh* types is currently available. Where a mesh is any collection of triangles specified by an ``*.stl`` file. Thus allowing for the import of any arbatrary model. Using these five different supported objects, there is the posiblity for the construction of all three dimensional models.

The implementation of different materials is such that the reflextivity of the material, the specular index, and the diffuse and specular colors can be determined. Using these settings it is posible to demonstrate most opaque materials.

There are three formats of lights implemented in the system. *Distant* lights are lights that cast parallel rays across the entier space. They are useful for simulations of sunlight, or large sources of light that are very far away. *Point* lights approximate point sources. *Area* lights represent a light source from a rectangle. This is useful for most light sources, as very few sources of light are actual point sources, and can be better represented by this area light source. Every light can have have a specified intensity and color. And area light sources can specify the number of samples for calculating the lighting. Higher number of samples improves the quality of soft shadows produced in the final image.

The entier process is self enclosed, as the process of compialation also compiles and links ``libpng`` inorder to output ``png`` files.

The multithreading is optimized by scattering the pixels that each thread renders, so that no single thread is soley rendering a simple set of pixels. This provies a significantly faster rendering time. Thus allowing for the rendering of significantly more complex systems.