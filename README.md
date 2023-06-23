
<img src="https://i.ibb.co/dfr9wXv/TINYSHARP.png" align="center" width="100%">

# TinySharp: A Minimal Programming Language Based on Haskell

Welcome to TinySharp, a minimalist programming language inspired by Haskell! This project was undertaken as part of a CSE class at UCSD. Although tiny in its scope, TinySharp aims to provide essential programming language features.

## Features of TinySharp

TinySharp supports several fundamental programming concepts, such as:

- **Arithmetic Operations:** Includes addition, subtraction, and multiplication.
- **Variables:** Variables can be declared and used throughout the program.
- **Let-bindings:** These provide a way to name the results of expressions and use them in later computations.
- **Functions:** Basic function declarations and invocations are supported.
- **Recursion:** Allows functions to call themselves during execution, providing more complex functionality.

## TinySharp's Arithmetic

TinySharp supports a simple grammar for arithmetic expressions, defined as follows:

An expression `e` can be:
- A number `n`
- Addition of two expressions `e1 + e2`
- Subtraction of two expressions `e1 - e2`
- Multiplication of two expressions `e1 * e2`

## Expressions and Values Representation

In TinySharp, expressions are represented using the following Haskell data type:

```haskell
data Expr = Num Int             -- represents a number
          | Add Expr Expr       -- represents addition of two expressions
          | Sub Expr Expr       -- represents subtraction of two expressions
          | Mul Expr Expr       -- represents multiplication of two expressions
```

## Evaluating Arithmetic Expressions
Arithmetic expressions in TinySharp can be evaluated using the following Haskell function:

```haskell
eval :: Expr -> Value
eval (Num n)     = n
eval (Add e1 e2) = eval e1 + eval e2
eval (Sub e1 e2) = eval e1 - eval e2
eval (Mul e1 e2) = eval e1 * eval e2
```

## Alternative Representation
As an alternative, we can separate binary operations into a distinct type for a cleaner representation:

```haskell
data Binop = Add | Sub | Mul   -- represents binary operations
data Expr = Num Int            -- represents a number
          | Bin Binop Expr Expr  -- represents a binary expression
```

This alternative representation abstracts the concept of binary operations, making the code more readable and manageable.

Happy coding with TinySharp!


