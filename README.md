Sketch Interpolate Paths Plugin
===============================

This plugin attempts to recreate the "interpolate path" feature which may be
known from tools like Adobe Illustrator for the otherwise brilliant [Sketch
app](http://bohemiancoding.com/sketch).

The plugin will eventually be able to generate a stepwise interpolation between
two selected paths. Below is a proof-of-concept animation using a very early
version of the script:

![Proof of Concept](proof_of_concept.gif)

The interpolation seen in the animation is by no means perfect yet.


## Usage

- Put the .sketchplugin file into the Plugins folder of your Sketch app.
- Execute from Sketch's Plugin menu after selecting two paths.


## Features

The following attributes are regarded when doing the interpolation:

- Position of points
- Position of curve anchors
- Path opacity

Todo:

- All other path-level properties (Size, Color, ...)

Can't really be done:

- Blending modes: interpolation does not make sense here

Currently, **both paths must have the same number of points**. This restriction
might be lifted in the future. There's no guarantee of proper working if
corresponding points have differing curve modes in the two paths. Generally, it
should work fine, though.

Generally the plugin copies the properties of the hierarchy wise bottom-most
path selected (i.e. the one furthest in the back).
