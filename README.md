# Discovering vulnerabilities in Python Applications with a Static Analyzer tool
## Problem
Our main goal with this tool was to create a securely sound application that statically analyzed Python programs in order to detect implicit and explicit vulnerabilities that could be used to compromise the integrity and confidentiality of information.

A large class of vulnerabilities in applications originates in programs that enable user input information to affect the values of certain parameters of security-sensitive functions. In other words, these programs encode a potentially dangerous information flow, in the sense that low integrity -- tainted -- information (user input) may interfere with high integrity parameters of sensitive functions or variables (so called sensitive sinks). This means that users are given the power to alter the behavior of sensitive functions or variables, and in the worst case may be able to induce the program to perform security violations. For this reason, such flows can be deemed illegal for their potential to encode vulnerabilities.

## Run the tool
There is a folder "slices" that, for each test, has three files, the slice to be analyzed, the patterns to use to detect vulnerabilities, and the output expected.

So, in order to run the program you should perform
```bash
python py_analyzer.py slices/<slice_file.py> slices/<patterns_file.json>
```
After this, check the actual output in the folder "output"

## Details
Note that the main logic of the program is implemented in the file "classes/nodes.py" where each node of the AST tree used is recursively implemented.

## Limitations
The last tests (7, 8, and 9) have the purpose of testing advanced detection for implicit flows, but because of time limits, this logic was not implemented.
