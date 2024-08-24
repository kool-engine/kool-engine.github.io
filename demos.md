---
layout: default
title: Demos
nav_order: 100
---

# kool Demos
{: .fs-9 }

The following demos demonstrate various features of the engine. All demos run in the browser as well as on Desktop JVM.
{: .fs-6 .fw-300 }

---

## Demos

Following the links launch each demo directly in the browser. (Desktop-) Chrome is recommended but other browsers might work as well.
All demos are implemented in code-only fashion (i.e. without using the editor). The code for all demos is available in
the [kool repo].

- [Island] - Height-map based island incl. some wind-affected vegetation + a basic controllable character.
- [Physics - Ragdoll] - Ragdoll physics demo.
- [Physics - Vehicle] - A drivable vehicle (W, A, S, D / cursor keys, R to reset) based on the Nvidia PhysX vehicles SDK.
- [Physics - Joints] - Physics demo consisting of a chain running over two gears. Uses a lot of multi shapes and revolute joints.
- [Physics - Collision] - The obligatory collision physics demo with various different shapes.
- [Embedded UI] - Integrated UI framework implemented completely within the engine. Fast, highly customizable and easy-to-use.
- [Particles] - Two teams of bees fighting against each other. Simulation can be toggled between CPU and compute-shader
  (if available, i.e. on WebGPU).
- [Fluffy Bunny] - Shell-shading based rendering of animated fur (based on this [video](https://www.youtube.com/watch?v=9dr-tRQzij4)).
- [Creative Coding] - A few relatively simple demos showcasing different techniques of generating procedural geometry.
- [Procedural Geometry] - Small test-case for
  procedural geometry; all geometry is generated in code (even the roses! Textures are regular images though). Also,
  some glass shading (shaft of the wine glass, the wine itself looks quite odd when shaded with refractions and is
  therefore opaque).
- [glTF Models] - Various demo models loaded from glTF / glb format
  - Flight Helmet from [glTF sample models](https://github.com/KhronosGroup/glTF-Sample-Models/tree/master/2.0/FlightHelmet)
  - Polly from [Blender](https://github.com/KhronosGroup/glTF-Blender-Exporter/tree/master/polly)
  - Coffee Cart from [Poly Haven](https://polyhaven.com/a/CoffeeCart_01)
  - Camera Model also from [Poly Haven](https://polyhaven.com/a/CoffeeCart_01)
  - A few feature test models also from the [glTF sample model repository](https://github.com/KhronosGroup/glTF-Sample-Models/tree/master/2.0)
- [Deferred Shading] - Thousands of dynamic light sources, bloom and ambient occlusion.
- [Screen-space Ambient Occlusion] - Roughly based on [this](http://john-chapman-graphics.blogspot.com/2013/01/ssao-tutorial.html) article by
  John Chapman with slightly optimized sampling (also shamelessly recreated his demo scene).
- [Screen-space Reflections] - A simple PBR shaded model with screen-space reflections and up to four spot-lights with dynamic shadows.
- [Physical Based Rendering] - Interactive PBR demo with image based lighting for various materials and environments (underlying PBR theory
  from [this](https://learnopengl.com/PBR/Theory) awesome article series).
- [Instanced / LOD Drawing] - Instanced rendering demo of the Stanford Bunny. Uses six levels of detail to render up to 8000 instances.
- [Mesh Simplification]  Interactive mesh simplification demo (based on traditional [error-quadrics](https://www.cs.cmu.edu/~./garland/Papers/quadrics.pdf))

[kool repo]: https://github.com/kool-engine/kool
[Island]: https://kool-engine.github.io/kool/demos/?demo=phys-terrain
[Physics - Ragdoll]: https://kool-engine.github.io/kool/demos/?demo=phys-ragdoll
[Physics - Vehicle]: https://kool-engine.github.io/kool/demos/?demo=phys-vehicle
[Physics - Joints]: https://kool-engine.github.io/kool/demos/?demo=phys-joints
[Physics - Collision]: https://kool-engine.github.io/kool/demos/?demo=physics
[Embedded UI]: https://kool-engine.github.io/kool/demos/?demo=ui
[Particles]: https://kool-engine.github.io/kool/demos/?demo=bees
[Fluffy Bunny]: https://kool-engine.github.io/kool/demos/?demo=shell
[Creative Coding]: https://kool-engine.github.io/kool/demos/?demo=creative-coding
[Procedural Geometry]: https://kool-engine.github.io/kool/demos/?demo=procedural
[glTF Models]: https://kool-engine.github.io/kool/demos/?demo=gltf
[Deferred Shading]: https://kool-engine.github.io/kool/demos/?demo=deferred
[Screen-space Ambient Occlusion]: https://kool-engine.github.io/kool/demos/?demo=ao
[Screen-space Reflections]: https://kool-engine.github.io/kool/demos/?demo=ssr
[Physical Based Rendering]: https://kool-engine.github.io/kool/demos/?demo=pbr
[Instanced / LOD Drawing]: https://kool-engine.github.io/kool/demos/?demo=instance
[Mesh Simplification]: https://kool-engine.github.io/kool/demos/?demo=simplification