#### Table of contents

* [Resources](#resources)
* [Introduction](#introduction)
* [Core principles](#core-principles)
* [Examples](#examples)
* [Syntax](#syntax)
* [Naming convention](#naming-convention)
* [Technologies](#technologies)
* [Workflow](#workflow)

#### Resources

* Syntax highlighting
    * [Notepad++](resources/npp-syntax.xml)
    * [Visual Studio Code](https://github.com/IonLanguage/Ion.VSCode) (undergoing early development)

#### Introduction

The Ion language project is a programming language currently undergoing active, early development. It was created mainly for research purposes, however it is fair to say that it has grown beyond that.

Ion is an umbrella project that borrows functionality from its various respositories to accomplish a fully functional, compiled programming language.

#### Core principles

1. **Simplicity**. The language should be simple, or as powerful as the programmer wishes. This means that some symbols and patterns are optional and infered by the compiler.

2. **Fully managed**. The programmer should not be required to spend significant time installing (or building) the language, or its dependencies, when they could be coding their projects instead.

3. **Flexible**. The language should contain tools and shortcuts to make the programming experience smooth, not rigid. This means that the programmer is not required (but can) to be explicit with their code.

### Examples

Hello world

```cs
extern int puts(string message);

void main() {
    puts("Hello world!");
}
```

Fibonacci sequence

```cs
int fib(number) {
    if (number <= 1) {
        return 1;
    }

    return fib(number - 1) + fib(number - 2);
}
```

Formatted output

```cs
extern int printf(string format, ...);

void main() {
    printf("%d + 2 = 3", 1);
}
```

Struct

```cs
extern int printf(string format, ...);

struct Person {
    string name;
    int age;
}

void main() {
    Person joe = new Person {
        name: "Joe",
        age: 25
    };

    printf("Joe's age in 5 years will be: %d.", joe.age + 5);
}
```

### Syntax

Globals

```cs
int @counter = 0;

void main() {
    counter++;
    // ...
}
```

Functions

```cs
void join(char delimiter, ...) {
    // ...
}

void main() {
    // ...
}
```

Structs

```cs
struct Person {
    string name;
    int age;
}

void main() {
    // Create the struct.
    Person joe = new Person {
        name: "Joe",
        age: 25
    };

    // Access its properties.
    joe.name;
    joe.age;
}
```

Lambdas

```cs
delegate void WorkCallback(int status);

void work(WorkCallback callback) {
    int status;
    // ...
    callback(status);
}

void main() {
    // Pass lambda as parameter.
    work((int status) => {
        // ...
    });
}
```

Importing modules

```cs
// Import a module.
import my.module;

// Import a system/built-in module.
import <os>;

// Import a module with an alias.
import my.other.module as other;

// ...
```

#### Naming convention

#### Functions

All function names should be in camelCase.

```rust
void main() {
    //
}
```

#### Classes

Class names should be in PascalCase, and members in camelCase.

```c#
extern int printf(string message, ...);

class Example {
    public string name = "John Doe";

    void sayHello() {
        printf("Hello, " + this.name);
    }
}
```

#### Attributes

Attributes are considered proxy functions, thus they should be treated as functions and be named in camelCase.

```c
[Transform(0)]
int main() {
    // Return value will be transformed to '0'.
    return 1;
}
```

#### Technologies

The entire project has been implemented around Microsoft's C# language, using .NET Core.

#### Workflow

In the future, the Ion.IR repository will be the central point connecting all other repositories.

Below is a diagram of the future workflow implementation of the project.

<br />
<img src="assets/workflow.png" />
