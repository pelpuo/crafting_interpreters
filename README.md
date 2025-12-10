## Running the Project

```bash
javac com/craftinginterpreters/lox/*.java
java -cp . com.craftinginterpreters.lox.Lox hello_world.lox
```

## Creating Expr
```bash
javac -d . com/craftinginterpreters/tool/GenerateAst.java
java -cp . com.craftinginterpreters.tool.GenerateAst Expr
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