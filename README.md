# Memory Manipulation DLL Library

## Overview

This is a DLL library created for memory manipulation tasks. It provides functionality to read from and write to memory, including the ability to handle strings and integers using memory addresses. This library is intended for personal use only and may not be redistributed or used for commercial purposes.

## Features

- **Read and Write Strings**: Allows you to read from and write strings to specific memory addresses.
- **Read and Write Integers**: Enables reading from and writing integers to specified memory addresses.
- **Read and Write Floats**: Supports reading from and writing float values to specified memory addresses.
- **Read and Write Doubles**: Supports reading from and writing double values to specified memory addresses.
- **Read and Write Booleans**: Enables reading from and writing boolean values to specified memory addresses.

## Usage

### Importing the DLL

To use this library in your project, you need to import the DLL into your C# application. Here’s a sample code snippet on how to import and use the functions provided by the library:

```csharp
using MemoryLibX;
// using System.Diagnostics;

namespace MemoryTest
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // YOU CAN ALSO GET PID USING PROCESS NAME LIKE BELOW:
            //   Process process = Process.GetProcessByName("process_name")[0];
            //   Memory memory = new Memory(process.Id);

            Memory memory = new Memory(1050 /* PID of the process */);
            memory.BindProcess();

            string str = "Hello, World!";

            memory.WriteStringToMemory(0x0138C15 /* address */, str /* your string */, 16 /* allocation size */);
        }
    }
}

```
