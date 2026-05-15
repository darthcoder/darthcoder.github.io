`Bool` is the Boolean type. 

## Defining Boolean Functions

```haskell
exOr :: Bool -> Bool -> Bool
exOr x y = (x || y) && not (x && y)
```

## Literals and definitions

Expressions like `True` and `False` and numbers like `2` are known as **literals** as they are literal values, they evaluate to themselves and don't need further evaluation.

```haskell
myNot :: Bool -> Bool 
myNot True = False
myNot False = True
```

We can also use a combination of literals and variables on the LHS of equations defining `exOr`
```haskell
exOr True x = not x
exOr False x = x
```

## Testing

