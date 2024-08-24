---
layout: default
title: Editor Basics
parent: Editor
nav_order: 2
---

# Editor Basics
{: .fs-9 .no_toc }

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The basic scene editing features work similar to most 3D editing software and should be mostly self-explanatory.
Most editing features are also accessible via key-bindings and you can open a context-aware popup window, showing
you the currently available keys by pressing `F1`.

## Adding and removing objects
You can add objects by right-clicking into the scene view and select an object type from the `Add object` sub-menu
of the appearing popup-menu (e.g. `Add object` -> `Mesh` -> `Box` to add a box mesh). The object appears at the
click position and will have the same parent object as the object you selected with the initial right click.
Alternatively, you can right click any object in the `Scene Browser` on the left side and use the popup-menu there.

Objects can be removed via the right-click menu or by pressing `Delete`.

## Undo / redo, copy & paste and duplicate
Of course undo and redo work as expected by pressing `Ctrl + Z` / `Ctrl + Y` and you can use `Ctrl + C` and
`Ctrl + V` to copy and paste selected objects. Moreover, you can use `Ctrl + D` to duplicate the current selection
which is more or less identical to copy and immediately pasting it.

## Manipulating objects
You can move, rotate and scale selected objects either via the corresponding toolbar buttons on the left side of
the scene view or by using the hotkeys `G` (grab / move), `R` (rotate) and `S` (scale). The toolbar buttons enable
a transform gizmo for the selected objects which can then be used to transform the objects as you like.

When using the hotkeys however, you enter the immediate transform mode, which works very similar to how Blender
works but might be a bit unintuitive in case you never used Blender: In immediate transform mode, the objects are
transformed by simply moving the mouse, without the need to drag any fiddly gizmo handles. Moreover, you can constrain
the manipulation to a certain axis by pressing `X`, `Y` or `Z` or to a plane by pressing `Shift + X`, `Shift + Y`
or `Shift + Z`. Finally, in axis mode you can also type a number to manipulate the selected objects by that amount.
Press `Enter` or the left mouse button to apply the transform or `Esc` or the right mouse button to cancel the transform.

Immediate transform mode is very useful to do quick and precise manipulations. For example, if you want to move an
object 3.5 units to the right, you can simply select it and type `G` (to enter grab / move mode), `X` to constrain
movement to the x-axis then type `3.5` to move the object 3.5 units along the x-axis and finally press enter to apply
the movement.

During object manipulation you can also press `Ctrl` to get a ticked behavior with fixed increments and `Shift`
to get more precise manipulation.

## Transform mode
By default object transforms are relative to the global frame, but it often makes sense to use the local or parent
frame instead. You can do so by selecting the corresponding mode from the `Transform mode` chooser at the top of the
window.
