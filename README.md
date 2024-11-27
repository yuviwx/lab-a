# Lab A - Encoder Program

Welcome to **Lab A**, a simple encoder program written in C. 
This repository contains the implementation of an encoder that processes text character by character, applies a configurable encoding scheme, and outputs the result. 
The project demonstrates command-line argument parsing, character encoding, and file I/O operations in a Linux environment.

---
## **Features**
- **Command-Line Argument Parsing**:
  - Configure encoding schemes dynamically.
  - Enable or disable debug mode.
  - Redirect input and output to files.

- **Character Encoding**:
  - Supports addition and subtraction-based encoding keys.
  - Wrap-around behavior for:
    - Uppercase letters (`A-Z`)
    - Lowercase letters (`a-z`)
    - Digits (`0-9`)

- **File I/O**:
  - Processes input from `stdin` or a specified input file.
  - Outputs encoded text to `stdout` or a specified output file.

- **Debug Mode**:
  - Print program configuration and status messages to `stderr`.

---

## **How to Build**
To compile the program, ensure you have `gcc` installed and simply run 'make'.

```bash
make
```

### **How to Run**

#### **Basic Usage**
```bash
./encoder [options]
```

### **Options**

| **Option**        | **Description**                                                                              |
|--------------------|----------------------------------------------------------------------------------------------|
| `+D`              | Enable debug mode (default).                                                                |
| `-D`              | Disable debug mode.                                                                         |
| `+E<key>`         | Apply addition-based encoding with the specified numeric key (e.g., `+E123`).               |
| `-E<key>`         | Apply subtraction-based encoding with the specified numeric key (e.g., `-E123`).            |
| `-i<filename>`    | Read input from the specified file instead of `stdin`.                                      |
| `-o<filename>`    | Write output to the specified file instead of `stdout`.                                     |

---

### **Examples**

#### **1. Encode Text with a Key**  
Encode the string `"Hello123"` using the key `12`:
```bash
echo "Hello123" | ./encoder +E12
```
#### Output:
```bash
Igmnq234
```

#### **2. Encode and Write to a File**  
Encode `"Hello World!"` using the key `123` and save the result to a file named `output.txt`:
```bash
echo "Hello World!" | ./encoder +E123 -ooutput.txt
```
#### Output in output.txt:
```bash
Igopt Xquoe!
```
#### **3. Read Input from a File**  
Read input from `input.txt`, encode it using the key `123`, and save the output to `output.txt`:
```bash
./encoder +E123 -iinput.txt -ooutput.txt
```
