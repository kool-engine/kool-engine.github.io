---
layout: default
title: Object Settings
parent: Editor
nav_order: 3
---

# Object Settings
{: .fs-9 .no_toc }

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The `Object settings` panel on the right side is used to customize objects. You can add arbitrary components
via the `Add Component` button in the bottom and edit the component properties in the editor.

**TODO:** Add more explanations

## Object type
The assigned components determine the type of an object. There can only be one type-determining component per
object.

### Mesh
`GameEntities` containing a `MeshComponent`.

### Model
`GameEntities` containing a `ModelComponent`.

{: .warning }
`ModelComponent` will probably be merged with `MeshComponent` soon.

### Light
`GameEntities` containing a `LightComponent`.

### Camera
`GameEntities` containing a `CameraComponent`.

### Group
`GameEntities` without any of the aforementioned components.

### Scene
`GameEntities` containing a `SceneComponent`.

## Material components

## Physics components
**TODO**

## Scene-level components
**TODO**