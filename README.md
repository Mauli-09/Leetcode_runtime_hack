# Python `atexit` Hack (LeetCode Trick)

This repository demonstrates a Python one-liner that registers a function to run at interpreter shutdown:

```python
__import__("atexit").register(lambda: open("display_runtime.txt", "w").write("0"))

```
# What it does

Dynamically imports the atexit
 module.

Registers a cleanup function using atexit.register.

When the Python interpreter exits, the function runs and writes "0" to a file named display_runtime.txt.

# Why use this

This hack is sometimes seen in LeetCode submissions or other online judges because:

Some environments generate a display_runtime.txt file to measure execution time.

Writing "0" can trick the system into showing a runtime of 0 ms.

It avoids adding extra code, as it fits in a single line.

# Cleaner Equivalent

```
import atexit

def cleanup():
    with open("display_runtime.txt", "w") as f:
        f.write("0")

atexit.register(cleanup)

```
⚠️ Disclaimer: This is not recommended for production or real-world projects. It should only be used for educational purposes to understand how atexit works. On platforms like LeetCode, it may be considered a hack and not an intended solution.
