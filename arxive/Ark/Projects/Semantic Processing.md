> From regular expressions to semantic expressions. 

A program is built first into an AST or an abstract syntax tree using a lexer and parser. We will, instead of a lexer use a tokenizer and instead of regular expression use semantic expressions. 

Semantic expressions are analogous to regular expressions, but they clarify intent instead of syntactial constructs. What this means is we classify (or lex) the input into tokens which have a semantic role in the context instead of being a list of characters to be modified.

This has one advantage and one disadvantage, the advantage is that we can tremendously relax the syntax rules in composing our programs, the disadvantage is that it can lead to ambiguity. 