# Programming-in-C
Okay, here are the detailed notes based on the provided PowerPoint slides, organized by lecture number.

---

## Lecture 1: Introduction - Part I (July 31, 2024)

**Topic:** Introduction to C Programming

**1. Why Learn Programming Languages (PL)?**
    *   **Interaction with Machines (Computers):** Humans need a way to give instructions to computers.
    *   **Problem Solving:** Computers excel at complex calculations and repetitive tasks much faster and more accurately than humans (e.g., large multiplications, route finding).
    *   **Automation:** Create programs (sequences of instructions) to automate tasks (e.g., Google Maps finding a route, ATM dispensing cash).
    *   **Computers are "Dumb":** They only follow instructions precisely as given.

**2. Levels of Programming Languages:**
    *   **Machine Language (0s and 1s):** Directly understood by the computer's hardware. Very difficult for humans to read, write, or debug. Prone to errors (mistakenly flipping a bit).
    *   **Assembly Language:** Uses mnemonics (like ADD, MOV, SUB) which are more human-readable than binary. Requires an *Assembler* to translate it into machine code. Still machine-dependent and low-level.
    *   **High-Level Languages (HLL):** (e.g., C, C++, Java, Python) Use English-like words and syntax (e.g., `a + b`). Much easier for humans to write, read, and maintain. Requires a *Translator* (Compiler or Interpreter) to convert to machine code. Logic is transferable across different HLLs.

