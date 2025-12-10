## Running the Project

```bash
java -cp . com.craftinginterpreters.lox.Lox hello_world.lox
```

## Lox grammar
```py
expression → literal
| unary
| binary
| grouping ;

literal → NUMBER | STRING | "true" | "false" | "nil" ;

grouping → "(" expression ")" ;

unary → ( "-" | "!" ) expression ;

binary → expression operator expression ;

operator → "==" | "!=" | "<" | "<=" | ">" | ">="
| "+" | "-" | "*" | "/" ;
```