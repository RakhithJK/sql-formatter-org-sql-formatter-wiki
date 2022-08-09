All dialects support the following standard operators:

- `=`, `>`, `>=`, `<`, `<=`, `<>`, `!=`

Below only additional non-standard operators are listed.

#### SingleStoreDB:

- [Comparison operators][ssdb-comp]: `<=>` (NULL-safe equal operator)
- [Bitwise operators][ssdb-bit]: `&`, `|`, `^`, `~`, `>>`, `<<`
- Boolean operators:<sup>1</sup> `AND`, `&&`, `OR`, `||`

Notes:

1. Tested SingleStoreDB boolean operators manually. Found no docs for these.

[ssdb-comp]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/comparison-operators-and-functions.html
[ssdb-bit]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/numeric-functions/bitwise-and----.html