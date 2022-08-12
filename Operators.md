All dialects support the following standard operators:

- [Comparison][sql-comp]: `=`, `>`, `>=`, `<`, `<=`, `<>`, `!=`
- [Boolean][sql-bool]: `AND`, `OR`, `NOT`, `IS`, `IS NOT`
- [Math][sql-math]: `+`, `-`, `*`, `/`

The standard also defines operators that aren't supported a lot in actual implementations:

- `::` [static method invocation][]
- `->` [attribute or method reference][]
- `||` [string concatenation][]
- `..` embedded [Ada][] and [Pascal][] syntax

Below only additional non-standard operators are listed (the uncommon ones (`::`, `->`, `||`, `..`) are assumed to be unsupported unless mentioned otherwise):

#### SingleStoreDB:

- [Comparison operators][ssdb-comp]: `<=>` (NULL-safe equal operator)
- [Bitwise operators][ssdb-bit]: `&`, `|`, `^`, `~`, `>>`, `<<`
- Boolean operators:<sup>1</sup> `&&`, `||`
- [Variable assignment][ssdb-var]:<sup>2</sup> `:=`

#### [SQLite:][sqlite]

- bitwise: `~`, `&`, `|`, `<<`, `>>`
- arithmetic: `%` (modulus)
- comparison: `==`
- string concatenation: `||`
- JSON: `->`, `->>`

Notes:

1. Tested SingleStoreDB boolean operators manually. Found no docs for these.
2. SingleStoreDB only clearly documents the use of `=` operator for assignment, but testing shows that `:=` works as well (the docs also contain a lonely example that uses the `:=` syntax).

[sql-comp]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#comp-op
[sql-bool]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#boolean-value-expression
[sql-math]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#numeric-value-expression
[static method invocation]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_17_static_method_invocation
[attribute or method reference]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_19_attribute_or_method_reference
[ada]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_21_3_embedded_sql_ada_program
[pascal]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_21_8_embedded_sql_pascal_program
[string concatenation]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_28_string_value_expression
[ssdb-comp]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/comparison-operators-and-functions.html
[ssdb-bit]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/numeric-functions/bitwise-and----.html
[ssdb-var]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/user-defined-variables/set.html
[sqlite]: https://www.sqlite.org/lang_expr.html#operators_and_parse_affecting_attributes