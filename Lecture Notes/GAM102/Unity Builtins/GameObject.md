# GameObjects in Unity

## Overview
A `GameObject` is the fundamental object in Unity that represents characters, props, scenery, cameras, lights, and more. Every entity in a Unity scene is a GameObject. GameObjects act as containers for components that define their behavior, appearance, and functionality.

---

## Basic Structure

A typical GameObject may contain the following:
- **Transform Component** (required): Defines the object's position, rotation, and scale in the scene.
- **Renderer Component**: Defines how the object appears visually.
- **Collider Component**: Defines the physical shape used for collisions.
- **Custom Scripts**: Define specific behavior via MonoBehaviour scripts.

---

## Creating and Accessing GameObjects

### Creating in the Editor
- Right-click in the *Hierarchy* panel and select **Create Empty** or choose a primitive object (e.g., Cube, Sphere).
- Components can be added using the **Inspector**.

### Creating via Script

```csharp
using UnityEngine;

public class CreateObject : MonoBehaviour
{
    void Start()
    {
        // Create an empty GameObject
        GameObject emptyObject = new GameObject("EmptyObject");

        // Create a primitive GameObject (e.g., Cube)
        GameObject cube = GameObject.CreatePrimitive(PrimitiveType.Cube);

        // Position the cube
        cube.transform.position = new Vector3(0, 1, 0);
    }
}
```

---

## Common GameObject Methods

| Method                                  | Description                                                       |
|-----------------------------------------|-------------------------------------------------------------------|
| `SetActive(bool value)`                 | Activates or deactivates the GameObject                           |
| `activeSelf`                            | Returns whether the GameObject is active in the hierarchy         |
| `activeInHierarchy`                     | Returns whether the GameObject is active considering its parents  |
| `AddComponent<T>()`                     | Adds a component of type T to the GameObject                      |
| `GetComponent<T>()`                     | Retrieves a component of type T attached to the GameObject        |
| `Find(string name)`                     | Finds a GameObject by name in the scene                           |
| `Destroy(Object obj)`                   | Removes a GameObject or component from the scene                  |

---

## Key Points
- A GameObject itself does not contain behavior or visual data; components define these aspects.
- The `Transform` component is mandatory and always present.
- Activating or deactivating a GameObject affects all of its children.
- Multiple components of the same type can be added if allowed (e.g., multiple colliders).

---

## Important Considerations
- Using `Find()` frequently can be inefficient; consider caching references.
- Deactivating a parent GameObject will also deactivate all its children.
- When cloning GameObjects with `Instantiate()`, be aware of references to scripts and components to avoid unintended behavior.
- Proper hierarchy organization improves scene management and performance.

[[Unity Builtins]]