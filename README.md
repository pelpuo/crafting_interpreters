## Running the Project

```bash
javac com/craftinginterpreters/lox/*.java && java -cp . com.craftinginterpreters.lox.Lox test.lox
```

## Creating Expr

```bash
javac -d . com/craftinginterpreters/tool/GenerateAst.java && java -cp . com.craftinginterpreters.tool.GenerateAst ./com/craftinginterpreters/lox/
```

## Lox grammar 1

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

## Lox grammar 2

```py
program → declaration * EOF ;

declaration → varDecl | statement | funDecl ;

varDecl → "var" IDENTIFIER ( "=" expression )? ";" ;

funDecl → "fun" function ;

function → IDENTIFIER "(" parameters? ")" block ;

parameters → IDENTIFIER ( "," IDENTIFIER )* ;

statement → exprStmt | printStmt | block  | ifStmt | whileStmt | forStmt | returnStmt ;

returnStmt → "return" expression? ";" ;

whileStmt → "while" "(" expression ")" statement ;

forStmt → "for" "(" ( varDecl | exprStmt | ";" ) expression? ";"
 expression? ")" statement ;

ifStmt → "if" "(" expression ")" statement ( "else" statement )? ;

block → "{" declaration* "}" ;

exprStmt → expression ";" ;

printStmt → "print" expression ";" ;

expression  → assignment ;

assignment → IDENTIFIER "=" assignment | equality | logic_or ;

logic_or → logic_and ( "or" logic_and )* ;

logic_and → equality ( "and" equality )* ;

equality    → comparison ( ( "!=" | "==" ) comparison )* ;

comparison  → term ( ( ">" | ">=" | "<" | "<=" ) term )* ;

term        → factor ( ( "-" | "+" ) factor )* ;


factor      → unary ( ( "/" | "*" ) unary )* ;

unary       → ( "!" | "-" ) unary
               | primary;

primary     → NUMBER | STRING | "true" | "false" | "nil"
               | "(" expression ")" | IDENTIFIER ;
```

## Reached Page `171`
