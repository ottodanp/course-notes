# File IO
File.CreateText("path.ext") // returns a System.IO.StreamWriter and creates the file if it doesn't exist
StreamWriter.WriteLine()

### File locking
if you open a file, and another program tries to open the same file, issues may happen - so close files when done with them 

### Default arguments
default args work the same as python
static void DoThing(int arg1, int arg2 = 10) {}
arg2 has default value of 10 
calling DoThing(5) : arg1 = 5, arg2 = 10
calling DoThing(5, 5) : arg1 = 5, arg2 = 5

### Formatted Strings
either $"asd {variable}" or ("asd {0:D}", variable)

### Overloading arguments
you may have two versions of the same function with different input types, and the function run can be decided based on the types of the given input
This does not work for return types, functions with the same input args and same name are not allowed

### Flushing
important when reading and writing to the same file in the same program / when writing networking code to avoid hanging the active thread waiting for network action to happen

### Defining arrays
Lists are defined using the type and square brackets, and the length of the list e.g.:
`int[] num = new int[40]`

