### Basics
Arguments are values accepted into a function/method, and work effectively as variables.

### Default Arguments
Default arguments in C# work effectively the same as in Python
```C#
void SomeFunc(int a = 1, int b = 2) 
{
	return a + b
}

SomeFunc(); // calls SomeFunc(1, 2)
SomeFunc(3, 4) // overrides default arguments
```

[[Fundamentals]]