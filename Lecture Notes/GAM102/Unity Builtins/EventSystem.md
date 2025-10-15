# Unity EventSystem

## Overview
The **EventSystem** in Unity is responsible for managing and routing input events (mouse, touch, keyboard, etc.) to UI elements and game objects that can respond to them.  
It works alongside components like **Input Modules** and **Raycasters** to detect user interactions.

---

## Core Components

### EventSystem
- Central component that coordinates event handling.  
- Typically one **EventSystem** object exists in a scene.  
- Handles input updates, selection states, and event dispatching.

**Key Properties:**
- `current`: The active EventSystem in the scene.
- `currentSelectedGameObject`: The currently selected UI element.
- `firstSelectedGameObject`: The first object selected when the scene starts.
- `sendNavigationEvents`: Enables/disables keyboard/controller navigation.

---

### Input Modules
Modules define how input is processed and translated into events.  

**Common Input Modules:**
- **StandaloneInputModule**: Handles mouse, keyboard, and controller input (default).
- **TouchInputModule**: Handles touch input for mobile devices.
- **XRInputModule**: Used for VR/AR interactions.

Each EventSystem uses exactly one active Input Module at a time.

---

### Raycasters
Raycasters determine which UI element or object is under a pointer.

**Common Raycasters:**
- **GraphicRaycaster**: Used for UI elements on a Canvas.
- **PhysicsRaycaster**: Used for 3D objects with colliders.
- **Physics2DRaycaster**: Used for 2D objects with colliders.

---

## Event Interfaces

Unity provides several interfaces to handle user interactions:

| Interface | Triggered By | Common Use |
|------------|---------------|-------------|
| `IPointerEnterHandler` | Pointer entering object | Hover effects |
| `IPointerExitHandler` | Pointer leaving object | Hover exit |
| `IPointerDownHandler` | Mouse/touch press | Button press |
| `IPointerUpHandler` | Mouse/touch release | Button release |
| `IPointerClickHandler` | Completed click | UI button click |
| `IBeginDragHandler` / `IDragHandler` / `IEndDragHandler` | Drag events | Draggable UI |
| `IScrollHandler` | Scroll input | Scroll views |
| `ISelectHandler` / `IDeselectHandler` | Selection changes | UI focus logic |
| `ISubmitHandler` / `ICancelHandler` | Input submit/cancel | Form or menu control |

Implement these interfaces in a script attached to the target GameObject.

---

## Typical Setup
1. Create a **Canvas** (for UI).  
2. Add an **EventSystem** to the scene (automatically created when adding UI).  
3. Ensure the **StandaloneInputModule** is attached.  
4. Use a **GraphicRaycaster** on the Canvas to enable UI interaction.

---

## Example: Basic Click Handling

```csharp
using UnityEngine;
using UnityEngine.EventSystems;

public class ClickHandler : MonoBehaviour, IPointerClickHandler
{
    public void OnPointerClick(PointerEventData eventData)
    {
        Debug.Log("Object clicked: " + gameObject.name);
    }
}
```

---

## Notes
- Only one EventSystem should exist per scene.
- The EventSystem updates each frame and determines which object should receive input events.
- Custom input modules can be created by extending `BaseInputModule`.

[[Unity Builtins]]