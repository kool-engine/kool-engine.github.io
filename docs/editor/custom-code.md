---
layout: default
title: Integrating Custom Code
parent: Editor
nav_order: 4
---

# Integrating Custom Code
{: .fs-9 .no_toc }

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

The most powerful feature of the editor is the integration of custom code, which works by adding a custom `Behavior`
component to an object. Custom behaviors can be created with the JVM version of the editor by creating a new class
that extends `KoolBehavior` in the source code (i.e. in IntelliJ). A minimal custom behavior could look like this:

```kotlin
class SomeCustomBehavior : KoolBehavior() {
    override fun onInit() {
        // optional: do initialization stuff here 
    }

    override fun onUpdate(ev: RenderPass.UpdateEvent) {
        // optional: do most of your business here, called on every frame
    }
    
    override fun onPhysicsUpdate(timeStep: Float) {
        // optional: do physics related stuff here, called on every physics step
    }
}
```

Whenever you add or edit source-code and return to the kool editor window it detects the changes automatically and
reloads the scene including the changed code. I.e. after adding the above class stub, the editor would reload the
scene and you could select `Some Custom Behavior` from the `Add Component -> Behavior` menu.

### Editor visible properties
It's also possible to add (public mutable) properties to behavior classes, which then appear in the editor UI.
Property types supported by the editor are:

- Primitive types (numeric types, strings and booleans)
- Vector types (2, 3 and 4 components, int, float and double types. E.g. Vec2i, Vec3f, Vec4d)
- `GameEntity`, which can be assigned with any other scene object 
- `GameEntityComponent` and all its subclasses (e.g. `RigidActorComponent`)
- `KoolBehavior` and all its subclasses (e.g. any custom behavior class)

Properties can also be annotated to get a richer editor experience:

```kotlin
class SomeCustomBehavior : KoolBehavior() {
    @EditorInfo(label = "Meaningful label:", order = 1)
    @EditorRange(minX = 0.0, maxX = 100.0)
    var someNumber: Int = 17

    @EditorInfo(label = "Character:", order = 2)
    var giveMeSomeCharacter: CharacterControllerComponent? = null

    @EditorHidden
    var valueThatShouldNotShowUpInTheEditor = 1234
}
```
In this example the first two properties would show up in the editor, while the third property (annotated with
`@EditorHidden`) would not show up despite being public and mutable. Moreover, `someNumber` could only be assigned
with values between 0 and 100. `giveMeSomeCharacter` could be assigned with any `CharacterControllerComponent`
present in the scene.

### Interacting with scene objects and other components
Besides assigning scene objects via the editor UI, behavior classes can also query them programmatically. After
a behavior class is attached to a scene object, it is accessible via `gameEntity`:
```kotlin
class SomeCustomBehavior : KoolBehavior() {
    override fun onInit() {
        logI { "I'm attached to ${gameEntity.name}" }
    }
}
```


For convenience, the `transform` component of the parent `gameEntity` is directly accessible in behavior classes:
```kotlin
class SomeCustomBehavior : KoolBehavior() {
    override fun onUpdate(ev: RenderPass.UpdateEvent) {
        // rotates the parent object by 90°/s around the Y-axis
        transform.rotate(90f.deg, Vec3f.Y_AXIS)
    }
}
```


Other components of the parent `gameEntity` can be queried via `getComponent()`:
```kotlin
class SomeCustomBehavior : KoolBehavior() {
    private val meshComponent by lazy { gameEntity.getComponent<MeshComponent>() }

    override fun onStart() {
        meshComponent?.drawNode?.let { mesh ->
            logI { "Mesh tri count: ${mesh.geometry.numPrimitives}" }
        }
    }
}
```

It's also possible to access the scene via `gameEntity.scene` and do scene-wide queries for components, iterate
over all scene objects, etc.
