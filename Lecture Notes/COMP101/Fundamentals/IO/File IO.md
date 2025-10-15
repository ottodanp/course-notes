### Creating a File
```C#
File.CreateText("path.ext"); // returns a System.IO.StreamWriter and creates the file if it doesn't exist
```
### Writing to a File
```C#
StreamWriter file = new StreamWriter("file.txt");
file.WriteLine("hi"); // Writes a line to a file
file.Flush();
file.Close(); 
```
### Reading From a File
```C#
try { 
	// Open the text file using a stream reader. 
	using StreamReader reader = new("TestFile.txt"); 
	// Read the stream as a string. 
	string text = reader.ReadToEnd(); 
	// Write the text to the console. 
	Console.WriteLine(text); 
} catch (IOException e) 
{ 
	Console.WriteLine("The file could not be read:"); 
	Console.WriteLine(e.Message); 
}
```

[[IO]]