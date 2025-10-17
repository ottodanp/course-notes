# C# Value Types
Value types in C# are always copied by data, so data is duplicated leading to increased memory usage.
Modifying a copy of a value type will not modify the original, or vice versa.
Value types should always be less than 16 bytes in size and immutable to avoid copying errors.
[[Types]]