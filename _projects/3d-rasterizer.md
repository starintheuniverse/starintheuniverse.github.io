---
title: "3D Rasterizer"
date: 2016-10-31
---

I wrote this program for UO CIS441, Computer Graphics (w/ Prof. Hank Childs).
It takes as input a vector of triangles (represented as 3 vertex locations, 3 vertex colors, 3 vertex normals) + camera and lighting parameters, and renders an image. 
[Video demo](https://vimeo.com/228142150).

<!--endexcerpt-->

[![Final Output](https://user-images.githubusercontent.com/30641704/28946358-40467c64-785f-11e7-8ec1-3c202e96f294.gif)](https://vimeo.com/228142150 "Final Output")

I am not uploading my source code publicly, out of respect for the instructor and students in future CIS441 classes.
Please contact me privately if you would like to see the code.

Dependencies & Attributions:
Depends on the VTK library to unpack .vtk geometry files and to export a color buffer to a PNG-formatted file.
Depends on the C++ standard library for memory copy and floating point math.
Prof. Childs supplied inputs and some utility code:
* the polygon geometry (.vtk file);
* lighting parameters;
* a routine to initialize a vector of triangles from a .vtk geometry file;
* a routine to export a color buffer to a PNG file;
* a Triangle struct and a Screen struct (color buffer);
* a Matrix class with a routine to multiply two matrices and a method to act on a point (length-4 float array);
* an animation over the camera parameters;
* custom floating-point rounding procedures;

All other code was written by me by hand.

This program was constructed in iterations, as per the course requirements:

**Phase A** - Output an image.  
<img src="/assets/3d-rasterizer-screenshots/1A.png" alt=""> 

**Phase B** - Basic scanline. Assume 2D flat-bottom triangles (color; vertex locations) with device space coordinates.  
<img src="/assets/3d-rasterizer-screenshots/1B.png" alt=""> 

**Phase C** - Introduce arbitrary 2D triangles (color; vertex locations), still device space coordinates.  
<img src="/assets/3d-rasterizer-screenshots/1C.png" alt=""> 

**Phase D** - Introduce Z-buffer and 3D triangles (vertex locations & colors) with device space + depth coordinates.  
<img src="/assets/3d-rasterizer-screenshots/1D.png" alt=""> 

**Phase E** - Introduce Phong shading, directional lighting. Add vertex normals to triangles.  
<img src="/assets/3d-rasterizer-screenshots/1E-ambient.png" alt="Ambient">
<img src="/assets/3d-rasterizer-screenshots/1E-diffuse.png" alt="Diffuse">
<img src="/assets/3d-rasterizer-screenshots/1E-specular.png" alt="Specular">
<img src="/assets/3d-rasterizer-screenshots/1E-composed.png" alt="Phong">

**Phase F** - Introduce camera transforms, assume triangle coordinates are in world space. (See animation at top).  
