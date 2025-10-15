# Canvas in Unity

## Overview
The `Canvas` is a core component in Unity's UI system. It acts as a container for all UI elements, defining how they are rendered and positioned. Every UI element (such as Text, Image, Button) must be a child of a Canvas to be visible in the scene.

---

## Types of Canvas

| Render Mode             | Description                                                                 | Typical Use Case                                 |
|--------------------------|-----------------------------------------------------------------------------|-------------------------------------------------|
| Screen Space - Overlay   | Renders UI directly on the screen, on top of all scene elements             | Main HUD, menus, score displays                 |
| Screen Space - Camera    | Renders UI in relation to a specific camera                                 | UI with perspective effects or camera effects   |
| World Space             | Renders UI as part of the 3D world, positioned via transforms               | In-world labels, interactive panels in 3D space |

---

## Creating a Canvas

### In the Editor
1. Right-click in the *Hierarchy* panel.
2. Select **UI > Canvas**.
3. A Canvas and an [[EventSystem]] will be created automatically.

### Via Script

```csharp
using UnityEngine;

public class CanvasCreator : MonoBehaviour
{
    void Start()
    {
        GameObject canvasObject = new GameObject("MyCanvas");
        Canvas canvas = canvasObject.AddComponent<Canvas>();
        canvas.renderMode = RenderMode.ScreenSpaceOverlay;

        // Add a CanvasScaler and GraphicRaycaster for proper UI behavior
        canvasObject.AddComponent<UnityEngine.UI.CanvasScaler>();
        canvasObject.AddComponent<UnityEngine.UI.GraphicRaycaster>();
    }
}
```

---

## Common Canvas Properties

| Property           | Description                                                               |
|---------------------|---------------------------------------------------------------------------|
| `renderMode`        | Defines how the Canvas is rendered (Overlay, Camera, or World Space)     |
| `pixelPerfect`      | When enabled, ensures UI elements align with pixels                     |
| `worldCamera`       | Specifies which camera renders the UI (used in Screen Space - Camera)   |
| `sortingOrder`      | Controls the rendering order of multiple canvases                       |

---

## Key Points
- A Canvas is required for any UI elements to appear.
- UI elements use **RectTransform** instead of regular Transform.
- Each Canvas incurs a draw call; multiple canvases can affect performance.
- For better optimization, group static UI elements under a single Canvas.

---

## Important Considerations
- Frequent changes to UI elements on the same Canvas can cause the entire Canvas to be redrawn. Consider splitting dynamic and static UI across multiple canvases.
- In World Space mode, the Canvas behaves like any other [[GameObject]] and can be positioned in the scene.
- Ensure a **GraphicRaycaster** component is present to detect UI input events.
- Adjust **Canvas Scaler** settings for consistent UI scaling across different screen resolutions.


[[Unity Builtins]]