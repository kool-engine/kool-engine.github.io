---
title: Home
layout: default
nav_order: 1
description: "An OpenGL / WebGPU engine for Desktop JVM, Android and Javascript written in Kotlin."
---

# kool Documentation
{: .fs-9 }

kool is a multi-platform OpenGL / WebGPU game engine written in kotlin that works on Desktop Java, Android and in browsers.
{: .fs-6 .fw-300 }

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[View it on GitHub][kool repo]{: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started

kool supports two development styles: Editor and code-only. The easiest way to get into things is using
[the editor]({% link docs/editor/editor.md %}). However, the editor is still in a rather early state and you may prefer
the code-only way. In that case the [kool Templates] provide the easiest way to start a clean kool project from scratch.

Alternatively, you can browse the
[sourcecode](https://github.com/kool-engine/kool/tree/main/kool-demo/src/commonMain/kotlin/de/fabmax/kool/demo) of
[the Demos]({% link demos.md %}) to get an impression of slightly more complex scenarios.

Finally, here's a complete hello world example:

```kotlin
fun main() = KoolApplication {
    // Create and add a new scene
    addScene {
        // Add a mouse manipulatable camera
        defaultOrbitCamera()

        // Add a spinning colored cube
        addColorMesh {
            generate {
                cube {
                    colored()
                }
            }
            shader = KslPbrShader {
                color { vertexColor() }
                metallic(0f)
                roughness(0.25f)
            }
            onUpdate {
                transform.rotate(45f.deg * Time.deltaT, Vec3f.X_AXIS)
            }
        }

        // Add a directional light to illuminate the scene
        lighting.singleDirectionalLight {
            setup(Vec3f(-1f, -1f, -1f))
            setColor(Color.WHITE, 5f)
        }
    }
}
```

### License

kool is distributed by an [Apache-2.0 License](https://github.com/kool-engine/kool/blob/main/LICENSE).

### Get in touch

Feel free to join the [Discord Server](https://discord.gg/GvsJj2Pk3K)!

### Code of conduct

kool is committed to fostering a welcoming community.

[View the Code of Conduct](https://github.com/kool-engine/kool/blob/main/CODE_OF_CONDUCT.md) on our GitHub repository.

[kool repo]: https://github.com/kool-engine/kool
[kool Templates]: https://github.com/kool-engine/kool-templates