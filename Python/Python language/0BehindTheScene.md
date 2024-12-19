Python is not directly compiled into machine code like C or C++. Instead, Python code goes through the following stages:

1.. Source Code:
You write Python code in `.py` files (human-readable).

2.. **Compilation to Bytecode**:
- Python **compiles** the source code into an intermediate representation called **bytecode**.
- Bytecode is a low-level, platform-independent set of instructions stored in `.pyc` files (in the `__pycache__` directory). 
- Bytecode is not a machine code.
- This step happens automatically when you run a Python script.
- **Tools**: The `py_compile` module can explicitly compile `.py` files into `.pyc`.

3.. **Interpretation by the Python Virtual Machine (PVM)**:
- The **Python Virtual Machine (PVM)** reads the bytecode and executes it.
- The PVM is part of the **CPython interpreter**, the most widely used implementation of Python.

![[Pasted image 20241219091828.png]]

#### What Happens When You Run a Script?
1. **Parsing**:
    - Python parses the script to check for syntax errors.
2. **Compilation**:
    - The script is compiled into bytecode (`example.pyc`).
3. **Execution**:    
    - The bytecode is interpreted by the PVM, which executes the `print` function.
4. **Output**:
    - The PVM sends the output to the console: `Hello, World!`.

#### Key Components of Python's Runtime:
##### a. Interpreter (CPython)

- CPython is the default implementation of Python, written in C.
- It includes:
    - A compiler (to convert source code to bytecode).
    - A bytecode interpreter (to execute bytecode).
- Other implementations:
    - **PyPy**: A Python interpreter with Just-In-Time (JIT) compilation for faster performance.
    - **Jython**: Python for the Java Virtual Machine (JVM).
    - **IronPython**: Python for the .NET framework.

##### b. Global Interpreter Lock (GIL)

- The **GIL** ensures that only one thread executes Python bytecode at a time in CPython, even on multi-core processors.
- This simplifies memory management but limits multithreading performance for CPU-bound tasks.


#### Memory Management in Python
Python uses a sophisticated memory management system that includes:
##### a. Reference Counting

- Every object in Python has a **reference count**.
- When the reference count drops to zero, the memory is automatically deallocated.

##### b. Garbage Collection:

- Python uses a **garbage collector** to reclaim memory from objects involved in circular references.
- **Generational Garbage Collection**: Objects are grouped into generations (young, middle-aged, and old), and younger objects are collected more frequently.

##### c. Memory Pooling:

- Python uses a memory allocator (`PyMalloc`) to optimize memory usage for small objects like integers and strings.


#### 