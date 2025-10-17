# C# Inheritance

## Overview
**Inheritance** in C# is an **object-oriented programming** feature that allows a [[Class]] to **derive** from another class, enabling code reuse, extension, and polymorphism.  
The **derived (child)** class inherits fields, properties, methods, and other members from the **base (parent)** class, and can also override or extend them.

---

## Key Characteristics
- Enables **code reuse** by inheriting behavior from a base class.
- Supports **hierarchical relationships** between classes.
- Allows **method overriding** to change or extend base functionality.
- A class can inherit from **only one base class** (C# does not support multiple inheritance).
- Can use the `base` keyword to access base class members.
- Supports **abstract classes**, **virtual methods**, and **interfaces** for polymorphism.
- Constructors are **not inherited**, but derived constructors may call base constructors via `base(...)`.

---

## Syntax Example
```csharp
// Base Class
class Animal
{
    public string Name;

    public Animal(string name)
    {
        Name = name;
    }

    public virtual void Speak()
    {
        Console.WriteLine($"{Name} makes a sound.");
    }
}

// Derived Class
class Dog : Animal
{
    public Dog(string name) : base(name) { }

    public override void Speak()
    {
        Console.WriteLine($"{Name} barks!");
    }
}

// Usage
Animal animal = new Animal("Generic Animal");
animal.Speak(); // Output: Generic Animal makes a sound.

Dog dog = new Dog("Rex");
dog.Speak(); // Output: Rex barks!
```

---

## Access Modifiers and Inheritance
| Modifier | Inherited? | Accessible in Derived Class |
|----------|------------|-----------------------------|
| `public` | ✅ Yes | Yes |
| `protected` | ✅ Yes | Yes (within derived class only) |
| `private` | ❌ No | No |
| `internal` | ✅ Yes (if in same assembly) | Yes (same assembly) |
| `protected internal` | ✅ Yes | Yes (derived or same assembly) |
| `private protected` | ✅ Yes (within containing class or derived in same assembly) | Limited |

---

## `base` Keyword
- Used to **call base class constructors** or **access base class methods** and properties.
- When used in a constructor it **must** be the first call.
- Use `base.MethodName()` to call a base implementation from an overriding method.

```csharp
class Vehicle
{
    public Vehicle(string type) => Console.WriteLine($"Vehicle type: {type}");
    public virtual void Start() => Console.WriteLine("Vehicle starting...");
}

class Car : Vehicle
{
    public Car() : base("Car") { }

    public override void Start()
    {
        base.Start(); // Calls Vehicle.Start()
        Console.WriteLine("Car is ready to go!");
    }
}
```

---

## Sealed Classes and Methods
- The `sealed` keyword prevents further inheritance.
- You can seal **classes** or **methods** to stop additional overrides.

```csharp
sealed class FinalClass { } // Cannot be inherited

class Base
{
    public virtual void Run() => Console.WriteLine("Base running...");
}

class Derived : Base
{
    public sealed override void Run() => Console.WriteLine("Derived running...");
}

// Subclassing Derived and overriding Run is not allowed.
```

---

## Abstract Classes and Inheritance
- **Abstract classes** cannot be instantiated directly.
- They may contain **abstract members** (methods, properties) that must be implemented by non-abstract derived classes.
- Use abstract classes to provide a common base with some shared implementation and some required overrides.

```csharp
abstract class Shape
{
    public abstract double GetArea();
}

class Square : Shape
{
    public double Side;
    public Square(double side) => Side = side;
    public override double GetArea() => Side * Side;
}
```

---

## Inheritance vs Interfaces

| Feature | Inheritance | Interface Implementation |
|----------|-------------|----------------------------|
| **Purpose** | Reuse and extend base functionality | Define a contract for behavior |
| **Multiple Allowed** | ❌ Single base class | ✅ Multiple interfaces |
| **Access to Base Members** | Full access via `base` | No base implementation (until default interface methods in C# 8+) |
| **Use Case** | "Is-a" relationship (e.g., Dog is an Animal) | "Can-do" relationship (e.g., Dog can Run) |

---

## When to Use Inheritance
Use inheritance when:
- There is a **clear “is-a” relationship** between classes.
- You need to **reuse common behavior** and extend it.
- **Polymorphism** is required (e.g., working with a base reference to derived objects).
- The base class provides **shared structure or logic** that many derived classes should use or override.

---

## Common Examples
- Framework/base classes that provide shared behavior (e.g., `Controller` base class in ASP.NET MVC).
- GUI control hierarchies where a base `Control` class provides shared rendering/behavior.
- Domain models where a base entity provides common fields/validation.

---

## Notes and Best Practices
- Prefer **composition over inheritance** when possible — composition is often more flexible and less coupled.
- Keep inheritance hierarchies **shallow**; deep hierarchies increase complexity.
- Mark methods `virtual` only when you intend them to be overridden.
- Use `sealed` for performance-critical classes when further inheritance is not needed (the runtime can optimize sealed types).
- Consider interfaces for cross-cutting capabilities (logging, serialization) that many unrelated types may implement.
- Document the intended extension points of your base classes so derived class authors know which members are safe to override.

[[Fundamentals]]