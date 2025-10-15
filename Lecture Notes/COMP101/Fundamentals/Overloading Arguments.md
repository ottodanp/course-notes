# Method Overloading in C#

## Overview
**Method overloading** (also known as **[[Arguments]] overloading**) allows multiple methods in the same class to share the same name but differ in their **parameter lists**.  
This feature enables more readable and flexible code by allowing the same method name to handle different input types or numbers of arguments.

---

## Rules for Overloading
A method is considered **overloaded** if:
- It has the **same method name**, and  
- **Different parameters** (in one or more of the following ways):
  - Different **number** of parameters  
  - Different **types** of parameters  
  - Different **order** of parameters (if types differ)

The **return type** alone **cannot** be used to distinguish overloaded methods.

---

## Example

```csharp
public class Calculator
{
    // Overload 1: Two integer parameters
    public int Add(int a, int b)
    {
        return a + b;
    }

    // Overload 2: Three integer parameters
    public int Add(int a, int b, int c)
    {
        return a + b + c;
    }

    // Overload 3: Two double parameters
    public double Add(double a, double b)
    {
        return a + b;
    }
}
```

Usage:
```csharp
Calculator calc = new Calculator();
int sum1 = calc.Add(2, 3);        // Calls first overload
int sum2 = calc.Add(1, 2, 3);     // Calls second overload
double sum3 = calc.Add(2.5, 3.7); // Calls third overload
```

---

## Key Points
- Overloading improves **code clarity** and **reusability**.  
- The compiler determines which method to call at **compile time** (this is **static polymorphism**).  
- Optional parameters can sometimes reduce the need for multiple overloads.  
- Overloaded methods can **coexist** with methods inherited from a base class (unless hidden or overridden).

---

## Common Pitfalls
- Changing only the **return type** is **not valid** for overloading.  
- Ambiguity can occur if parameter conversions make it unclear which overload to use.  
- Excessive overloading can reduce readability; use it judiciously.
[[Fundamentals]]