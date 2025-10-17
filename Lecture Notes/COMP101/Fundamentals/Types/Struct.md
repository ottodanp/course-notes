# C# Struct

## Overview
A **struct** in C# is a **value type** used to encapsulate small groups of related variables, similar to a lightweight [[Class]].  
Structs are commonly used for representing simple data entities such as points, colours, or coordinates.

---

## Key Characteristics
- **[[Value type]]** (stored on the stack, not the heap).
- Can contain **fields, properties, methods, constructors, and operators**.
- Cannot inherit from another struct or [[Class]] (but can implement interfaces).
- Automatically inherits from `System.ValueType`.
- Copied by value, not by reference.
- Default constructor initializes all fields to their default values.

---

## Syntax Example
```csharp
struct Point
{
    public int X;
    public int Y;

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Display()
    {
        Console.WriteLine($"Point: ({X}, {Y})");
    }
}

// Usage
Point p1 = new Point(2, 3);
p1.Display(); // Output: Point: (2, 3)

Point p2 = p1; // Value copy
p2.X = 10;
p1.Display(); // Still (2, 3)
p2.Display(); // (10, 3)
```

---

## Differences Between Structs and Classes

| Feature | Struct | Class |
|----------|---------|--------|
| **Type** | Value type | Reference type |
| **Memory Allocation** | Stack | Heap |
| **Inheritance** | Cannot inherit other structs/classes | Can inherit other classes |
| **Default Constructor** | Automatically provided, cannot define your own without parameters | Can define freely |
| **Copy Behavior** | Copied by value | Copied by reference |
| **Null Assignment** | Cannot be null (unless nullable) | Can be null |
| **Performance** | Usually faster for small objects | May incur garbage collection overhead |

---

## Constructors and Initialization
- Structs **cannot** have a parameterless constructor.
- Custom constructors must initialize all fields before returning.
- Fields are automatically initialized to default values (e.g., 0, false, null for reference fields).

```csharp
struct Rectangle
{
    public int Width;
    public int Height;

    public Rectangle(int width, int height)
    {
        Width = width;
        Height = height;
    }
}
```

---

## Structs and Interfaces
Structs can implement interfaces, which allows them to define behaviour contracts without inheritance.

```csharp
interface IDisplay
{
    void Show();
}

struct Circle : IDisplay
{
    public int Radius;

    public Circle(int radius)
    {
        Radius = radius;
    }

    public void Show()
    {
        Console.WriteLine($"Circle radius: {Radius}");
    }
}
```

---

## When to Use Structs
Use structs when:
- The object represents a **single, small value or data unit**.
- It is **immutable** after creation.
- You need **high-performance value semantics** (no heap allocation).
- Inheritance is not required.

**Common Examples:**
- `Vector3`, `Color`, and `Quaternion` in Unity.
- `DateTime`, `Guid`, and `KeyValuePair` in .NET.

---

## Notes
- Avoid large structs (over 16 bytes) to prevent performance issues during copying.
- Structs should be **immutable** when possible.
- Passing structs by reference (using `ref` or `in`) can improve performance for larger structs.

[[Types]]