**3. Why C Programming Specifically?**
    *   Foundation for many other languages (C++, Java, C#).
    *   Used extensively in system programming (Operating Systems, Compilers, Embedded Systems).
    *   Provides low-level memory access capabilities.
    *   Efficient and performs well.

**4. Course Structure (Approximate Lecture Allocation):**
    *   Data Types and Operators: 6-7 Lectures
    *   Control Flow Statements: 6 Lectures
    *   Functions & Storage Classes: 5 Lectures
    *   Arrays & Pointers: 10 Lectures
    *   Strings: 2 Lectures
    *   Structure, Union: 2 Lectures
    *   Miscellaneous Topics: 1 Lecture (Preprocessor, etc.)
    *   *Total: ~32-33 Lectures*

**5. Basic Requirements for Programming:**
    *   **Need to Learn a PL:** Understand its syntax and grammar (like learning English grammar).
    *   **Write Programs:** Create sequences of instructions following the PL's rules.
    *   **Translator:** Use a Compiler (like GCC for C) or Interpreter to convert the human-readable program (source code) into machine-readable code (executable).
    *   **Input/Output:** Programs need to interact - take input (e.g., from keyboard) and produce output (e.g., to screen).
    *   **Interface/Abstraction:** Hiding complex implementation details (e.g., how `printf` actually displays text on screen) allows programmers to focus on the logic.

**6. Tools Needed:**
    *   **C-Related Software:** (e.g., Turbo C, Dev C++, VS Code with C extension, GCC)
    *   This software typically includes:
        *   **Compiler:** Translates C code to machine code.
        *   **Library:** Pre-written code for common functions (like `printf` in `stdio.h`).

**7. Key Concepts Introduced:**
    *   **Program:** A sequence of instructions written in a PL.
    *   **Compiler/Interpreter:** Translators from HLL to machine code.
    *   **Library:** Collection of pre-defined functions. `#include <stdio.h>` brings in the Standard Input/Output library.
    *   **Variable:** A named container to store data that can vary (change). Has an address (location in memory), a label (identifier/name), and holds data.
    *   **Identifier:** The name given to a variable, function, etc.
    *   **Data:** The information processed by a program (Numeric, Textual).
    *   **Data Type:** Specifies the kind of data a variable can hold (e.g., integer, character, floating-point) and the operations that can be performed on it.

**8. Course Logistics:**
    *   Timings mentioned: 4:00 PM - 5:30 PM, 5:30 PM - 6:30 PM, 5 PM - 10 PM (Context unclear, likely related to different batches or subjects).
    *   C and DS (Data Structures) ~ 10 Marks (presumably in GATE).
    *   CDSA (Compiler Design, System Software, Architecture?) ~ 18-72 Marks (Range seems very wide, needs clarification).

---

## Lecture 2: Introduction - Part II (Aug 1, 2024)

**Topic:** Introduction - II (Variables, Data Types, Identifiers)

**1. Essential Programming Language Facilities:**
    *   Take input (e.g., from keyboard).
    *   Display output (e.g., to screen).

**2. User vs. Programmer:**
    *   **User:** Interacts with the application's interface (e.g., buttons, text boxes on an ATM). Doesn't need to know the underlying programming.
    *   **Programmer:** Writes the set of programs (code) that make the application work. Needs to understand the PL.
    *   **Abstraction:** Hiding implementation details from the user (and often from other programmers using a module) is crucial.

**3. Software and File Types:**
    *   Different software is used to create different file types (PowerPoint -> .pptx, MS Word -> .doc).
    *   C programs (.c files) require C-related software (Compiler + Libraries) like Turbo C, Dev C, VS Code, Code::Blocks.

**4. Compiler and Library:**
    *   **Compiler:** Translates the `.c` source file into machine code.
    *   **Library:** Contains pre-written, pre-compiled code for standard functions (e.g., `printf`, `scanf`). The `#include <stdio.h>` directive tells the compiler to include information about the standard input/output library, allowing the use of functions like `printf`.

**5. Variables:**
    *   **Concept:** Named memory locations used to store data that can change during program execution. Like containers (Tea, Rice, Sugar).
    *   **Analogy:** Retrieving items from storage requires knowing *where* they are. In memory, we need a way to refer to data locations.
    *   **Identifier:** The name given to a variable (e.g., `a`, `sum`, `userName`). It acts as a label for the memory location.
    *   **Address:** The actual memory location where the data is stored (e.g., 1048, 2186). Usually handled by the compiler/system.
    *   **Data:** The value stored in the variable (e.g., 10, 3.14, 'c').

**6. Data:**
    *   Information processed by computers.
    *   Can be broadly categorized:
        *   **Numeric:** Numbers.
            *   Without decimal point (Integers: 12, -12, 0).
            *   With decimal point (Floating-point: 9.8, -9.8, 0.0).
        *   **Text:** Characters, strings, addresses, email, names. (Internally represented numerically, e.g., using ASCII).

**7. Data Types:**
    *   Tells the compiler:
        *   What kind of data a variable will hold (e.g., integer, float, character).
        *   How much memory to allocate for it.
        *   What operations are valid for that data.
    *   **Categories in C:**
        *   **Primitive:** Basic types built into the language.
            *   Integer types (`short`, `int`, `long`, `long long` - signed/unsigned)
            *   Character type (`char` - signed/unsigned)
            *   Floating-point types (`float`, `double`, `long double`)
            *   Void (`void`) - Represents the absence of a type.
            *   Boolean (`_Bool` or `bool` via `stdbool.h`) - Though often integers (0/1) are used.
        *   **Derived:** Constructed from primitive types.
            *   Arrays
            *   Pointers
            *   Strings (Arrays of characters)
        *   **User-Defined:** Defined by the programmer.
            *   Structure (`struct`)
            *   Union (`union`)
            *   Typedef (`typedef`)
            *   Enumeration (`enum`)

**8. Integer Data Types:**
    *   Used to store whole numbers (+ve, -ve, 0).
    *   Variations: `short int`, `int`, `long int`, `long long int`. These differ in the range of values they can store (and potentially the memory size they occupy, though this can be system-dependent).
    *   **Modifiers:**
        *   `signed`: Can store positive, negative, and zero (this is the default for `int` types).
        *   `unsigned`: Can store only non-negative values (zero and positive).

**9. Number Systems & Memory:**
    *   **Decimal (Base 10):** Uses digits 0-9.
    *   **Binary (Base 2):** Uses digits 0-1. Computers store data in binary.
        *   1 bit (binary digit) can be 0 or 1 (2 possible values).
        *   1 byte = 8 bits -> 2⁸ = 256 possible values.
    *   **Range:**
        *   **Unsigned n-bit:** 0 to 2ⁿ - 1
        *   **Signed n-bit (2's complement):** -2ⁿ⁻¹ to +2ⁿ⁻¹ - 1
    *   **Example (Assuming 16-bit `int`):**
        *   `unsigned int`: 0 to 65535 (2¹⁶ - 1)
        *   `signed int`: -32768 to +32767 (-2¹⁵ to +2¹⁵ - 1)
    *   **Example (Assuming 32-bit `int`):**
        *   `unsigned int`: 0 to 2³² - 1 (~4 billion)
        *   `signed int`: -2³¹ to +2³¹ - 1 (~ -2 billion to +2 billion)

**10. `printf` Function:**
    *   Used to display output on the screen.
    *   `printf("text");` - Prints the literal text.
    *   `printf("format_specifier", variable);` - Prints the value of the variable according to the format specifier.
        *   `%d` or `%i`: Signed integer.
        *   `%u`: Unsigned integer.
        *   `%ld`: Long signed integer.
        *   `%lld`: Long long signed integer.
        *   `%c`: Character.
        *   `%f`: Float / Double.
        *   `%s`: String.
        *   `%p`: Pointer address.
    *   `printf("Text %d more text %d", var1, var2);` - Embeds variable values within text.

---

## Lecture 3: Introduction - Part III (Aug 2, 2024)

**Topic:** Data Types (Integer types, `printf`, `scanf`, Character types)

**1. Data Types Recap:**
    *   **Primitive:** Integer, Character, Floating Point, Void, Boolean.
    *   **Derived:** Arrays, Pointers, Strings.
    *   **User-Defined:** Struct, Union, Typedef, Enum.

**2. Integer Types (`int`, `short`, `long`, `long long`):**
    *   Store whole numbers.
    *   Can be `signed` (default) or `unsigned`.
    *   Size (and thus range) can vary by system/compiler but C standard guarantees minimum ranges and relative sizes (`short` <= `int` <= `long` <= `long long`).

**3. Range Examples (Assuming 2-byte `int`):**
    *   `unsigned int`: 0 to 65535
    *   `signed int`: -32768 to +32767
    *   **Wrap-around:** If you exceed the maximum value, it wraps around (e.g., `unsigned int i = 65535; i++;` might result in `i` being 0). If you go below the minimum, it wraps the other way (e.g., `signed int i = -32768; i--;` might result in `i` being 32767).
    *   **Format Specifiers:** `%d` for signed int, `%u` for unsigned int. Using the wrong specifier can lead to unexpected output when values are near the range boundaries.
        *   `unsigned int i = -2; printf("%u", i);` -> Prints 65534 (assuming 2-byte int). The bit pattern for -2 (in 2's complement) is interpreted as a large unsigned number.
        *   `signed int i = 32768; printf("%d", i);` -> Prints -32768. The bit pattern for 32768 (which requires 16 bits if the sign bit is included) is interpreted as the most negative signed number.

**4. `scanf` Function:**
    *   Used to read formatted input from the keyboard.
    *   Syntax: `scanf("format_specifier", &variable_address);`
    *   Requires the **address** of the variable (using the `&` address-of operator) to know where in memory to store the input value.
    *   Input from the keyboard is initially a sequence of characters; `scanf` converts it based on the format specifier and stores it.

**5. Character Data Type (`char`):**
    *   Typically used to store single characters (like 'A', 'z', '!', '?').
    *   Size: Usually 1 byte (8 bits).
    *   Range (1 byte):
        *   `unsigned char`: 0 to 255
        *   `signed char`: -128 to +127 (Default `char` can be signed or unsigned depending on the compiler/system).
    *   **Internal Representation:** Characters are stored as integer values based on a character encoding system (commonly ASCII).
        *   ASCII 'A' = 65, 'B' = 66, ..., 'a' = 97, 'b' = 98, ..., '0' = 48, '1' = 49, ...
    *   **`printf` with `char`:**
        *   `%d`: Prints the integer (ASCII) value. `char c = 'A'; printf("%d", c);` -> Prints 65.
        *   `%c`: Prints the corresponding character symbol. `char c = 65; printf("%c", c);` -> Prints A.
    *   **Wrap-around Example (`signed char`):**
        *   `char c = 128; printf("%d", c);` -> Prints -128. (128 wraps around past +127).
        *   `char c = 132; printf("%d", c);` -> Prints -124. (132 wraps around).
        *   `char c = -191; printf("%c", c);` -> Prints 'A'. (-191 wraps around, `256 - 191 = 65`, which is ASCII 'A').

**Code Example: `printf` and `scanf`**
```c
#include <stdio.h>

int main() {
    int a, b, sum;

    // Prompt user for the first number
    printf("Enter First number: ");
    // Read the first number from keyboard and store it in variable 'a'
    scanf("%d", &a); // Note the '&' to pass the address of 'a'

    // Prompt user for the second number
    printf("Enter second number: ");
    // Read the second number from keyboard and store it in variable 'b'
    scanf("%d", &b); // Note the '&' to pass the address of 'b'

    // Calculate the sum
    sum = a + b;

    // Print the result
    // %d is replaced by the value of 'a', the second %d by 'b', the third %d by 'sum'
    printf("The sum of %d and %d is %d\n", a, b, sum);

    return 0; // Indicate successful execution
}
```
**How to Run:**
1.  Save the code in a file named `sum.c`.
2.  Compile using a C compiler (like GCC): `gcc sum.c -o sum`
3.  Run the executable: `./sum` (on Linux/macOS) or `sum.exe` (on Windows).
4.  The program will prompt you to enter two numbers. Type a number and press Enter after each prompt.

---

## Lecture 4: Data Types & Operators (Aug 5, 2024)

**Topic:** Data Types (Format Specifiers, Escape Sequences), Operators (Introduction)

**1. `printf` Format Specifiers (Review/Expansion):**
    *   `%d`, `%i`: Signed integer.
    *   `%u`: Unsigned integer.
    *   `%ld`: Long signed integer.
    *   `%lld`: Long long signed integer.
    *   `%c`: Character.
    *   `%f`: Floating-point (`float`, `double`).
    *   `%lf`: Long double (often used, though `%f` usually works for `double` in `printf`).
    *   `%s`: String (char *).
    *   `%p`: Pointer address.
    *   `%%`: To print a literal '%' sign.

**2. Escape Sequences:**
    *   Special character combinations starting with `\` used within strings/character literals to represent characters that are difficult or impossible to type directly or have special meaning.
    *   `\n`: **Newline.** Moves the cursor to the beginning of the next line.
    *   `\t`: **Horizontal Tab.** Moves the cursor to the next tab stop (often every 8 columns, but can vary). Used for alignment.
        *   Tab stops are typically at columns 1, 9, 17, 25, etc. `\t` moves to the *start* of the next available frame/stop.
    *   `\b`: Backspace.
    *   `\r`: Carriage Return. Moves cursor to the beginning of the current line.
    *   `\\`: Backslash (`\`).
    *   `\'`: Single quote (`'`).
    *   `\"`: Double quote (`"`).
    *   `\0`: Null character (used to terminate strings).

**Code Example: Escape Sequences**
```c
#include <stdio.h>

int main() {
    // Without \n
    printf("Hello Everyone.");
    printf("How are you?");
    printf("\n---\n"); // Separator

    // With \n
    printf("Hello Everyone.\n");
    printf("How are you?\n");
    printf("---\n");

    // With \t
    printf("Hello\tPankaj\n"); // Moves to next tab stop after Hello
    printf("Welcome\tsir\n");  // Moves to next tab stop after Welcome
    printf("PankajJi\tMast hain\n"); // Moves to next tab stop after PankajJi

    // Other examples
    printf("This is a backslash: \\ \n");
    printf("This is a double quote: \" \n");
    printf("This is a single quote: \' \n");

    return 0;
}
```
**Output:**
```
Hello Everyone.How are you?
---
Hello Everyone.
How are you?
---
Hello   Pankaj
Welcome sir
PankajJi        Mast hain
---
This is a backslash: \
This is a double quote: "
This is a single quote: '
```

**3. Operators:**
    *   Symbols that perform operations on data (operands).
    *   **Operand:** The data on which an operator acts.
    *   **Types based on number of operands:**
        *   **Unary:** Operates on one operand (e.g., `-7`, `+10`, `!isValid`). The `-` in `-7` is a unary minus operator.
        *   **Binary:** Operates on two operands (e.g., `10 + 20`, `a * b`, `x > y`). The `+` is a binary addition operator.
        *   **Ternary:** Operates on three operands (e.g., `condition ? value_if_true : value_if_false`). C has one ternary operator (`?:`).
    *   **Expression:** A combination of variables, constants, operators, and function calls that evaluates to a single value (e.g., `10 + 2`, `a * b / 2`, `isValid && count > 0`).
    *   **Statement:** A complete unit of execution. Often ends with a semicolon (`;`).
        *   Declaration statement: `int a;`
        *   Assignment statement: `a = 20;`
        *   Expression statement: `10 + 2;` (Evaluates to 12, but the value is discarded. Legal but often not useful unless it has side effects like `i++;`). `a = 20;` is also an expression statement where the expression has the side effect of assignment.

**4. Assignment Operator (`=`):**
    *   Binary operator.
    *   Syntax: `LHS = RHS;`
    *   **LHS (Left Hand Side):** Must be a modifiable *lvalue* (typically a variable, representing a memory location).
    *   **RHS (Right Hand Side):** Can be a constant, variable, or expression.
    *   **Action:** Evaluates the RHS and stores the resulting value into the memory location represented by the LHS.
    *   **Lvalue:** An expression that refers to a memory location (locator value). Variables are lvalues. Constants (like `10`) or complex expressions (like `a+b`) are generally *not* lvalues. You cannot write `10 = a;` or `a + b = c;`.

---

## Lecture 5: Data Types & Operators - Part II (Aug 6, 2024)

**Topic:** Operators (Arithmetic, Relational, Logical), Operator Precedence & Associativity

**1. Arithmetic Operators:**
    *   `+` (Addition), `-` (Subtraction), `*` (Multiplication), `/` (Division), `%` (Modulus/Remainder).
    *   Unary `+`, Unary `-`.
    *   **Priority/Precedence:** Determines the order of operations.
        *   High: `*`, `/`, `%`
        *   Low: `+`, `-`
        *   Unary `+`, `-` have higher precedence than binary `*`, `/`, `%`.
    *   **Associativity:** Determines the order when operators have the same precedence.
        *   `*`, `/`, `%`: Left-to-Right (LtoR) -> `8 / 4 * 2` is `(8 / 4) * 2 = 2 * 2 = 4`.
        *   `+`, `-`: Left-to-Right (LtoR) -> `10 - 5 + 2` is `(10 - 5) + 2 = 5 + 2 = 7`.
        *   Unary `+`, `-`: Right-to-Left (RtoL).
        *   Assignment (`=`): Right-to-Left (RtoL) -> `a = b = c = 4;` is `a = (b = (c = 4));`. `c` gets 4, then `b` gets the result of `(c=4)` which is 4, then `a` gets the result of `(b=4)` which is 4.
    *   **Integer Division:** If both operands of `/` are integers, the result is an integer (fractional part is truncated). `7 / 2` is `3`.
    *   **Floating-Point Division:** If *at least one* operand is a floating-point type, the result is floating-point. `7.0 / 2`, `7 / 2.0`, `7.0 / 2.0` all result in `3.5`.
    *   **Modulus (`%`):**
        *   Gives the remainder of an integer division. `12 % 5` is `2`.
        *   **Operands MUST be integers.** `12.0 % 5` or `12 % 5.0` will result in a compiler error.
        *   The sign of the result usually matches the sign of the first operand (dividend), but this can be implementation-defined in older C standards (C99 onwards specifies it matches the dividend).

**2. `printf` Return Value:**
    *   `printf` returns the number of characters successfully printed to the screen.
    *   `int i = printf("Pankaj");` -> Prints "Pankaj" and assigns `6` to `i`.

**Code Example: `printf` Return Value**
```c
#include <stdio.h>

int main() {
    int i;
    int a;

    i = printf("Pankaj"); // Prints Pankaj, i becomes 6
    printf("\nValue of i: %d\n", i); // Prints Value of i: 6

    // Nested printf
    // 1. Inner printf("Gate2026") executes: Prints Gate2026, returns 8
    // 2. Outer printf("%d", 8) executes: Prints 8, returns 1 (length of "8")
    printf("\n---\n");
    printf("%d", printf("Gate2026"));
    printf("\n---\n");

    // Nested printf assigned to 'a'
    // 1. Innermost printf("Gate2026") -> Prints Gate2026, returns 8
    // 2. Middle printf("%d", 8) -> Prints 8, returns 1
    // 3. Outermost printf("%d", 1) -> Prints 1, returns 1
    // 4. Assignment: a = 1
    a = printf("%d", printf("%d", printf("Gate2026")));
    printf("\nValue of a: %d\n", a); // Prints Value of a: 1

    return 0;
}
```
**Output:**
```
Pankaj
Value of i: 6

---
Gate20268
---
Gate202681
Value of a: 1
```

**3. Relational Operators:**
    *   Used to compare two values. Result is either `1` (true) or `0` (false).
    *   `<` (Less than), `>` (Greater than), `<=` (Less than or equal to), `>=` (Greater than or equal to), `==` (Equal to), `!=` (Not equal to).
    *   **Precedence:**
        *   High: `<`, `>`, `<=`, `>=` (LtoR associativity)
        *   Low: `==`, `!=` (LtoR associativity)
    *   Relational operators have lower precedence than arithmetic operators. `a + b > c - d` is `(a + b) > (c - d)`.

**4. Logical Operators:**
    *   Used to combine or modify logical (true/false) values. Operands are typically treated as true if non-zero and false if zero. Result is `1` (true) or `0` (false).
    *   `&&` (Logical AND): Binary. Result is `1` if *both* operands are non-zero (true), otherwise `0`.
    *   `||` (Logical OR): Binary. Result is `1` if *at least one* operand is non-zero (true), otherwise `0`.
    *   `!` (Logical NOT): Unary. Result is `1` if the operand is zero (false), and `0` if the operand is non-zero (true).
    *   **Precedence:**
        *   High: `!` (Unary, RtoL)
        *   Medium: `&&` (Binary, LtoR)
        *   Low: `||` (Binary, LtoR)
    *   Logical operators generally have lower precedence than relational operators. `a > b && c < d` is `(a > b) && (c < d)`.

---

## Lecture 6: Data Types & Operators - Part III (Aug 7, 2024)

**Topic:** Operators (Logical cont., Bitwise, Ternary), Short-Circuit Evaluation, Pre/Post Increment/Decrement

**1. Logical Operators (Continued):**
    *   **Short-Circuit Evaluation:**
        *   **`&&` (Logical AND):** If the *first* operand evaluates to false (0), the result is guaranteed to be false (0), so the *second* operand is **not evaluated**.
        *   **`||` (Logical OR):** If the *first* operand evaluates to true (non-zero), the result is guaranteed to be true (1), so the *second* operand is **not evaluated**.
        *   This is important when the second operand has side effects (like function calls or increment/decrement).

**Code Example: Short-Circuit Evaluation**
```c
#include <stdio.h>

int main() {
    int a = 0, b = 5;
    int result;

    // Example 1: && with first operand false
    printf("Before &&: a=%d, b=%d\n", a, b);
    result = (a == 1) && (++b > 5); // a==1 is false, ++b is NOT evaluated
    printf("After &&: a=%d, b=%d, result=%d\n", a, b, result); // b remains 5

    printf("---\n");

    // Example 2: || with first operand true
    a = 1; b = 5;
    printf("Before ||: a=%d, b=%d\n", a, b);
    result = (a == 1) || (++b > 5); // a==1 is true, ++b is NOT evaluated
    printf("After ||: a=%d, b=%d, result=%d\n", a, b, result); // b remains 5

    return 0;
}
```
**Output:**
```
Before &&: a=0, b=5
After &&: a=0, b=5, result=0
---
Before ||: a=1, b=5
After ||: a=1, b=5, result=1
```

**2. Increment (`++`) and Decrement (`--`) Operators:**
    *   Unary operators that modify their operand (must be a variable/lvalue).
    *   **Pre-increment (`++var`):** Increments the variable *before* its value is used in the expression. Returns the *incremented* value.
    *   **Post-increment (`var++`):** Increments the variable *after* its value is used in the expression. Returns the *original* value (before increment).
    *   **Pre-decrement (`--var`):** Decrements the variable *before* its value is used. Returns the *decremented* value.
    *   **Post-decrement (`var--`):** Decrements the variable *after* its value is used. Returns the *original* value.

**Code Example: Increment/Decrement**
```c
#include <stdio.h>

int main() {
    int a = 5, b;

    // Pre-increment
    b = ++a; // a becomes 6, b becomes 6
    printf("Pre-increment: a=%d, b=%d\n", a, b); // Output: 6 6

    // Post-increment
    a = 5; // Reset a
    b = a++; // b becomes 5 (original value of a), a becomes 6
    printf("Post-increment: a=%d, b=%d\n", a, b); // Output: 6 5

    // Sequence Points & Undefined Behavior:
    // Expressions like i = ++i + ++i + i++; or a = a++;
    // result in UNDEFINED BEHAVIOR in C/C++. The order of evaluation
    // and side effects between sequence points is not guaranteed.
    // Avoid modifying the same variable multiple times without an intervening
    // sequence point (like ';', '&&', '||', '?:', ',').
    // int i = 5;
    // i = ++i + i++; // Undefined behavior - Don't do this!
    // printf("%d\n", i); // Output is unpredictable

    return 0;
}
```

**3. Operator Precedence & Associativity (Summary Table Snippet):**

| Precedence | Operator        | Associativity |
| :--------- | :-------------- | :------------ |
| Highest    | `()` `[]` `.` `->` | L to R        |
|            | `++` `--` `!` `~` (Unary `+` `-`) `*` (deref) `&` (addr) `sizeof` `(type)` | R to L        |
|            | `*` `/` `%`       | L to R        |
|            | `+` `-`         | L to R        |
|            | `<<` `>>`       | L to R        |
|            | `<` `<=` `>` `>=` | L to R        |
|            | `==` `!=`       | L to R        |
|            | `&` (Bitwise AND) | L to R        |
|            | `^` (Bitwise XOR) | L to R        |
|            | `|` (Bitwise OR)  | L to R        |
|            | `&&` (Logical AND)| L to R        |
|            | `||` (Logical OR) | L to R        |
|            | `?:` (Ternary)    | R to L        |
|            | `=` `+=` `-=` `*=` `/=` `%=` `&=` `^=` `|=` `<<=` `>>=` | R to L        |
| Lowest     | `,` (Comma)      | L to R        |

*(Note: This is a simplified table. Refer to a C standard reference for the full, precise table).*

**4. Problem Solving Examples (Illustrative):**

*   `a = 30 > 12 < 1 > 4 < 60 == 2;`
    *   Associativity of `< > <= >=` is L to R.
    *   `(30 > 12)` -> 1
    *   `(1 < 1)` -> 0
    *   `(0 > 4)` -> 0
    *   `(0 < 60)` -> 1
    *   `(1 == 2)` -> 0
    *   `a = 0;`
*   `a = 3 > 1 > 0 == 4 < 6 > 3 != 5;`
    *   `(3 > 1)` -> 1
    *   `(1 > 0)` -> 1
    *   `(4 < 6)` -> 1
    *   `(1 > 3)` -> 0
    *   `(0 != 5)` -> 1
    *   Now: `a = 1 == 1 != 1;`
    *   Associativity of `== !=` is L to R.
    *   `(1 == 1)` -> 1
    *   `(1 != 1)` -> 0
    *   `a = 0;`

---

## Lecture 7: Problem Solving (Aug 8, 2024)

**Topic:** Data Types & Operators (Problem Solving)

*(This lecture appears very short in the slides, possibly just containing the title and topic slides. No specific problems or code were shown in the provided images for Lecture 7 itself. Problems related to Data Types and Operators were covered in Lecture 10, which might have been intended as the problem-solving session for this topic.)*

---

## Lecture 8: Control Flow Statements - Part I (Aug 10, 2024)

**Topic:** Control Flow Statements (Introduction, `if` statement)

*(This lecture seems to cover concepts explained in detail in Lecture 11 and 12. The slides provided for Lecture 8 itself mainly focus on Logical Operators, Short-Circuit Evaluation, Increment/Decrement, and Operator Precedence, which were covered in Lecture 6 notes. It seems the topic slide might be misaligned with the content slides shown for Lecture 8.)*

*Assuming Lecture 8 intended to start Control Flow:*

**1. Flow Control:**
    *   By default, C programs execute statements sequentially, one after another.
    *   Control flow statements alter this sequential execution.
    *   **Types:**
        *   **Selection/Conditional:** Choose which code block to execute based on a condition (`if`, `if-else`, `switch`).
        *   **Iterative/Looping:** Repeat a block of code (`for`, `while`, `do-while`).
        *   **Jump:** Unconditional transfer of control (`break`, `continue`, `goto`, `return`).

**2. Selection Statements:**
    *   Allow the program to make decisions.

**3. `if` Statement:**
    *   Executes a block of code *only if* a specified condition is true (non-zero).
    *   **Syntax:**
        ```c
        if (condition) {
            // Statements to execute if condition is true
            statement1;
            statement2;
            ...
        }
        // Next statement after the if block
        ```
    *   **Condition:** Any expression that evaluates to a value.
        *   Non-zero value: Condition is considered TRUE.
        *   Zero value: Condition is considered FALSE.
    *   **Braces `{}`:**
        *   Define the block of code controlled by the `if`.
        *   If the block contains only *one* statement, the braces are optional.
        *   **Good Practice:** *Always* use braces, even for single statements, to avoid ambiguity and errors, especially during code modification.
        *   **Without Braces:** `if (condition) statement1; statement2;` - Only `statement1` is controlled by the `if`. `statement2` always executes.

**Code Example: `if` Statement**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 5;

    printf("Start\n");

    // Condition is true (10 > 5)
    if (a > b) {
        printf("a is greater than b\n");
    }

    // Condition is false (5 > 10)
    if (b > a) {
        printf("This will not be printed\n");
    }

    // Condition is true (non-zero result)
    if (a + b) { // 10 + 5 = 15 (non-zero)
        printf("a + b is non-zero\n");
    }

    // Condition is false (zero result)
    if (a - 10) { // 10 - 10 = 0 (zero)
         printf("This will not be printed either\n");
    }

    // Single statement without braces (generally discouraged)
    if (a == 10)
        printf("a is 10 (single statement if)\n");
        printf("This line always executes, regardless of the if\n");

    printf("End\n");

    return 0;
}
```
**Output:**
```
Start
a is greater than b
a + b is non-zero
a is 10 (single statement if)
This line always executes, regardless of the if
End
```

---

## Lecture 9: Control Flow Statements - Part II (Aug 12, 2024)

**Topic:** Control Flow Statements (`if-else`, `if-else if-else`)

*(The slides provided for Lecture 9 focus on Number Systems and Bitwise Operators. This seems misaligned with the lecture title. The notes below cover `if-else` based on the title, assuming the content was intended for this lecture or covered elsewhere.)*

**1. `if-else` Statement:**
    *   Executes one block of code if a condition is true, and a *different* block if the condition is false.
    *   Provides an alternative path of execution.
    *   **Syntax:**
        ```c
        if (condition) {
            // Statements for TRUE case
            statement_block_1;
        } else {
            // Statements for FALSE case
            statement_block_2;
        }
        // Next statement after the if-else block
        ```
    *   Exactly one of the blocks (`statement_block_1` or `statement_block_2`) will be executed.

**Code Example: `if-else`**
```c
#include <stdio.h>

int main() {
    int number;

    printf("Enter an integer: ");
    scanf("%d", &number);

    // Check if the number is even or odd
    if (number % 2 == 0) {
        printf("%d is an even number.\n", number);
    } else {
        printf("%d is an odd number.\n", number);
    }

    return 0;
}
```

**2. `if-else if-else` Ladder (or Chain):**
    *   Used to check multiple conditions sequentially.
    *   The first condition that evaluates to true has its corresponding block executed, and the rest of the ladder is skipped.
    *   The final `else` (optional) acts as a default case if none of the preceding `if` or `else if` conditions are true.
    *   **Syntax:**
        ```c
        if (condition1) {
            // Block 1: Executes if condition1 is true
        } else if (condition2) {
            // Block 2: Executes if condition1 is false AND condition2 is true
        } else if (condition3) {
            // Block 3: Executes if condition1 & 2 are false AND condition3 is true
        }
        ... // More else if blocks
        else {
            // Default Block: Executes if ALL preceding conditions are false
        }
        // Next statement after the ladder
        ```

**Code Example: `if-else if-else`**
```c
#include <stdio.h>

int main() {
    int number;

    printf("Enter an integer: ");
    scanf("%d", &number);

    if (number > 0) {
        printf("%d is positive.\n", number);
    } else if (number < 0) {
        printf("%d is negative.\n", number);
    } else {
        printf("The number is zero.\n", number);
    }

    return 0;
}
```

**3. Nested `if` Statements:**
    *   An `if` or `if-else` statement can be placed inside another `if` or `else` block.
    *   Used for more complex decision-making structures.
    *   **Dangling Else Problem:** An `else` clause always associates with the *nearest* preceding `if` that doesn't already have an `else`, unless braces `{}` dictate otherwise.
        ```c
        int a = 1, b = -1;
        if (a > 0)
            if (b > 0) // This if pairs with the else
                printf("Both positive\n");
        else // This else belongs to 'if (b > 0)'
            printf("a positive, b non-positive\n");
        // To make the else pair with 'if (a > 0)', use braces:
        if (a > 0) {
            if (b > 0)
                 printf("Both positive\n");
        } else { // Now this else belongs to 'if (a > 0)'
            printf("a non-positive\n");
        }
        ```

---

## Lecture 10: Control Flow Statements - Part III (Aug 13, 2024)

**Topic:** Data Types and Operators Practice Problems (DPP 01 Discussion)

*(This lecture contains practice problems related to Data Types and Operators, likely serving as the problem-solving session for Lectures 4-6).*

**Problem 1 (MCQ):**
*   **Q:** Consider the following declarations:
    *   P: `signed short x;`
    *   Q: `unsigned long long int x;`
    Which of the given declarations is/are CORRECT?
*   **Analysis:**
    *   `short` is a valid integer type. `signed` is a valid modifier (and often default for short). `signed short x;` is correct.
    *   `long long int` is a valid integer type. `unsigned` is a valid modifier. `unsigned long long int x;` is correct.
*   **Answer:** C (Both P and Q)

**Problem 2 (NAT):**
*   **Q:** Consider the following program:
    ```c
    #include <stdio.h>
    int main() {
        int x = 32769;
        printf("%d", x);
        return 0;
    }
    (Assume integer is of 2 bytes)
    The value printed is ______.
    ```
*   **Analysis:**
    *   Integer is 2 bytes (16 bits).
    *   `printf("%d", ...)` expects a `signed int`.
    *   Range of signed 16-bit int: -32768 to +32767.
    *   32769 is outside this range. It wraps around.
    *   32767 is the max positive. 32768 would be -32768. 32769 would be -32767.
*   **Answer:** -32767

**Problem 3 (MCQ):**
*   **Q:** Consider the following program:
    ```c
    #include <stdio.h>
    int main() {
        char ch = 141;
        printf("%d", ch);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:**
    *   `char` is likely `signed char` by default (common). Range: -128 to +127.
    *   141 is outside this range. It wraps around.
    *   127 is max positive. 128 -> -128, 129 -> -127, ..., 141 -> ?
    *   Calculation: `141 - 256 = -115`. (Since 256 values total for 1 byte).
    *   `printf("%d", ...)` prints the integer value.
*   **Answer:** B (-115)

**Problem 4 (MCQ):**
*   **Q:** Consider the following function:
    ```c
    #include <stdio.h>
    int main() {
        char ch = -134;
        printf("%c", ch);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:**
    *   `char` is likely `signed char`. Range -128 to +127.
    *   -134 is outside the range. It wraps around.
    *   -128 is min negative. -129 -> +127, -130 -> +126, ..., -134 -> ?
    *   Calculation: `-134 + 256 = 122`.
    *   `printf("%c", ...)` prints the character corresponding to the ASCII value. ASCII 122 is 'z'.
*   **Answer:** D (z)

**Problem 5 (NAT):**
*   **Q:** Consider the following program:
    ```c
    #include <stdio.h>
    int main() {
        char ch = 125;
        ch = ch + 6;
        printf("%d", ch);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:**
    *   `char` likely `signed char`. Range -128 to +127.
    *   `ch = 125;` (Valid)
    *   `ch = ch + 6;` -> `ch = 125 + 6 = 131;`
    *   131 is outside the range. Wraps around.
    *   127 is max. 128 -> -128, 129 -> -127, 130 -> -126, 131 -> -125.
    *   `printf("%d", ...)` prints the integer value.
*   **Answer:** -125

**Problem 6 (NAT):**
*   **Q:** Consider the following program:
    ```c
    #include <stdio.h>
    int main() {
        int x = -32769;
        printf("%d", x);
        return 0;
    }
    (Assume integer is of 2 bytes)
    The output is ______.
    ```
*   **Analysis:**
    *   Signed 16-bit int range: -32768 to +32767.
    *   -32769 is outside the range. Wraps around.
    *   -32768 is min. -32769 -> +32767.
*   **Answer:** 32767

**Problem 7 (MCQ):**
*   **Q:** Consider the following two statements:
    *   P: C standard specifies fixed number of bytes for every data type. (False - it specifies minimum ranges, sizes can vary).
    *   Q: The size order for int, short and long data type is short < int < long. (False - it's short <= int <= long).
    Which of the following statements is/are CORRECT?
*   **Answer:** C (Neither P nor Q)

**Problem 8 (MSQ):**
*   **Q:** Which of the following is/are valid declaration of a signed short integer?
    *   A: `Short int a;` (Valid - `int` is optional)
    *   B: `Short a;` (Valid - `int` is optional)
    *   C: `Signed short a;` (Valid - `signed` is optional/default, `int` is optional)
    *   D: `Signed short int a;` (Valid - most explicit form)
*   **Answer:** A, B, C, D

**Problem 9 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main(void) {
        int a;
        a = 2 * 6 / 5 + 3.0 / 2 + 1;
        printf("%d", a);
        return 0;
    }
    The value of a is ______.
    ```
*   **Analysis:**
    *   `2 * 6 / 5`: `12 / 5` (integer division) -> `2`
    *   `3.0 / 2`: `3.0 / 2.0` (floating-point division) -> `1.5`
    *   `a = 2 + 1.5 + 1;` -> `a = 4.5;`
    *   Assigning float `4.5` to `int a`. Truncation occurs. `a` becomes `4`.
    *   `printf("%d", a);` prints the integer value.
*   **Answer:** D (4) *(Self-correction: The slide shows 9. Let's re-evaluate `a = 2 * 6 / 5 + 3.0 / 2 + 1;`. Precedence: `* /` before `+`. `2*6` is 12. `12/5` is 2. `3.0/2` is 1.5. `a = 2 + 1.5 + 1`. `a = 4.5`. Assign to int `a` -> `a=4`. The slide's answer 9 seems incorrect based on standard C rules. Let's assume the expression was different, maybe `a = 2 * (6 / 5 + 3.0 / 2 + 1);`? No. Maybe `a = (2 * 6) / (5 + 3.0 / 2 + 1);`? No. Let's trust the standard evaluation: result is 4. The slide answer might be wrong or based on a different expression/compiler.)*

**Problem 10 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main(void) {
        int a;
        a = 16.0 / 4 * 5 % 3;
        printf("%d", a);
        return 0;
    }
    The value of a printed is ______.
    ```
*   **Analysis:**
    *   `16.0 / 4`: Floating point division -> `4.0`
    *   `4.0 * 5`: -> `20.0`
    *   `20.0 % 3`: Modulus operator requires integer operands. This is a **compiler error**.
*   **Answer:** A (Compiler error)

**Problem 11 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a;
        a = 32 > 24 > 13 > 10 > 8 > -1 > 0;
        printf("%d", a);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:** Relational operators associate L to R. Result is 0 or 1.
    *   `(32 > 24)` -> 1
    *   `(1 > 13)` -> 0
    *   `(0 > 10)` -> 0
    *   `(0 > 8)` -> 0
    *   `(0 > -1)` -> 1
    *   `(1 > 0)` -> 1
    *   `a = 1;`
*   **Answer:** 1

**Problem 12 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a;
        a = 25 > 15 > 0 != 12 < 45 > 42 != 65;
        printf("%d", a);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:** `> < >= <=` have higher precedence than `== !=`. Both groups are L to R.
    *   `(25 > 15)` -> 1
    *   `(1 > 0)` -> 1
    *   `(12 < 45)` -> 1
    *   `(1 > 42)` -> 0
    *   Expression becomes: `a = 1 != 0 != 65;`
    *   `(1 != 0)` -> 1
    *   `(1 != 65)` -> 1
    *   `a = 1;`
*   **Answer:** 1

**Problem 13 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a=0, b=1;
        a = (a=5) && (b=0);
        printf("%d", a);
        printf("%d", b);
        return 0;
    }
    The output is: ______.
    ```
*   **Analysis:**
    *   `a = (a=5) && (b=0);`
    *   Inner `(a=5)`: Assigns 5 to `a`. The value of this assignment expression is 5 (non-zero, true).
    *   `&&`: Since the first operand (5) is true, the second operand `(b=0)` is evaluated.
    *   Inner `(b=0)`: Assigns 0 to `b`. The value of this assignment expression is 0 (false).
    *   `5 && 0`: The result is 0 (false).
    *   Outer `a = 0;`: The final result 0 is assigned to `a`.
    *   Final values: `a` is 0, `b` is 0.
    *   `printf` outputs: 00
*   **Answer:** B (00)

**Problem 14 (MCQ):**
*   **Q:** Consider the following statements:
    *   P: The precedence of the modulus operator is higher than multiplication or division operator. (False - same precedence).
    *   Q: The result of the modulus operator contains the sign of the second operand. (False - usually the sign of the first operand, or implementation defined in older standards).
    Which of the following statements is/are INCORRECT?
*   **Answer:** C (Both P and Q)

**Problem 15 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int x = -2023;
        printf("%d", ~(x = x + 5));
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:**
    *   `x = x + 5` -> `x = -2023 + 5` -> `x = -2018`. The value of the assignment expression is -2018.
    *   `~(-2018)`: Bitwise NOT. Formula: `~a = -(a + 1)`.
    *   `~(-2018) = -(-2018 + 1) = -(-2017) = 2017`.
*   **Answer:** 2017

**Problem 16 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main(void) {
        float x;
        x = 7 * 2.0 / 2 + 10 / 3;
        printf("%f", x);
        return 0;
    }
    The value of x is ______.
    ```
*   **Analysis:**
    *   `7 * 2.0`: -> `14.0` (float)
    *   `14.0 / 2`: -> `7.0` (float)
    *   `10 / 3`: -> `3` (integer division)
    *   `x = 7.0 + 3;` -> `x = 10.0;`
*   **Answer:** B (10.0)

**Problem 17 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a=0;
        a = printf("Pankaj%dSharma", printf("GATE Sharma"));
        printf("%d", a);
        return 0;
    }
    What will be the output when you compile and run the above code?
    ```
*   **Analysis:** Nested `printf`. Evaluate inner first.
    *   `printf("GATE Sharma")`: Prints "GATE Sharma". Length is 11. Returns 11.
    *   Outer `printf("Pankaj%dSharma", 11)`: Prints "Pankaj11Sharma". Length is 14. Returns 14.
    *   `a = 14;`
    *   `printf("%d", a)`: Prints 14.
    *   Combined output: GATE SharmaPankaj11Sharma14
*   **Answer:** C (GATE SharmaPankaj11Sharma14)

**Problem 18 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a;
        a = 21 > 24 > 17 > -10 < 8 > -1 > -5 != 0;
        printf("%d", a);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:** L to R for `> < >= <=`, then L to R for `== !=`.
    *   `(21 > 24)` -> 0
    *   `(0 > 17)` -> 0
    *   `(0 > -10)` -> 1
    *   `(1 < 8)` -> 1
    *   `(1 > -1)` -> 1
    *   `(1 > -5)` -> 1
    *   Expression becomes: `a = 1 != 0;`
    *   `(1 != 0)` -> 1
    *   `a = 1;`
*   **Answer:** 1

**Problem 19 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a = 2, b = -1, c = 0, d;
        d = a-- || b++ && c++;
        printf("%d%d%d%d", a, b, c, d);
        return 0;
    }
    The output string is: ______.
    ```
*   **Analysis:** Precedence: `&&` before `||`. Short-circuiting applies.
    *   `d = a-- || b++ && c++;`
    *   Evaluate `a--`: Use current value of `a` (2, which is true) for the `||` operation. Then decrement `a` to 1.
    *   `||`: Since the first operand (2) is true, the second operand (`b++ && c++`) is **not evaluated** due to short-circuiting.
    *   The result of the `||` operation is 1 (true).
    *   `d = 1;`
    *   Final values: `a` is 1, `b` is -1 (not incremented), `c` is 0 (not incremented), `d` is 1.
    *   Output: 1-101
*   **Answer:** A (1-101)

**Problem 20 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int x = -2024;
        printf("%d", ~(x = x + 5));
        printf("%d", ~(x + 1));
        return 0;
    }
    The sum of the output values printed is ______.
    ```
*   **Analysis:**
    *   First `printf`:
        *   `x = x + 5` -> `x = -2024 + 5 = -2019`. Value is -2019.
        *   `~(-2019)` -> `-(-2019 + 1) = -(-2018) = 2018`. Prints 2018.
    *   Second `printf`:
        *   `x` is now -2019.
        *   `x + 1` -> `-2019 + 1 = -2018`.
        *   `~(-2018)` -> `-(-2018 + 1) = -(-2017) = 2017`. Prints 2017.
    *   Sum: `2018 + 2017 = 4035`.
*   **Answer:** 4035

**Problem 21 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a = 0, b = 1;
        a = (a = 5) || (b = 0);
        printf("%d", a);
        printf("%d", b);
        return 0;
    }
    The output is: ______.
    ```
*   **Analysis:**
    *   `a = (a=5) || (b=0);`
    *   Inner `(a=5)`: Assigns 5 to `a`. Value is 5 (true).
    *   `||`: Since the first operand (5) is true, the second operand `(b=0)` is **not evaluated**.
    *   The result of the `||` is 1 (true).
    *   Outer `a = 1;`: Assigns 1 to `a`.
    *   Final values: `a` is 1, `b` is 1 (not changed).
    *   Output: 11
*   **Answer:** C (11)

**Problem 22 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a = 2, b = 3, c = 0, d = 1, m;
        m = a-- || b++ && c++ || d--;
        printf("%d %d %d %d %d", a, b, c, d, m); return 0;
    }
    ```
*   **Analysis:** Precedence: `&&` before `||`. Associativity: L to R for `||`.
    *   `m = a-- || (b++ && c++) || d--;`
    *   Evaluate `a--`: Use value 2 (true). Decrement `a` to 1.
    *   First `||`: `2 || (...)`. Since 2 is true, the right side (`b++ && c++`) is **not evaluated**. Result of first `||` is 1.
    *   Expression becomes: `m = 1 || d--;`
    *   Second `||`: Since the first operand (1) is true, the right side (`d--`) is **not evaluated**.
    *   Result of second `||` is 1.
    *   `m = 1;`
    *   Final values: `a`=1, `b`=3, `c`=0, `d`=1, `m`=1.
    *   Output: 1 3 0 1 1
*   **Answer:** D (2 3 0 1 1) *(Self-correction: The trace on the slide seems to evaluate differently. Let's re-read the question's code vs the slide's trace. The slide trace seems to evaluate `m = a-- || b++ && c++ || d--;` as `m = (a-- || (b++ && c++)) || d--;`.
    *   `a--`: Use 2 (true), a becomes 1.
    *   `2 || (...)`: Result is 1. `b++ && c++` is skipped.
    *   `1 || d--`: Result is 1. `d--` is skipped.
    *   `m = 1`.
    *   Final state: a=1, b=3, c=0, d=1, m=1. Output: `1 3 0 1 1`. The slide answer D (2 3 0 1 1) implies `a` was not decremented. This contradicts `a--`. Let's assume the slide answer D is based on a typo in the code, perhaps `m = a || ...` instead of `m = a-- || ...`. Sticking to the code as written, the output is `1 3 0 1 1`.)*

**Problem 23 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int a;
        a = printf("Pankaj Sharma") && printf("Padh Lo") || printf("Beta");
        printf("%d", a);
        return 0;
    }
    The number of characters printed is ______.
    ```
*   **Analysis:**
    *   `a = printf("Pankaj Sharma") && printf("Padh Lo") || printf("Beta");`
    *   Evaluate `printf("Pankaj Sharma")`: Prints "Pankaj Sharma". Length 13. Returns 13 (true).
    *   `&&`: Since first operand (13) is true, evaluate second: `printf("Padh Lo")`. Prints "Padh Lo". Length 7. Returns 7 (true).
    *   `13 && 7`: Result is 1 (true).
    *   Expression becomes: `a = 1 || printf("Beta");`
    *   `||`: Since first operand (1) is true, second operand `printf("Beta")` is **not evaluated**.
    *   Result of `||` is 1.
    *   `a = 1;`
    *   `printf("%d", a)`: Prints 1.
    *   Total characters printed: "Pankaj Sharma" (13) + "Padh Lo" (7) + "1" (1) = 21.
*   **Answer:** 21

**Problem 24 (MCQ):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        char ch = -143;
        printf("%c", ch);
        return 0;
    }
    The output is ______.
    ```
*   **Analysis:**
    *   `signed char` range: -128 to +127.
    *   -143 wraps around: `-143 + 256 = 113`.
    *   ASCII 113 is 'q'.
*   **Answer:** B (q)

**Problem 25 (NAT):**
*   **Q:**
    ```c
    #include <stdio.h>
    int main() {
        int c = 32780;
        printf("%d", c);
        return 0;
    }
    (Assume the size of integer is specified as of 2 bytes.)
    The output is ______.
    ```
*   **Analysis:**
    *   Signed 16-bit range: -32768 to +32767.
    *   32780 wraps around.
    *   32767 is max. 32768 -> -32768, 32769 -> -32767, ..., 32780 -> ?
    *   `32780 - 65536 = -32756`.
*   **Answer:** -32756

**Problem 26 (MSQ):**
*   **Q:** Which of the following are valid declarations?
    *   A: `unsigned a;` (Valid - `int` is implied)
    *   B: `unsigned long a;` (Valid - `int` is implied)
    *   C: `unsigned long long int a;` (Valid)
    *   D: `short a;` (Valid - `signed int` is implied)
*   **Answer:** A, B, C, D

---

## Lecture 11: Control Flow Statements - Part IV (Aug 14, 2024)

**Topic:** Control Flow Statements (Selection: `if`, `if-else`, `if-else if-else`)

**1. Recap: Flow Control Statements**
    *   Alter the default sequential execution.
    *   **Categories:**
        *   **Selection:** `if`, `if-else`, `if-else if-else`, `switch`.
        *   **Iteration:** `for`, `while`, `do-while`.
        *   **Jump:** `continue`, `break`, `goto`, `return`, `exit`.

**2. Selection Statements - `if`**
    *   Executes code block if condition is true (non-zero).
    *   **Syntax:**
        ```c
        if (condition) { // or if (expression)
           // code block for true case
        }
        ```
    *   If braces `{}` are omitted, only the *first* statement following the `if` is part of the conditional block.

**Code Example: `if` scope**
```c
#include <stdio.h>

int main() {
    // Example 1: Braces used
    if (5 > 2) { // True
        printf("Pankaj\n");
    }
    printf("Sharma\n"); // Executes regardless

    // Example 2: No braces
    if (2 < 3) // True
        printf("START\n"); // Controlled by if
    printf("END\n"); // Executes regardless

    // Example 3: Nested if without braces (potential confusion)
    if (5 > 2) // True
        if (2 < 3) // True
            printf("2\n"); // Controlled by inner if
            printf("3\n"); // Controlled by outer if (WRONG - actually executes regardless)
    // Correct interpretation:
    // if (5 > 2) {
    //     if (2 < 3) {
    //         printf("2\n");
    //     }
    //     printf("3\n"); // This is OUTSIDE the inner if, but inside the implicit outer if block
    // }
    // To make it clearer:
    if (5 > 2) { // True
        if (2 < 3) { // True
            printf("2\n");
        }
        printf("3\n"); // Executes because outer if is true
    }

    return 0;
}
```

**3. Condition Evaluation in `if`:**
    *   Any non-zero value is TRUE.
    *   Zero value is FALSE.
    *   `if (expression)`: The expression is evaluated.
        *   `if (i = 3)`: Assignment occurs (i becomes 3), the value of the assignment (3) is used as the condition (true).
        *   `if (i == 3)`: Comparison occurs. Result is 1 (true) or 0 (false).
        *   `if (printf("Hello"))`: `printf` executes (prints "Hello"), returns 5 (non-zero, true). The `if` block executes.
        *   `if (!printf("Pankaj"))`: `printf` executes (prints "Pankaj"), returns 6 (true). `!6` is 0 (false). The `if` block does *not* execute.
        *   `if (i++)`: Uses the *current* value of `i` as the condition, then increments `i`. If `i` was 0, condition is false.
        *   `if (--i)`: Decrements `i` *first*, then uses the *new* value as the condition. If the new value is 0, condition is false.

**4. `if-else` Statement:**
    *   Provides two alternative paths.
    *   **Syntax:**
        ```c
        if (condition) {
            // true block
        } else {
            // false block
        }
        ```
    *   The `else` block executes only if the `if` condition is false.

**5. `if-else if-else` Ladder:**
    *   Handles multiple mutually exclusive conditions.
    *   Checks conditions sequentially. Executes the block for the *first* true condition found and skips the rest.
    *   The final `else` is the default case if none of the above conditions are met.

**Code Example: `if-else if-else`**
```c
#include <stdio.h>

int main() {
    int marks = 75;

    if (marks >= 90) {
        printf("Grade A\n");
    } else if (marks >= 80) {
        printf("Grade B\n");
    } else if (marks >= 70) {
        printf("Grade C\n"); // This block executes
    } else if (marks >= 60) {
        printf("Grade D\n");
    } else {
        printf("Grade F\n");
    }

    // Example with logical error (independent ifs vs else if)
    // This prints multiple grades if marks are high
    if (marks >= 90) { printf("A "); }
    if (marks >= 80) { printf("B "); }
    if (marks >= 70) { printf("C "); } // Prints C
    if (marks >= 60) { printf("D "); } // Prints D
    printf("\n");
    // Correct logic uses else if

    return 0;
}
```

---

## Lecture 12: Control Flow Statements - Part V (Aug 15, 2024)

**Topic:** Control Flow Statements (Ternary Operator, Loops - `for`)

**1. Ternary Operator (`?:`)**
    *   A shorthand for simple `if-else` statements that produce a value.
    *   The only ternary operator in C.
    *   **Syntax:** `condition ? expression_if_true : expression_if_false`
    *   **Action:**
        1.  `condition` is evaluated.
        2.  If true (non-zero), `expression_if_true` is evaluated, and its value becomes the result of the whole ternary expression. `expression_if_false` is *not* evaluated.
        3.  If false (zero), `expression_if_false` is evaluated, and its value becomes the result. `expression_if_true` is *not* evaluated.
    *   **Example:** Find the largest of two numbers.
        ```c
        int a = 10, b = 20, max;
        // Using if-else
        if (a > b) {
            max = a;
        } else {
            max = b;
        }
        // Using ternary operator
        max = (a > b) ? a : b; // max will be 20
        printf("Max is %d\n", max);
        ```
    *   **Example:** Largest of three distinct numbers.
        ```c
        int a=10, b=30, c=20, largest;
        largest = (a > b && a > c) ? a : ((b > c) ? b : c);
        // (10 > 30 && 10 > 20) -> false
        // Evaluate ((30 > 20) ? 30 : 20)
        // (30 > 20) -> true
        // Result is 30
        // largest = 30;
        printf("Largest is %d\n", largest);
        ```

**2. Iterative Statements (Loops):**
    *   Used to repeat a block of code multiple times.
    *   Types: `for`, `while`, `do-while`.

**3. `for` Loop:**
    *   Typically used when the number of iterations is known or can be determined beforehand.
    *   **Syntax:**
        ```c
        for (initialization; condition; update) {
            // Loop body - statements to repeat
            statement1;
            statement2;
            ...
        }
        // Next statement after the loop
        ```
    *   **Execution Flow:**
        1.  **Initialization:** Executed *once* at the very beginning (e.g., `int i = 1;`).
        2.  **Condition:** Evaluated *before* each potential iteration. If true (non-zero), the loop body executes. If false (zero), the loop terminates, and execution jumps to the statement after the loop.
        3.  **Loop Body:** Executed if the condition is true.
        4.  **Update:** Executed *after* the loop body completes each iteration (e.g., `i++`, `i = i + 2`).
        5.  Go back to Step 2 (evaluate condition again).

**Code Example: `for` Loop**
```c
#include <stdio.h>

int main() {
    int i;

    // Print "Pankaj" 5 times
    printf("Printing Pankaj 5 times:\n");
    // 1. Init: i = 1
    // 2. Cond: 1<=5 (T) -> Body -> Update (i=2)
    // 3. Cond: 2<=5 (T) -> Body -> Update (i=3)
    // 4. Cond: 3<=5 (T) -> Body -> Update (i=4)
    // 5. Cond: 4<=5 (T) -> Body -> Update (i=5)
    // 6. Cond: 5<=5 (T) -> Body -> Update (i=6)
    // 7. Cond: 6<=5 (F) -> Terminate
    for (i = 1; i <= 5; i++) {
        printf("Pankaj\n"); // Loop body
    }

    printf("\nPrinting numbers 6 to 10:\n");
    for (int roll = 6; roll <= 10; roll++) {
         printf("Roll: %d\n", roll);
    }

    printf("\nPrinting numbers -1 to 3:\n");
    for (int count = -1; count <= 3; count++) {
         printf("Count: %d\n", count);
    }

    return 0;
}
```

**4. Calculating Loop Iterations:**
    *   For simple loops like `for (i = start; i <= end; i++)`, the number of iterations is `end - start + 1`.
    *   For `for (i = start; i < end; i++)`, it's `end - start`.
    *   Be careful with the condition (`<=` vs `<`) and the update step.

---

## Lecture 13: Control Flow Statements - Part VI (Aug 16, 2024)

**Topic:** Control Flow Statements (`for` loop variations)

**1. `for` Loop Flexibility:**
    *   Any of the three expressions (initialization, condition, update) in a `for` loop are **optional**.
    *   **Omitting Initialization:** Can be done if the loop variable is initialized before the loop.
        ```c
        int i = 1;
        for (; i <= 5; i++) { /* ... */ }
        ```
    *   **Omitting Update:** The update can be done inside the loop body.
        ```c
        for (int i = 1; i <= 5; ) {
            printf("%d ", i);
            i++; // Update inside the body
        }
        ```
    *   **Omitting Condition:** If the condition is omitted, it defaults to **true**. This creates an infinite loop unless terminated by other means (like `break` or `return`).
        ```c
        for (int i = 1; ; i++) { // Infinite loop (condition is always true)
            printf("%d ", i);
            if (i > 10) {
                break; // Exit condition inside the loop
            }
        }
        ```
    *   **Omitting All:** `for ( ; ; ) { /* ... */ }` is a common way to write an infinite loop.

**2. Comma Operator in `for` Loop:**
    *   The comma operator (`,`) allows multiple expressions to be evaluated sequentially within the initialization or update parts. The value of the entire comma-separated expression is the value of the *last* expression.
    *   **Example:**
        ```c
        int i, j;
        for (i = 0, j = 10; i < j; i++, j--) {
            printf("i=%d, j=%d\n", i, j);
        }
        ```

**3. `for` Loop Examples & Analysis:**

*   **Example 1:**
    ```c
    #include <stdio.h>
    int main() {
        int i = 1;
        // Init: None (i=1 before)
        // Cond: i <= 3 (evaluated first with i=1 -> True)
        // Body: printf("Pan"), i=i+2 (i=3)
        // Update: 50 (evaluated, value discarded)
        // Cond: i <= 3 (evaluated with i=3 -> True)
        // Body: printf("kaj"), i=i+2 (i=5)
        // Update: 50 (evaluated, value discarded)
        // Cond: i <= 3 (evaluated with i=5 -> False) -> Terminate
        for ( ; i <= 3; 50) { // 50 is a valid expression, but has no effect here
            printf("Pan");
            printf("kaj");
            i = i + 2;
        }
        return 0;
    } // Output: PankajPankaj
    ```
    *(Self-correction: The slide trace shows `PankajPankaj`. Let's re-trace carefully.
    1. i=1. Cond: 1<=3 (T). Body: Prints "Pankaj", i becomes 3. Update: 50.
    2. i=3. Cond: 3<=3 (T). Body: Prints "Pankaj", i becomes 5. Update: 50.
    3. i=5. Cond: 5<=3 (F). Terminate.
    Output is indeed `PankajPankaj`.)*

*   **Example 2 (Infinite Loop - Signed Char Overflow):**
    ```c
    #include <stdio.h>
    int main() {
        // Assuming char is signed (-128 to +127)
        char ch;
        // ch=1 -> T -> print -> ch=2
        // ...
        // ch=127 -> T -> print -> ch=128 (wraps to -128)
        // ch=-128 -> T -> print -> ch=-127
        // ...
        // ch=-1 -> T -> print -> ch=0
        // ch=0 -> T -> print -> ch=1
        // Loop never terminates because ch is always non-zero inside the loop body
        // and the condition `ch` is checked *before* the increment.
        // Wait, the condition is just `ch`. The loop terminates when `ch` becomes 0 *before* the check.
        // Let's re-trace:
        // ch=1 -> Cond(1) T -> print -> ch=2
        // ...
        // ch=127 -> Cond(127) T -> print -> ch=-128
        // ch=-128 -> Cond(-128) T -> print -> ch=-127
        // ...
        // ch=-1 -> Cond(-1) T -> print -> ch=0
        // ch=0 -> Cond(0) F -> Terminate.
        // How many prints? 1 to 127 (127 times) + -128 to -1 (128 times) = 255 times.
        for (ch = 1; ch; ch++) { // Condition is just 'ch' (true if non-zero)
            printf("Pankaj");
        }
        // The slide says 255 times. This matches the trace.
        return 0;
    }
    ```

*   **Example 3 (Infinite Loop - Skipping Values):**
    ```c
    #include <stdio.h>
    int main() {
        // Assuming char is signed (-128 to +127)
        char ch;
        // ch=1 -> Cond(1) T -> print -> ch=3
        // ch=3 -> Cond(3) T -> print -> ch=5
        // ...
        // ch=127 -> Cond(127) T -> print -> ch=129 (wraps to -127)
        // ch=-127 -> Cond(-127) T -> print -> ch=-125
        // ...
        // ch=-1 -> Cond(-1) T -> print -> ch=1
        // The loop never reaches ch=0, so it's infinite.
        for (ch = 1; ch; ch = ch + 2) {
            printf("Pankaj");
        }
        return 0;
    }
    ```

*   **Example 4 (Complex `for`):**
    ```c
    #include <stdio.h>
    int main() {
        int i = 1;
        // Init: printf("1") -> prints 1, returns 1.
        // Cond: i <= 5 (evaluated with i=1 -> True)
        // Body: printf("2") -> prints 2, returns 1. i++ (i becomes 2).
        // Update: printf("3") -> prints 3, returns 1.
        // Cond: i <= 5 (evaluated with i=2 -> True)
        // Body: printf("2") -> prints 2, returns 1. i++ (i becomes 3).
        // Update: printf("3") -> prints 3, returns 1.
        // Cond: i <= 5 (evaluated with i=3 -> True)
        // Body: printf("2") -> prints 2, returns 1. i++ (i becomes 4).
        // Update: printf("3") -> prints 3, returns 1.
        // Cond: i <= 5 (evaluated with i=4 -> True)
        // Body: printf("2") -> prints 2, returns 1. i++ (i becomes 5).
        // Update: printf("3") -> prints 3, returns 1.
        // Cond: i <= 5 (evaluated with i=5 -> True)
        // Body: printf("2") -> prints 2, returns 1. i++ (i becomes 6).
        // Update: printf("3") -> prints 3, returns 1.
        // Cond: i <= 5 (evaluated with i=6 -> False) -> Terminate.
        for (printf("1"); i <= 5; printf("3")) {
            printf("2");
            i++;
        }
        return 0;
    } // Output: 12323232323
    ```

---

## Lecture 14: Control Flow Statements - Part VII (Aug 19, 2024)

**Topic:** Control Flow Statements (Nested Loops, `while` loop)

**1. Nested Loops:**
    *   A loop placed inside the body of another loop.
    *   The inner loop executes completely for *each* iteration of the outer loop.
    *   **Example:** Print a 3x4 grid of coordinates.
        ```c
        #include <stdio.h>
        int main() {
            int i, j;
            // Outer loop runs 3 times (i=1, i=2, i=3)
            for (i = 1; i <= 3; i++) {
                // Inner loop runs 4 times for each outer iteration
                for (j = 1; j <= 4; j++) {
                    printf("(%d,%d) ", i, j); // Print coordinates
                }
                printf("\n"); // Newline after each row (inner loop finishes)
            }
            return 0;
        }
        ```
        **Output:**
        ```
        (1,1) (1,2) (1,3) (1,4)
        (2,1) (2,2) (2,3) (2,4)
        (3,1) (3,2) (3,3) (3,4)
        ```
    *   **Complexity/Number of Executions:** If the outer loop runs N times and the inner loop runs M times for each outer iteration, the inner loop's body executes N * M times.

**2. Time Complexity Analysis (Basic Examples):**
    *   `for (i=1; i<=n; i++) { for (j=1; j<=3; j++) { printf("P"); } }` -> Inner body runs n * 3 = O(n) times.
    *   `for (i=1; i<=n; i++) { for (j=1; j<=n; j++) { printf("P"); } }` -> Inner body runs n * n = O(n²) times.
    *   `for (i=1; i<=n; i++) { for (j=1; j<=n; j=j*2) { printf("P"); } }` -> Inner loop runs ~log₂(n) times. Total: O(n log n).
    *   `for (i=1; i<=n; i=i*2) { for (j=1; j<=n; j++) { printf("P"); } }` -> Outer loop runs ~log₂(n) times. Inner loop runs n times each. Total: O(n log n).
    *   `for (i=1; i<=n; i=i*2) { for (j=1; j<=n; j=j*2) { printf("P"); } }` -> Outer ~log₂(n), Inner ~log₂(n). Total: O((log n)²).
    *   `for (i=1; i<=n; i++) { for (j=1; j<=i; j++) { printf("P"); } }` -> Inner loop runs 1, 2, 3, ..., n times. Total = 1 + 2 + ... + n = n(n+1)/2 = O(n²).

**3. `while` Loop:**
    *   Repeats a block of code *as long as* a condition remains true.
    *   Condition is checked *before* each potential iteration (pre-test loop).
    *   Used when the number of iterations is not known in advance, but depends on a condition becoming false.
    *   **Syntax:**
        ```c
        initialization; // Often needed before the loop
        while (condition) {
            // Loop body
            statement1;
            statement2;
            ...
            update; // Often needed inside the loop to eventually make condition false
        }
        ```
    *   **Equivalence to `for`:**
        ```c
        // for loop
        for (init; cond; update) { body; }
        // equivalent while loop
        init;
        while (cond) {
            body;
            update;
        }
        ```

**Code Example: `while` Loop**
```c
#include <stdio.h>

int main() {
    int i = 1; // Initialization

    printf("Using while loop (1 to 5):\n");
    while (i <= 5) { // Condition
        printf("%d ", i);
        i++; // Update
    }
    printf("\n");

    // Example: Loop until user enters 0
    int num = -1; // Initialize to something other than 0
    printf("Enter numbers (0 to stop):\n");
    while (num != 0) {
        scanf("%d", &num);
        printf("You entered: %d\n", num);
    }
    printf("Loop finished.\n");

    return 0;
}
```

---

## Lecture 15: Functions and Storage - Part I (Aug 20, 2024)

**Topic:** Control Flow Statements (`do-while`, Loop Comparison, `break`, `continue`)

**1. `do-while` Loop:**
    *   Similar to `while`, but the condition is checked *after* the loop body executes.
    *   This guarantees the loop body runs **at least once**, even if the condition is initially false.
    *   Post-test loop.
    *   **Syntax:**
        ```c
        initialization;
        do {
            // Loop body
            statement1;
            statement2;
            ...
            update;
        } while (condition); // Note the semicolon ';' at the end
        ```

**Code Example: `do-while` Loop**
```c
#include <stdio.h>

int main() {
    int i = 10;

    // Condition (i < 5) is initially false
    printf("Using while (i=%d):\n", i);
    while (i < 5) {
        printf("This won't print.\n");
        i++;
    }

    printf("\nUsing do-while (i=%d):\n", i);
    // Body executes once, then condition (10 < 5) is checked (false)
    do {
        printf("This prints once.\n"); // Body executes
        i++;
    } while (i < 5); // Condition check

    printf("After loops, i=%d\n", i); // i will be 11

    return 0;
}
```
**Output:**
```
Using while (i=10):

Using do-while (i=10):
This prints once.
After loops, i=11
```

**2. Choosing Between Loops (`for`, `while`, `do-while`):**
    *   **`for`:** Best when the number of iterations is known or easily calculated beforehand (e.g., iterating 10 times, iterating through an array).
    *   **`while`:** Best when iteration depends on a condition becoming false, and the condition should be checked *before* the first iteration (e.g., reading file until end-of-file, processing user input until a specific value is entered). Pre-test loop.
    *   **`do-while`:** Best when the loop body *must* execute at least once, regardless of the condition (e.g., menu-driven programs where the menu is shown at least once). Post-test loop.

**3. Jump Statements (`break`, `continue`):**
    *   Alter the normal flow of loops (and `switch` statements).

**4. `continue` Statement:**
    *   Skips the *rest of the current iteration* of the loop body.
    *   Execution jumps immediately to the loop's *update* expression (in `for` loops) or the *condition* check (in `while` and `do-while` loops) for the *next* iteration.
    *   Does **not** terminate the loop entirely.

**Code Example: `continue`**
```c
#include <stdio.h>

int main() {
    int i;

    printf("Printing 1 to 10, skipping multiples of 3:\n");
    for (i = 1; i <= 10; i++) {
        if (i % 3 == 0) {
            continue; // Skip the printf for this iteration
        }
        printf("%d ", i); // Executed only if continue was not hit
    }
    printf("\n");

    return 0;
}
```
**Output:**
```
Printing 1 to 10, skipping multiples of 3:
1 2 4 5 7 8 10
```

**5. `break` Statement:**
    *   Terminates the *innermost* loop (`for`, `while`, `do-while`) or `switch` statement immediately.
    *   Execution jumps to the first statement *after* the terminated loop or switch.

**Code Example: `break`**
```c
#include <stdio.h>

int main() {
    int i;

    printf("Printing 1 up to the first multiple of 3:\n");
    for (i = 1; i <= 10; i++) {
        if (i % 3 == 0) {
            break; // Exit the loop immediately
        }
        printf("%d ", i);
    }
    printf("\nLoop finished after break at i=%d\n", i); // i will be 3

    return 0;
}
```
**Output:**
```
Printing 1 up to the first multiple of 3:
1 2
Loop finished after break at i=3
```

---

## Lecture 16: Functions and Storage - Part II (Aug 21, 2024)

**Topic:** Control Flow Statements (`switch` statement)

**1. `switch` Statement:**
    *   A multi-way selection statement.
    *   Compares the value of an *expression* against multiple constant *case labels*.
    *   Executes the block of code associated with the matching case.
    *   Often provides a more readable alternative to long `if-else if-else` ladders when checking against specific constant values.
    *   **Keywords:** `switch`, `case`, `break`, `default`.

**2. `switch` Syntax:**
    ```c
    switch (expression) { // Expression must evaluate to an integer type (int, char, enum)
        case constant_expression_1:
            // Statements for case 1
            statement_block_1;
            break; // Optional: exits the switch

        case constant_expression_2:
            // Statements for case 2
            statement_block_2;
            break; // Optional

        // ... more cases

        default: // Optional: default case if no other case matches
            // Statements for default case
            default_statement_block;
            break; // Optional (but good practice if default isn't last)
    }
    // Next statement after the switch
    ```

**3. Key Rules and Behavior:**
    *   **Expression:** Must evaluate to an integer value (including `char`, as chars are internally integers). Floats/doubles are not allowed directly.
    *   **`case` Labels:** Must be *constant integer expressions* (literals like `1`, `'A'`, or compile-time constants like `10+3*4`). Variables (like `case a:`) are **not allowed**. No duplicate case labels are allowed within the same switch.
    *   **`break` Statement:** Crucial for separating cases. If `break` is omitted, execution "falls through" to the *next* case's statements until a `break` is encountered or the `switch` block ends. This fall-through behavior can be useful but is often a source of bugs if unintended.
    *   **`default` Case:** Optional. If present, its block executes if none of the `case` labels match the `switch` expression's value. Its position within the `switch` doesn't matter, but it's conventionally placed last.
    *   **Execution Flow:**
        1.  The `switch` expression is evaluated once.
        2.  The result is compared against each `case` label sequentially.
        3.  If a match is found, execution jumps to the statements following that `case` label.
        4.  Execution continues (including falling through to subsequent cases) until a `break` statement is hit or the end of the `switch` block (`}`) is reached.
        5.  If no `case` label matches and a `default` case exists, execution jumps to the `default` block.
        6.  If no `case` matches and there's no `default`, the entire `switch` statement does nothing.

**Code Example: `switch`**
```c
#include <stdio.h>

int main() {
    int i = 3;
    char grade = 'B';

    // Example 1: Basic switch with break
    printf("Example 1 (i=%d):\n", i);
    switch (i) {
        case 1:
            printf("One\n");
            break;
        case 3:
            printf("Three\n"); // Matches, prints Three
            break; // Exits switch
        default:
            printf("Other\n");
            break;
    }

    // Example 2: Fall-through behavior
    printf("\nExample 2 (i=%d) with fall-through:\n", i);
     switch (i) {
        case 1:
            printf("One\n");
            // No break
        case 3:
            printf("Three\n"); // Matches, prints Three
            // No break, falls through!
        case 4:
            printf("Four\n"); // Prints Four due to fall-through
            break; // Exits switch
        default:
            printf("Other\n");
            break;
    }

    // Example 3: Using char and default
    printf("\nExample 3 (grade='%c'):\n", grade);
    switch (grade) {
        case 'A':
            printf("Excellent\n");
            break;
        case 'B':
        case 'C': // Multiple cases can lead to the same block
            printf("Well done\n"); // Matches 'B', prints Well done
            break;
        case 'D':
            printf("Passed\n");
            break;
        default:
            printf("Invalid grade\n");
            break;
    }

    return 0;
}
```
**Output:**
```
Example 1 (i=3):
Three

Example 2 (i=3) with fall-through:
Three
Four

Example 3 (grade='B'):
Well done
```

---

## Lecture 17: Recursion - Part I (Aug 22, 2024)

**Topic:** Recursion (Introduction, Factorial Example)

*(The slides provided for Lecture 17 cover `switch` statement details and Armstrong/Strong numbers, which seems like a continuation of Control Flow rather than Recursion. The notes below introduce Recursion based on the lecture title, assuming the content was intended for this or a later lecture.)*

**1. Recursion:**
    *   A process where a function calls itself, either directly or indirectly.
    *   A problem-solving technique where the solution to a larger problem depends on solutions to smaller instances of the *same* problem.
    *   **Analogy:** Looking up a word in a dictionary might require looking up other words within its definition (recursive lookup). Asking a question in a chain until someone knows the answer.

**2. Key Components of a Recursive Function:**
    *   **Base Case(s):**
        *   The simplest instance(s) of the problem that can be solved directly, without further recursion.
        *   Stops the chain of recursive calls.
        *   **Essential** to prevent infinite recursion (leading to stack overflow).
    *   **Recursive Step:**
        *   Breaks the problem down into a smaller/simpler instance of the same problem.
        *   Calls the function itself with the smaller instance.
        *   Combines the result of the recursive call with some computation to solve the original (larger) instance.

**3. How Recursion Works (Stack):**
    *   Each time a function is called (including recursive calls), a new *activation record* (or stack frame) is pushed onto the program's call stack.
    *   This record stores the function's local variables, parameters, and the return address (where to resume execution after the call finishes).
    *   When a function returns, its activation record is popped off the stack.
    *   In recursion, the stack grows with each recursive call and shrinks as the calls return, starting from the base case.

**4. Example: Factorial (n!)**
    *   n! = n * (n-1) * (n-2) * ... * 1
    *   0! = 1 (by definition)
    *   **Recursive Definition:**
        *   `factorial(n) = 1` if `n == 0` (Base Case)
        *   `factorial(n) = n * factorial(n-1)` if `n > 0` (Recursive Step)

**Code Example: Factorial using Recursion**
```c
#include <stdio.h>

// Recursive function to calculate factorial
long long factorial(int n) {
    // Base Case: Factorial of 0 is 1
    if (n == 0) {
        printf("Base case: factorial(0) returning 1\n");
        return 1;
    }
    // Recursive Step: n * factorial(n-1)
    else {
        printf("Recursive step: calculating %d * factorial(%d)\n", n, n - 1);
        long long result = n * factorial(n - 1); // Recursive call
        printf("Returning %d * factorial(%d) = %lld\n", n, n - 1, result);
        return result;
    }
}

int main() {
    int num = 4;
    long long fact_result;

    printf("Calculating factorial of %d:\n", num);
    fact_result = factorial(num);
    printf("\nFactorial of %d is %lld\n", num, fact_result);

    return 0;
}
```
**Output & Stack Trace (Conceptual):**
```
Calculating factorial of 4:
Recursive step: calculating 4 * factorial(3)
Recursive step: calculating 3 * factorial(2)
Recursive step: calculating 2 * factorial(1)
Recursive step: calculating 1 * factorial(0)
Base case: factorial(0) returning 1
Returning 1 * factorial(0) = 1
Returning 2 * factorial(1) = 2
Returning 3 * factorial(2) = 6
Returning 4 * factorial(3) = 24

Factorial of 4 is 24
```
*Stack:*
1. `main` calls `factorial(4)`
2. `factorial(4)` calls `factorial(3)`
3. `factorial(3)` calls `factorial(2)`
4. `factorial(2)` calls `factorial(1)`
5. `factorial(1)` calls `factorial(0)`
6. `factorial(0)` hits base case, returns 1
7. `factorial(1)` receives 1, returns 1 * 1 = 1
8. `factorial(2)` receives 1, returns 2 * 1 = 2
9. `factorial(3)` receives 2, returns 3 * 2 = 6
10. `factorial(4)` receives 6, returns 4 * 6 = 24
11. `main` receives 24

---

## Lecture 18: Recursion - Part II (Aug 23, 2024)

**Topic:** Functions & Storage Classes (Introduction to Functions)

*(The slides provided for Lecture 18 introduce Functions and related concepts like compilation steps, which seems more appropriate for "Functions and Storage - Part I". The notes below follow the slide content.)*

**1. Functions:**
    *   A block of code designed to perform a specific task.
    *   **Purpose:**
        *   **Code Reusability:** Write code once, call it multiple times from different parts of the program.
        *   **Modularity:** Break down a large program into smaller, manageable, independent units.
        *   **Abstraction:** Hide the implementation details of a task behind a function call.
    *   **Types:**
        *   **Built-in/Library Functions:** Provided by the C standard library (e.g., `printf`, `scanf`, `sqrt`, `strlen`). Need to include the appropriate header file (e.g., `stdio.h`, `math.h`, `string.h`).
        *   **User-Defined Functions:** Created by the programmer.

**2. Function Definition:**
    *   The actual code that implements the function's task.
    *   **Syntax:**
        ```c
        return_type function_name(parameter_list) {
            // Function body: declarations and statements
            // ...
            return value; // Optional, only if return_type is not void
        }
        ```
    *   `return_type`: Data type of the value the function sends back (or `void` if it returns nothing). If omitted, defaults to `int` in older C standards (bad practice).
    *   `function_name`: Identifier for the function.
    *   `parameter_list`: Comma-separated list of variable declarations (`type name`) that receive values when the function is called. These are *formal parameters*.
    *   `return value;`: Sends a value back to the caller. The `value` must match the `return_type`.

**3. Function Call:**
    *   Executing a function.
    *   **Syntax:** `function_name(argument_list);`
    *   `argument_list`: Comma-separated list of values passed to the function. These are *actual arguments*. The values are copied to the corresponding formal parameters.

**4. Function Declaration (Prototype):**
    *   Tells the compiler about a function *before* it's defined or called. Specifies the function's name, return type, and the types of its parameters.
    *   **Syntax:** `return_type function_name(parameter_type_list);` (Parameter names are optional here).
    *   **Necessity:** Required if a function is called *before* its definition appears in the source file, or if the definition is in a different file. Including header files (like `stdio.h`) provides declarations for library functions.
    *   **Forward Declaration:** A declaration placed before any calls to the function within the same file.

**5. Compilation & Linking Process:**
    *   **Source Code (`.c`):** Human-readable C code.
    *   **Preprocessor:** Handles directives like `#include` (pastes header file content) and `#define` (macro substitution). Output is still C code (`.i` file, usually temporary).
    *   **Compiler:** Translates the preprocessed C code into Assembly language (`.s` file, usually temporary).
    *   **Assembler:** Translates Assembly language into machine code (Object code, `.o` or `.obj` file). This file contains the code for the functions defined in the source file but doesn't yet resolve calls to library functions or functions in other files.
    *   **Linker:** Combines object code from your file(s) with necessary code from libraries (like the standard C library containing `printf`) and resolves addresses. Produces the final *executable* file.
    *   **Loader:** Loads the executable file into memory when you run the program.

**Code Example: User-Defined Function**
```c
#include <stdio.h>

// Function Declaration (Prototype)
int add(int x, int y); // Tells compiler 'add' exists before main calls it

// Main Function (Calling function)
int main() {
    int a = 10, b = 20, answer;
    printf("In main: Calling add function...\n");
    // Function Call: 'a' and 'b' are actual arguments
    answer = add(a, b);
    printf("In main: The result is %d\n", answer);
    return 0;
}

// Function Definition (Called function)
// 'x' and 'y' are formal parameters
int add(int x, int y) {
    int temp; // Local variable within 'add'
    printf("In add: Received x=%d, y=%d\n", x, y);
    temp = x + y;
    printf("In add: Returning %d\n", temp);
    return temp; // Return the calculated value
}
```

---

## Lecture 19: Recursion - Part III (Aug 26, 2024)

**Topic:** Functions & Storage Classes (Function Calls, Call by Value, Storage Classes Intro)

**1. Function Call Mechanism:**
    *   When `main` calls `add(a, b)`:
        1.  Values of actual arguments (`a`, `b`) are copied into the formal parameters (`x`, `y`) of the called function (`add`).
        2.  Control transfers to the beginning of the `add` function.
        3.  The body of `add` executes. Local variables (`temp`) are created.
        4.  The `return` statement evaluates its expression (`temp`).
        5.  The return value is sent back to the point where `add` was called in `main`.
        6.  Execution resumes in `main` using the return value (e.g., assigning it to `answer`).
        7.  Local variables of `add` (`x`, `y`, `temp`) are destroyed (stack frame is popped).

**2. Call by Value:**
    *   The default mechanism for passing arguments in C.
    *   The *values* of the actual arguments are copied into the formal parameters.
    *   The called function works with *copies* of the original data.
    *   **Consequence:** Changes made to the formal parameters *inside* the called function do **not** affect the original actual arguments in the calling function.

**Code Example: Call by Value (Swap attempt)**
```c
#include <stdio.h>

// Function attempts to swap values (using call by value)
void swap(int x, int y) { // x and y are copies of a and b
    int temp;
    printf("Inside swap (before): x=%d, y=%d\n", x, y);
    temp = x;
    x = y;
    y = temp;
    printf("Inside swap (after): x=%d, y=%d\n", x, y); // x and y are swapped here
}

int main() {
    int a = 10, b = 20;
    printf("In main (before swap): a=%d, b=%d\n", a, b);
    swap(a, b); // Pass values of a and b
    // Changes inside swap do NOT affect a and b in main
    printf("In main (after swap): a=%d, b=%d\n", a, b);
    return 0;
}
```
**Output:**
```
In main (before swap): a=10, b=20
Inside swap (before): x=10, y=20
Inside swap (after): x=20, y=10
In main (after swap): a=10, b=20
```
*(To actually swap values in `main`, we need to use pointers - Call by Reference/Address, covered later).*

**3. Storage Classes:**
    *   Determine the *scope*, *lifetime*, *default initial value*, and *storage location* of a variable or function.
    *   **Keywords:** `auto`, `register`, `static`, `extern`.
    *   **Key Concepts:**
        *   **Scope:** The region/part of the program where a variable/function is visible and can be accessed directly by its name.
            *   Block Scope: Visible only within the block (`{...}`) where it's declared.
            *   Function Scope: Visible only within the function (mainly for labels used with `goto`).
            *   File Scope: Visible from the point of declaration to the end of the source file.
            *   Program Scope (Linkage): Visibility across multiple files (related to `extern` and `static` at file scope).
        *   **Lifetime:** The duration for which the variable exists in memory during program execution.
        *   **Default Initial Value:** The value a variable holds if not explicitly initialized when created (e.g., garbage, zero).
        *   **Storage Location:** Where the variable is stored in memory (e.g., Stack, Data Segment, Registers).

**4. Memory Layout (Conceptual):**
    *   **Stack:** Used for local variables (`auto`, `register`), function parameters, return addresses. Grows and shrinks as functions are called and return. Memory is allocated/deallocated automatically.
    *   **Heap:** Used for dynamic memory allocation (`malloc`, `calloc`). Managed explicitly by the programmer.
    *   **Data Segment:**
        *   Initialized Data Segment: Stores global and static variables that *are* initialized.
        *   Uninitialized Data Segment (BSS): Stores global and static variables that are *not* explicitly initialized (system initializes them to zero/NULL).
    *   **Code Segment (Text Segment):** Stores the compiled machine code instructions of the program. Usually read-only.

---

## Lecture 20: Recursion - Part IV (Aug 27, 2024)

**Topic:** Functions & Storage Classes (`auto`, `register`, `static` variables)

**1. `auto` Storage Class:**
    *   The **default** storage class for variables declared *inside* a block or function.
    *   The keyword `auto` is rarely used explicitly because it's the default. `int a;` inside a function is implicitly `auto int a;`.
    *   **Scope:** Block scope (visible only within the `{...}` where declared).
    *   **Lifetime:** Block lifetime (created when the block is entered, destroyed when the block is exited).
    *   **Default Value:** Garbage (unpredictable value). Must be explicitly initialized.
    *   **Storage:** Stack.

**Code Example: `auto` Scope and Lifetime**
```c
#include <stdio.h>

void func() {
    int x = 10; // auto variable, created each time func is called
    printf("Inside func: x = %d\n", x);
    x++; // Increment the copy for this call
}

int main() {
    int a = 10; // auto variable in main

    printf("In main (before block): a = %d\n", a); // Output: 10
    a++; // a becomes 11

    { // Start of inner block
        int a = 25; // New 'a', shadows the outer 'a'. Auto storage.
        printf("Inside block (inner a): a = %d\n", a); // Output: 25
        a++; // Inner a becomes 26
        printf("Inside block (inner a after ++): a = %d\n", a); // Output: 26
    } // End of inner block, inner 'a' is destroyed

    printf("In main (after block): a = %d\n", a); // Output: 11 (outer 'a' is visible again)

    printf("\nCalling func multiple times:\n");
    func(); // x=10 created, printed, incremented, destroyed
    func(); // x=10 created again, printed, incremented, destroyed
    func(); // x=10 created again, printed, incremented, destroyed

    return 0;
}
```

**2. `register` Storage Class:**
    *   A **request** (hint) to the compiler to store the variable in a CPU register instead of RAM (stack).
    *   **Goal:** Faster access, as registers are much faster than memory.
    *   **Compiler's Decision:** The compiler might ignore the request (e.g., if no registers are available, or if optimization makes it unnecessary). If ignored, the variable defaults to `auto`.
    *   **Restrictions:**
        *   Cannot take the address (`&`) of a register variable (registers don't have memory addresses).
        *   Typically used for frequently accessed variables like loop counters or accumulators. Modern compilers are often better at optimizing register allocation than manual hints.
    *   **Scope:** Block scope.
    *   **Lifetime:** Block lifetime.
    *   **Default Value:** Garbage.
    *   **Storage:** CPU Register (if request granted), otherwise Stack.

**Code Example: `register`**
```c
#include <stdio.h>

int main() {
    register int i; // Request register storage for loop counter
    int sum = 0;

    for (i = 1; i <= 1000; i++) {
        sum += i;
    }

    printf("Sum: %d\n", sum);

    // Attempting to take address of a register variable (Compiler Error)
    // printf("Address of i: %p\n", &i); // This line will cause a compile error

    return 0;
}
```

**3. `static` Storage Class (Inside Functions/Blocks):**
    *   Used for local variables declared inside a function or block.
    *   **Scope:** Block scope (like `auto`). Only accessible within the block where declared.
    *   **Lifetime:** **Entire program execution.** The variable is created and initialized *once* (when the program starts or the first time the function is called, depending on context) and persists between function calls. It is *not* destroyed when the block/function exits.
    *   **Default Value:** **Zero** (unlike `auto`).
    *   **Storage:** Data Segment (Initialized or BSS).
    *   **Key Use:** To retain a value between calls to the same function.

**Code Example: `static` Local Variable**
```c
#include <stdio.h>

void counter_func() {
    int auto_count = 0; // Auto: Re-initialized to 0 each call
    static int static_count = 0; // Static: Initialized to 0 ONLY ONCE

    auto_count++;
    static_count++;

    printf("Auto=%d, Static=%d\n", auto_count, static_count);
}

int main() {
    printf("Calling counter_func:\n");
    counter_func(); // Auto=1, Static=1
    counter_func(); // Auto=1, Static=2 (retains value)
    counter_func(); // Auto=1, Static=3 (retains value)

    // Static initialization rule: Must be initialized with a constant literal/expression
    // int x = 10;
    // static int y = x; // ERROR: Cannot initialize static with a variable

    return 0;
}
```

---

## Lecture 21: Recursion - Part V (Aug 28, 2024)

**Topic:** Functions & Storage Classes (`static` global, `extern`)

**1. Global Variables:**
    *   Variables declared *outside* of any function.
    *   **Scope:** File scope (by default). Visible from the point of declaration to the end of the file.
    *   **Lifetime:** Entire program execution.
    *   **Default Value:** Zero.
    *   **Storage:** Data Segment (Initialized or BSS).
    *   **Accessibility:** Can be accessed (and modified) by any function within the same file (after the declaration point).
    *   **Potential Issues:** Can make code harder to understand and debug due to potential modification from anywhere (loss of locality). Use with caution.

**Code Example: Global Variable**
```c
#include <stdio.h>

int global_var = 10; // Global variable, file scope

void func1() {
    printf("Inside func1: global_var = %d\n", global_var);
    global_var++; // Modifies the global variable
}

void func2() {
    printf("Inside func2: global_var = %d\n", global_var);
    global_var += 5; // Modifies the global variable
}

int main() {
    printf("Inside main (start): global_var = %d\n", global_var); // Access global
    func1();
    printf("Inside main (after func1): global_var = %d\n", global_var);
    func2();
    printf("Inside main (after func2): global_var = %d\n", global_var);
    return 0;
}
```
**Output:**
```
Inside main (start): global_var = 10
Inside func1: global_var = 10
Inside main (after func1): global_var = 11
Inside func2: global_var = 11
Inside main (after func2): global_var = 16
```

**2. `static` Storage Class (Global Variables/Functions):**
    *   When applied to a global variable or a function definition, `static` restricts its **linkage** to the current file (*internal linkage*).
    *   **Effect:** The static global variable or static function is only visible/accessible *within the source file where it is defined*. It cannot be accessed directly by code in other source files (even if declared with `extern` there).
    *   **Use Case:** To create "private" global variables or helper functions for a specific source file (module), preventing naming conflicts with other files.
    *   **Lifetime/Storage/Default:** Same as regular global variables (program lifetime, data segment, zero default).

**Code Example: `static` Global (Conceptual - requires multiple files)**
```c
// File1.c
#include <stdio.h>

static int file_scope_static = 5; // Only visible within File1.c
int global_non_static = 10;       // Visible to other files (if declared extern)

void print_vars() {
    printf("File1: file_scope_static = %d\n", file_scope_static);
    printf("File1: global_non_static = %d\n", global_non_static);
    file_scope_static++;
    global_non_static++;
}

// File2.c
#include <stdio.h>

// Attempt to access variables from File1.c
// extern int file_scope_static; // LINKER ERROR: file_scope_static has internal linkage
extern int global_non_static;   // OK: global_non_static has external linkage

// Function defined in File1.c
void print_vars();

int main() {
    printf("File2: Accessing global_non_static = %d\n", global_non_static);
    // printf("File2: Accessing file_scope_static = %d\n", file_scope_static); // Compile/Link Error

    print_vars(); // Call function from File1.c
    printf("File2: Accessing global_non_static again = %d\n", global_non_static);

    return 0;
}

// Compilation (Example):
// gcc File1.c File2.c -o program // Will likely give a linker error for file_scope_static
```

**3. `extern` Storage Class:**
    *   Used to **declare** a global variable or function that is *defined* elsewhere (typically in another source file).
    *   It tells the compiler "this variable/function exists, but its definition/memory allocation is in another file; the linker will find it."
    *   It does *not* allocate memory. It's just a declaration.
    *   **Use Case:** To access global variables or functions defined in other `.c` files.
    *   **Forward Declaration (within same file):** `extern` can also be used to declare a global variable *before* its definition within the *same* file, although this is less common.
        ```c
        #include <stdio.h>
        extern int x; // Declares x (forward declaration)
        void func1() {
           // Can use x here
           x++;
        }
        int x = 10; // Defines x (memory allocated)
        int main() { /* ... */ }
        ```
    *   **Linkage:** `extern` implies *external linkage* (visible across files), unless the original definition was `static`. You cannot use `extern` to access a `static` global from another file.

**Summary Table:**

| Specifier | Scope        | Lifetime     | Default Value | Storage       | Linkage (Global/Func) | Notes                                       |
| :-------- | :----------- | :----------- | :------------ | :------------ | :-------------------- | :------------------------------------------ |
| `auto`    | Block        | Block        | Garbage       | Stack         | N/A                   | Default for local vars                      |
| `register`| Block        | Block        | Garbage       | Register/Stack| N/A                   | Hint to compiler, cannot take address       |
| `static`  | Block        | Program      | Zero          | Data Segment  | N/A                   | Local: Persists between calls             |
| `static`  | File         | Program      | Zero          | Data Segment  | Internal              | Global/Func: Visible only within file     |
| `extern`  | File/Block   | Program      | (Defined elsewhere) | (Defined elsewhere) | External              | Declaration only, definition is elsewhere |
| (None)    | Block        | Block        | Garbage       | Stack         | N/A                   | Implicit `auto`                           |
| (None)    | File         | Program      | Zero          | Data Segment  | External              | Global variable/function (default linkage)|

---

## Lecture 22: Recursion - Part VI (Aug 29, 2024)

**Topic:** Recursion (Examples: Print Stars, Sum of Digits, Print Numbers)

**1. Recursion Design Principles:**
    *   **Identify the Base Case:** What is the simplest input for which the answer is known directly, without needing further recursion? (e.g., `n=1` for printing stars, `n` is single digit for sum).
    *   **Identify the Recursive Step:** How can the problem for input `n` be expressed in terms of the *same problem* for a smaller input (e.g., `n-1`, `n/10`)?
    *   **Ensure Progress:** Each recursive call must move closer to the base case.
    *   **Combine Results:** (If necessary) How to combine the result of the recursive call with the work done at the current step.

**2. Example 1: Print `n` Stars**
    *   **Problem:** Print `n` asterisks (`*`).
    *   **Base Case:** If `n=1`, print one star.
    *   **Recursive Step:** To print `n` stars, print one star, then recursively print `n-1` stars.

**Code Example: Print Stars**
```c
#include <stdio.h>

void printStars(int n) {
    // Base Case: If n is 0 or less, do nothing (or print newline)
    if (n <= 0) {
        // printf("\n"); // Optional: Print newline at the end
        return;
    }
    // Recursive Step (Head Recursion - prints before call)
    // printf("*");
    // printStars(n - 1);

    // Recursive Step (Tail Recursion - prints after call - prints in reverse order conceptually)
    // printStars(n - 1);
    // printf("*");

    // To match the slide's likely intent (print n stars sequentially):
    // Base case: n=1 -> print "*", return
    // Recursive: print "*", call fun(n-1)
    if (n == 1) {
        printf("*");
        return;
    } else if (n > 1) {
        printf("*"); // Print one star for the current level
        printStars(n - 1); // Recursively print the remaining stars
    }
    // Note: A simple iterative loop is usually much better for this task.
}

// Alternative based on slide diagram (prints one star, then calls for n-1)
void printStarsAlt(int n) {
     if (n <= 0) { // Base case: stop when n reaches 0 or less
         return;
     }
     printf("*"); // Perform small work (print one star)
     printStarsAlt(n - 1); // Recursive call for the rest
}


int main() {
    int count = 5;
    printf("Printing %d stars:\n", count);
    printStarsAlt(count);
    printf("\n");
    return 0;
}
```

**3. Example 2: Sum of Digits**
    *   **Problem:** Calculate the sum of the digits of a non-negative integer `n`.
    *   **Base Case:** If `n` is a single digit (0-9), the sum is `n` itself. (`n >= 0 && n <= 9` or simply `n < 10` for non-negative n).
    *   **Recursive Step:** The sum of digits of `n` is `(last digit of n) + (sum of digits of remaining number)`.
        *   Last digit = `n % 10`
        *   Remaining number = `n / 10`
        *   `sumDigits(n) = (n % 10) + sumDigits(n / 10)`

**Code Example: Sum of Digits**
```c
#include <stdio.h>

int sumDigits(int n) {
    // Ensure non-negative input if necessary, or handle negative n
    if (n < 0) n = -n; // Handle negative numbers if needed

    // Base Case: Single digit number
    if (n >= 0 && n <= 9) { // or simply if (n < 10)
        return n;
    }
    // Recursive Step
    else {
        return (n % 10) + sumDigits(n / 10);
    }
}

int main() {
    int num = 1372;
    printf("Sum of digits of %d is %d\n", num, sumDigits(num)); // 2 + 7 + 3 + 1 = 13
    num = 2379;
    printf("Sum of digits of %d is %d\n", num, sumDigits(num)); // 9 + 7 + 3 + 2 = 21
    return 0;
}
```

**4. Example 3: Print Numbers (Illustrating Call Stack)**
    *   **Head Recursion:** Work is done *before* the recursive call.
    *   **Tail Recursion:** Work is done *after* the recursive call returns.

**Code Example: Print Numbers (Head vs Tail)**
```c
#include <stdio.h>

// Head Recursion: Prints before calling (Prints 4 3 2 1)
void printHead(int n) {
    if (n == 0) {
        return; // Base case
    } else {
        printf("%d ", n); // Work done first
        printHead(n - 1); // Recursive call
    }
}

// Tail Recursion: Prints after call returns (Prints 1 2 3 4)
void printTail(int n) {
     if (n == 0) {
        return; // Base case
    } else {
        printTail(n - 1); // Recursive call first
        printf("%d ", n); // Work done after return
    }
}

int main() {
    int val = 4;
    printf("Head Recursion (printHead(%d)): ", val);
    printHead(val);
    printf("\n");

    printf("Tail Recursion (printTail(%d)): ", val);
    printTail(val);
    printf("\n");

    return 0;
}
```
