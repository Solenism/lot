# lot
**A faster replacement for vector, but with element construction and destruction on memory reserveration and freeing, rather than on element insertion and deletion. It also allows enabling or disabling range checks independent from compiler debugging settings, and using 32-bit indices on 64-bit system.**

### Requirements

- C++11
- [CMake](https://cmake.org/) (only necessary for running the test)

### Installation

- *lot* is header only. Therefore, simply copy ```includes/mz/lot.h``` into a directory of your choice, and ```#include``` it.
- The namespace is ```std::mz```.

### Tested on

- Windows 10: Visual Studio 2017
- Fedora Linux: Visual Studio Code
 
### Download 

You can download the latest version of *lot* by cloning the GitHub repository:

	git clone https://github.com/Solenism/lot.git
	
### Usage

Take a look at the test file ```test/slot/lot.cpp``` or the header file itself. In general, it supports most methods of ```vector```, including:

- optimized copies, assignments, movement constructors and initializer lists
- auto iterators
- basic functions like clear, reserve, capacity, push_back, etc...

On top of the regular ```vector```, the following methods are also available

- ```Add(*various*)```: A synonym for push_back, but it supports multiple arguments, so multiple elements can be inserted at the same time. It also supports adding another ```lot<>```, by appending all entries.
- ```Take(lot& other)```: Append all elements of ```other```, and clears ```other```.

Unsupported ```vector``` methods:

- insert, emplace, erase
- lexicographic comparisons (==, !=, <, <=, >, >=)
