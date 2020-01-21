
![Recommender Engine|Large](https://i.ibb.co/0qZBKr0/Group.png)
# The tinysharp Language
This is my attempt at building a "very tiny" programming language, using Haskell. Work developed at UCSD for a CSE class.

#### Features of TinySharp:
- Arithmetic
- Variables
- Let-bindings
- Functions
- Recursion

#### TinySharp: Arithmetic
A grammar of arithmetic expressions:

e ::= n
    | e1 + e2
    | e1 - e2
    | e1 * e2

#### Representing Expressions and Values

data Expr = Num Int
          | Add Expr Expr
          | Sub Expr Expr
          | Mul Expr Expr

#### Evaluating Arithmetic Expressions
We can now write a Haskell function to evaluate an expression:

eval :: Expr -> Value
eval (Num n)     = n
eval (Add e1 e2) = eval e1 + eval e2
eval (Sub e1 e2) = eval e1 - eval e2
eval (Mul e1 e2) = eval e1 * eval e2


#### Alternative representation
Let’s factor out the operators into a separate type

data Binop = Add | Sub | Mul

data Expr = Num Int              -- number
          | Bin Binop Expr Expr  -- binary expression


