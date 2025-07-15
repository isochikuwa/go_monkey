# Monkey Programming Language Interpreter

A Go implementation of the Monkey programming language interpreter, following the book "Writing An Interpreter In Go" by Thorsten Ball.

## What is Monkey?

Monkey is a programming language designed for learning interpreter implementation. It features:

- C-like syntax
- Variable bindings
- Integers and booleans
- Arithmetic expressions
- Built-in functions
- First-class and higher-order functions
- Closures
- A string data structure
- An array data structure
- A hash data structure

## Features

This interpreter implements:

- **Lexical Analysis**: Tokenizes source code
- **Parsing**: Builds Abstract Syntax Trees using Pratt parsing
- **Evaluation**: Tree-walking interpreter with environment-based variable storage
- **REPL**: Interactive Read-Eval-Print Loop

### Supported Language Constructs

```monkey
// Variable bindings
let age = 1;
let name = "Monkey";
let result = 10 * (20 / 2);

// Functions
let add = fn(a, b) { return a + b; };
let fibonacci = fn(x) {
  if (x == 0) {
    0
  } else {
    if (x == 1) {
      1
    } else {
      fibonacci(x - 1) + fibonacci(x - 2);
    }
  }
};

// Function calls
add(2, 3);
fibonacci(10);

// Conditionals
if (age > 18) {
  "adult"
} else {
  "minor"
}
```

## Getting Started

### Prerequisites

- Go 1.24.4 or later

### Installation

1. Clone the repository:
```bash
git clone https://github.com/isochikuwa/monkey.git
cd go_monkey
```

2. Build the interpreter:
```bash
go build -o monkey main.go
```

3. Run the REPL:
```bash
./monkey
```

Or run directly with Go:
```bash
go run main.go
```

## Usage

### Interactive REPL

Start the REPL and begin typing Monkey expressions:

```bash
$ go run main.go
Hello username! This is the Monkey programming language!
Feel free to type in commands
>> let a = 5;
>> let b = 10;
>> a + b;
15
>> let add = fn(x, y) { x + y };
>> add(5, 5);
10
```

## Development

### Running Tests

Run all tests:
```bash
go test ./...
```

Test specific packages:
```bash
go test ./lexer
go test ./parser
go test ./evaluator
go test ./ast
```

### Project Structure

```
.
├── ast/           # Abstract Syntax Tree definitions
├── evaluator/     # Tree-walking interpreter
├── lexer/         # Lexical analysis (tokenization)
├── object/        # Runtime object system and environment
├── parser/        # Parser implementation (Pratt parsing)
├── repl/          # Read-Eval-Print Loop
├── token/         # Token definitions
├── main.go        # Entry point
└── go.mod         # Go module definition
```

## Architecture

The interpreter follows a traditional architecture:

1. **Lexer**: Converts source code into tokens
2. **Parser**: Builds an Abstract Syntax Tree from tokens
3. **Evaluator**: Walks the AST and evaluates expressions
4. **Environment**: Manages variable bindings and scope

## License

This project is implemented for educational purposes following "Writing An Interpreter In Go".