Other name: Lexer

# Topics

- [[Regular Expression]]
- [[Finite Automata]]
- [[Regular Expression]] to [[Non Deterministic Finite Automata]]
-  [[Non Deterministic Finite Automata]] to [[Deterministic Finite Automata]]
- Generator of a Lexical Analyzer (FLEX)
- Language Tiny


# Notes

Sistema de varredura 

Sequencias de caractreres são organizados como unidades significativas, chamadas lexemas.

Exemplo : a\[index\] = 4 + 2

| lexemas | tokens              |
| ------- | ------------------- |
| a       | identificador       |
| \[      | colchede á esquerda |
| index   | identificador       |
| ]       | colchete á direita  |
| =       | atribuição          |
| 4       | numero              |
| +       | adição              |
| 2       | numero                    |




no processo de analise lexica, os okens validos da lingugem normalmente sao especificados por expressoes regulares

expressoes regulares representam padroes de cadieas de caracteres

uma expressa regular e 'e completamente definda pelo conjunto de cadeias de caracteres com as quais ela casa