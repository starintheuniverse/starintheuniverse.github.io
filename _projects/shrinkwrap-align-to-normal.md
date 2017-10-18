---
title: "Shrinkwrap Align-to-Normal"
date: 2016-08-16"
---

This is a patch implementing a requested feature for Blender. [Watch a video demo](https://vimeo.com/234564499) of my code in action. View [my patch](https://developer.blender.org/D2154) and [the specification](https://developer.blender.org/T47440) on Blender's developer site.
<!--endexcerpt-->

"Blender is the free and open source 3D creation suite. It supports the entirety of the 3D pipeline--modeling, rigging, animation, simulation, rendering, compositing and motion tracking, even video editing and game creation" (Blender.org). I have been using and scripting in Blender since 2012, and finally dove into the source in 2016.

My patch augments the Shrinkwrap constraint. The original Shrinkwrap constraint in Blender causes the position of an object to snap to a target surface.
The method of choosing the snap point is configurable among three options.

The requested feature, Align-to-Normal, involves, in addition, conforming the orientation of the object to the surface. It's a 3D linear algebra problem.
My patch fulfills the feature requirements.

Disclaimer: My patch only works for two of the three available snap settings. When snap to "Nearest Vertex" is enabled, Align-to-Normal is disabled. This is because the surface normal is not well-defined for the "Nearest Vertex" scenario.

I submitted my code for the appropriately ranking contributors to review. Last I checked, it is still awaiting review. :]
