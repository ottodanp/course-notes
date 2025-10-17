# C# Class

## Overview
A **class** in C# is a **reference type** that defines the blueprint for objects.  
It encapsulates data (fields, properties) and behavior (methods, events) into a single unit.  
Classes are fundamental to **object-oriented programming (OOP)** in C#.

---

## Key Characteristics
- **[[Reference Type]]** (allocated on the heap).  
- Supports **[[Inheritance]]**, **[[polymorphism]]**, and **[[encapsulation]]**.  
- Can contain **fields, properties, methods, events, and constructors**.  
- Can be **abstract**, **sealed**, or **static**.  
- Objects are accessed via **references**, not by value.  

---

## Syntax Example
```csharp
class Player
{
    public string Name;
    public int Health;

    public Player(string name, int health)
    {
        Name = name;
        Health = health;
    }

    public void TakeDamage(int amount)
    {
        Health -= amount;
        Console.WriteLine($"{Name} took {amount} damage. Health: {Health}");
    }
}

// Usage
Player p1 = new Player("Alex", 100);
p1.TakeDamage(20);
```
---

## Access Modifiers
| Modifier | Accessibility |
|-----------|----------------|
| `public` | Accessible from anywhere |
| `private` | Accessible only within the same class |
| `protected` | Accessible within the class and derived classes |
| `internal` | Accessible within the same assembly |
| `protected internal` | Accessible within the same assembly or derived classes |
| `private protected` | Accessible only within the same assembly and derived classes |

---

## Constructors
Constructors are special methods that initialize new instances of a class.

```csharp
class Car
{
    public string Model;
    public int Year;

    // Default constructor
    public Car()
    {
        Model = "Unknown";
        Year = 0;
    }

    // Parameterized constructor
    public Car(string model, int year)
    {
        Model = model;
        Year = year;
    }
}
```

- If no constructor is defined, a **default constructor** is automatically provided.
- **Constructors cannot return values**.
- **Static constructors** initialize static members and run once per class.

---

## [[Inheritance]]
Classes support **single [[inheritance]]** in C#.

```csharp
class Animal
{
    public void Eat() => Console.WriteLine("Eating...");
}

class Dog : Animal
{
    public void Bark() => Console.WriteLine("Barking...");
}

// Usage
Dog d = new Dog();
d.Eat();  // Inherited from Animal
d.Bark(); // Defined in Dog
```

- Use the `:` symbol to inherit.  
- Derived classes can **override** virtual methods from the base class.

---

## Properties
Properties provide controlled access to class fields.

```csharp
class Person
{
    public string Name { get; set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```

- Auto-implemented properties simplify field encapsulation.  
- The `private set` modifier makes a property read-only outside the class.

---

## Static Members
Static members belong to the **class itself**, not to specific instances.

```csharp
class MathUtils
{
    public static float PI = 3.14159f;

    public static int Square(int x) => x * x;
}

// Usage
Console.WriteLine(MathUtils.PI);
Console.WriteLine(MathUtils.Square(4));
```

- Accessed using the class name (`MathUtils.Square()`).
- Static constructors initialize static members before first use.

---

## Differences Between Class and [[Struct]]

| Feature | Class | Struct |
|----------|--------|--------|
| **Type** | Reference type | Value type |
| **Memory** | Allocated on heap | Allocated on stack |
| **Inheritance** | Supports inheritance | Does not support inheritance |
| **Default Constructor** | Can be defined freely | Cannot be user-defined without parameters |
| **Nullability** | Can be null | Cannot be null (unless nullable) |
| **Copy Behavior** | Copied by reference | Copied by value |

---

## Notes
- Classes support **polymorphism** through `virtual`, `override`, and `abstract` keywords.  
- Marking a class as `sealed` prevents inheritance.  
- Use classes for **complex data structures** or when **object identity** and **shared references** are required.  
- Avoid using classes for small, immutable data — use structs instead.

[[Types]]