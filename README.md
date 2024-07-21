# Memory Manipulation DLL Library

## Overview

This is a DLL library created for memory manipulation tasks. It provides functionality to read from and write to memory, including the ability to handle strings and integers using memory addresses. This library is intended for personal use only and may not be redistributed or used for commercial purposes.

## Features

- **Read and Write Strings:** Allows reading and writing strings to specified memory addresses.
- **Read and Write Integers:** Enables reading and writing integer values from/to specified memory addresses.

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
