# MonoBehaviour Scripts in Unity

## Overview
`MonoBehaviour` is the base class from which every Unity script derives. It provides access to Unity's event-driven lifecycle and allows scripts to interact with game objects, physics systems, input, and the scene.

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    void Start()
    {
        Debug.Log("Game Started");
    }

    void Update()
    {
        Debug.Log("Frame Updated");
    }
}
```

---

## Common MonoBehaviour Methods

| Method          | Called When                                      | Purpose                                      |
|-----------------|--------------------------------------------------|----------------------------------------------|
| `Awake()`       | Once when the script instance is loaded          | Initialize variables or states               |
| `Start()`       | Once before the first frame update               | Set up references or game logic             |
| `Update()`      | Every frame                                     | Handle input and frame-dependent logic      |
| `FixedUpdate()` | At fixed intervals, independent of frame rate   | Perform physics calculations                |
| `LateUpdate()`  | After all `Update()` calls                      | Perform actions that depend on other updates |
| `OnDestroy()`   | When the object is destroyed                    | Clean up resources                          |

---

## Key Points
- Scripts must be attached to a GameObject in the scene to execute their lifecycle methods.
- Only classes inheriting from `MonoBehaviour` can use Unity-specific event methods such as `Start()` and `Update()`.
- Use `Awake()` or `Start()` for initialization instead of constructors.
- The `Awake()` method is called before `Start()`.

---

## Important Considerations
- Instances of MonoBehaviour cannot be created with the `new` keyword. Use `AddComponent<T>()` to attach a script to a GameObject at runtime.
- Disabling a GameObject stops its `Update()` calls but does not prevent `Awake()` or `OnDestroy()` from executing.
- The order of execution between `Awake()`, `Start()`, and other lifecycle methods should be carefully considered when setting dependencies between scripts.

[[Unity Builtins]]