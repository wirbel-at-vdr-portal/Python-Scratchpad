[return to index](README.md)

# Reading and writing files

* **open(filename, mode)**
  * **filename** - the file to open or write
  * **mode** - file open modifiers
      * "r" - Read - Default value. Opens a file for reading, error if the file does not exist
      * "a" - Append - Opens a file for appending, creates the file if it does not exist
      * "w" - Write - Opens a file for writing, creates the file if it does not exist
      * "x" - Create - Creates the specified file, returns an error if the file exists
      * "t" - Text - Default value. Text mode
      * "b" - Binary - Binary mode (e.g. images)
* **f.read(size)** - read some amount of data
  * **f** - a file object, see open() 
  * **size** - number of chars or bytes, defaults to all chars or bytes
* **f.readline()** - read a line until '\\n'
* **f.write(string)** - write a string to file
  * **string** - the string to write, append '\\n' for a line.
* **f.tell()** - returns actual file position
* **f.seek(offset, whence)** - set file position
  * **offset** - the new file offset, relativ to reference position
  * **whence** - set the reference position: 0: begin of file (default), 1: current file pos, 2: end of file

[return to index](README.md)
