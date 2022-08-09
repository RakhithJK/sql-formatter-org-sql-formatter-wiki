All dialects support the following standard operators:

- [Comparison][sql-comp]: `=`, `>`, `>=`, `<`, `<=`, `<>`, `!=`
- [Boolean][sql-bool]: `AND`, `OR`, `NOT`, `IS`, `IS NOT`
- [Math][sql-math]: `+`, `-`, `*`, `/`

Below only additional non-standard operators are listed.

#### SingleStoreDB:

- [Comparison operators][ssdb-comp]: `<=>` (NULL-safe equal operator)
- [Bitwise operators][ssdb-bit]: `&`, `|`, `^`, `~`, `>>`, `<<`
- Boolean operators:<sup>1</sup> `&&`, `||`

Notes:

1. Tested SingleStoreDB boolean operators manually. Found no docs for these.

[sql-comp]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#comp-op
[sql-bool]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#boolean-value-expression
[sql-math]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#numeric-value-expression
[ssdb-comp]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/comparison-operators-and-functions.html
[ssdb-bit]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/numeric-functions/bitwise-and----.html