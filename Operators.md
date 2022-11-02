All dialects support the following standard operators:

- [Arithmetic][sql-math]: `+`, `-`, `*`, `/`
- [Comparison][sql-comp]: `=`, `>`, `>=`, `<`, `<=`, `<>`, `!=`
- [Logical][sql-bool]: `AND`, `OR`, `NOT`, `IS`, `IS NOT`

The standard also defines operators that aren't supported a lot in actual implementations:

- `::` [static method invocation][]
- `->` [attribute or method reference][]
- `||` [string concatenation][]
- `..` embedded [Ada][] and [Pascal][] syntax

Below only additional non-standard operators are listed (the uncommon ones (`::`, `->`, `||`, `..`) are assumed to be unsupported unless mentioned otherwise):

#### [BigQuery](https://cloud.google.com/bigquery/docs/reference/standard-sql/operators):

- Bitwise: `&`, `|`, `^`, `~`, `<<`, `>>`
- String/Array concatenation: `||`

#### [DB2](https://www.ibm.com/docs/en/i/7.2?topic=le-expressions):

- [Arithmetic][db2-math]: `**`
- [Comparison][db2-comp]: `¬=`, `¬>`, `!>`, `¬<`, `!<`
- String concatenation: `CONCAT`, `||`

#### [Hive](https://cwiki.apache.org/confluence/display/Hive/LanguageManual+UDF):

- Arithmetic: `%`, `DIV`
- Bitwise: `~`, `^`, `|`, `&`
- Comparison: `==`, `<=>` (NULL-safe equal operator)
- Logical: `!`
- String concatenation: `||`

#### [MariaDB][]:

- Arithmetic: `%`, `MOD`, `DIV`
- Assignment: `:=`
- Bitwise: `&`, `|`, `^`, `~`, `>>`, `<<`
- Comparison: `<=>` (NULL-safe equal operator)
- Logical: `&&`, `||`, `XOR`, `!`

#### [MySQL][]:

- Arithmetic: `%`, `MOD`, `DIV`
- Assignment: `:=`
- Bitwise: `&`, `|`, `^`, `~`, `>>`, `<<`
- Comparison: `<=>` (NULL-safe equal operator)
- JSON: `->`, `->>`
- Logical: `&&`, `||`, `XOR`, `!`

#### [N1QL](https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/operators.html):

- Arithmetic: `%`
- Comparison: `==`
- [Object key-value separator][n1ql-obj]: `:`
- String concatenation: `||`

#### [PL/SQL](https://docs.oracle.com/cd/E11882_01/appdev.112/e25519/fundamentals.htm#LNPLS189):

- Arithmetic: `**`<sup>3</sup>
- [Assignment][plsql-var]: `:=`
- Attribute indicator: `%`
- [Comparison][plsql-comp]: `^=`, `~=`<sup>3</sup>
- [FOR loop range][plsql-for]: `..`
- [Label delimiters][plsql-label]: `<<`, `>>`
- [Named arguments][plsql-arg]: `=>`
- Remote access indicator: `@`
- String concatenation: `||`

#### [PostgreSQL][]:

- [Arithmetic][psql-math]: `%`, `^`, `|/` (square root), `||/` (cube root), `@` (abs value)
- [Assignment][psql-assign]: `:=`
- [Bitwise][psql-math]: `&`, `|`, `#`, `~`, `>>`, `<<`
- [Byte comparison][psql-byte]: `~>=~`, `~<=~`, `~>~`, `~<~`
- [Geometric][psql-geo]: `@-@`, `@@`, `#`, `##`, `<->`, `@>`, `<@`, `&&`, `<<`, `>>`, `&<`, `&>`, `<<|`, `|>>`, `&<|`, `|&>`, `<^`, `>^`, `?#`, `?-`, `?|`, `?-|`, `?||`, `~=`
- [JSON][psql-json]: `->`, `->>`, `#>`, `#>>`, `@>`, `?`, `?|`, `?&`, `||`, `#-`, `@?`, `@@`
- [Named function params][psql-func]: `=>`
- [Network address][psql-net]: `<<`, `>>`, `<<=`, `>>=`, `&&`, `~`, `&`, `|`
- [Pattern matching][psql-like]: `~~`, `~~*`, `!~~`, `!~~*`
- [Posix Regex][psql-regex]: `~`, `~*`, `!~`, `!~*`
- [Range/multirange][psql-range]: `@>`, `<@`, `&&`, `<<`, `>>`, `&<`, `&>`, `-|-`, 
- String concatenation: `||`
- [Text search][psql-txt]: `@@`, `@@@`, `||`, `&&`, `!!`, `<->`, `@>`, `<@`
- [Trigram/trigraph][psql-trgm]: `%`, `<%`, `%>`, `<<%`, `%>>`, `<->`, `<<->`, `<->>`, `<<<->`, `<->>>`
- [Type cast][psql-cast]: `::`

#### [Redshift](https://docs.aws.amazon.com/redshift/latest/dg/r_compound_expressions.html):

- Arithmetic: `^`, `%`, `@` (absolute value), `|/` (square root) `||/` cube root
- Bitwise: `&`, `|`, `#`, `~`, `<<`, `>>`
- String concatenation: `||`
- [Type cast](https://docs.aws.amazon.com/redshift/latest/dg/r_CAST_function.html): `::`

#### SingleStoreDB:

- [Assignment][ssdb-var]:<sup>2</sup> `:=`
- [Bitwise][ssdb-bit]: `&`, `|`, `^`, `~`, `>>`, `<<`
- [Comparison][ssdb-comp]: `<=>` (NULL-safe equal operator)
- Logical:<sup>1</sup> `&&`, `||`

#### [Snowflake][]:
- [Arithmethic][snow-math]: `%`
- [Generator][snow-generator]: `=>`
- [Path][snow-path]: `:`
- [String concatenation][snow-string]: `||`
- [Type cast][snow-cast]: `::`

#### [Spark](https://spark.apache.org/docs/3.3.0/sql-migration-guide.html#compatibility-with-apache-hive):

Same as Hive. Additionally (perhaps also in Hive?):

- [Lambda expression][spark-lambda]: `->`

#### [SQLite][]:

- Arithmetic: `%`
- Bitwise: `~`, `&`, `|`, `<<`, `>>`
- Comparison: `==`
- JSON: `->`, `->>`
- String concatenation: `||`

#### Transact-SQL:

- [Arithmetic][tsql-math]: `%`
- [Bitwise][tsql-bit]: `&`, `|`, `^`, `~`
- [Comparison][tsql-comp]: `!<`, `!>`
- [Compound][tsql-compound]: `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `|=`, `^=`
- [Scope resolution][tsql-scope]: `::`

#### [Trino][]:

- Arithmetic: `%`
- [Lambda expression][trino-lambda]: `->`
- [Named arguments][trino-arg]: `=>`
- [Object key-value separator][trino-obj]: `:`
- [Row pattern syntax][trino-row]: `+`, `|`, `*`, `?`, `$`, `(`..`)`, `{-`..`-}`, `{n}`, `{m,n}`
- String concatenation: `||`

Notes:

1. Tested SingleStoreDB boolean operators manually. Found no docs for these.
2. SingleStoreDB only clearly documents the use of `=` operator for assignment, but testing shows that `:=` works as well (the docs also contain a lonely example that uses the `:=` syntax).
3. Tested on [Oracle Live SQL playground](https://livesql.oracle.com/apex/f?p=590:1:5443282639708::NO:RP::) the following operators: `**`, `~=`. Both of them produced an error.

[sql-comp]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#comp-op
[sql-bool]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#boolean-value-expression
[sql-math]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#numeric-value-expression
[static method invocation]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_17_static_method_invocation
[attribute or method reference]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_19_attribute_or_method_reference
[ada]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_21_3_embedded_sql_ada_program
[pascal]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_21_8_embedded_sql_pascal_program
[string concatenation]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_28_string_value_expression
[db2-math]: https://www.ibm.com/docs/en/i/7.2?topic=clause-expressions-in-where
[db2-comp]: https://www.ibm.com/docs/en/i/7.2?topic=clause-comparison-operators
[mariadb]: https://mariadb.com/kb/en/operators/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html
[n1ql-obj]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/datatypes.html#objects
[plsql-comp]: https://docs.oracle.com/database/121/SQLRF/conditions002.htm
[plsql-arg]: https://docs.oracle.com/database/121/SQLRF/expressions008.htm
[plsql-var]: https://docs.oracle.com/cd/B19306_01/appdev.102/b14261/fundamentals.htm
[plsql-for]: https://docs.oracle.com/en/database/oracle/oracle-database/19/lnpls/FOR-LOOP-statement.html
[plsql-label]: https://docs.oracle.com/cd/B19306_01/appdev.102/b14261/goto_statement.htm
[postgresql]: https://www.postgresql.org/docs/14/functions.html
[psql-math]: https://www.postgresql.org/docs/14/functions-math.html
[psql-like]: https://www.postgresql.org/docs/14/functions-matching.html#FUNCTIONS-LIKE
[psql-regex]: https://www.postgresql.org/docs/14/functions-matching.html#FUNCTIONS-POSIX-REGEXP
[psql-net]: https://www.postgresql.org/docs/14/functions-net.html
[psql-geo]: https://www.postgresql.org/docs/14/functions-geometry.html
[psql-txt]: https://www.postgresql.org/docs/14/functions-textsearch.html
[psql-json]: https://www.postgresql.org/docs/14/functions-json.html
[psql-cast]: https://www.postgresql.org/docs/current/sql-createcast.html
[psql-func]: https://www.postgresql.org/docs/current/sql-syntax-calling-funcs.html
[psql-assign]: https://www.postgresql.org/docs/9.4/plpgsql-statements.html
[psql-range]: https://www.postgresql.org/docs/current/functions-range.html
[psql-trgm]: https://www.postgresql.org/docs/current/pgtrgm.html
[psql-byte]: https://stackoverflow.com/questions/35807872/operator-in-postgres/35808554#35808554
[snowflake]: https://docs.snowflake.com/en/sql-reference/functions-all.html
[snow-cast]: https://docs.snowflake.com/en/sql-reference/functions/cast.html#cast
[snow-generator]: https://docs.snowflake.com/en/sql-reference/functions/generator.html#generator
[snow-math]: https://docs.snowflake.com/en/sql-reference/operators-arithmetic.html
[snow-path]: https://docs.snowflake.com/en/sql-reference/functions/get_path.html#get-path
[snow-string]: https://docs.snowflake.com/en/sql-reference/functions/concat.html#concat
[ssdb-comp]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/comparison-operators-and-functions.html
[ssdb-bit]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/numeric-functions/bitwise-and----.html
[ssdb-var]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/user-defined-variables/set.html
[spark-lambda]: https://github.com/sql-formatter-org/sql-formatter/issues/176
[sqlite]: https://www.sqlite.org/lang_expr.html#operators_and_parse_affecting_attributes
[tsql-math]: https://docs.microsoft.com/en-us/sql/t-sql/language-elements/arithmetic-operators-transact-sql?view=sql-server-ver16
[tsql-scope]: https://docs.microsoft.com/en-us/sql/t-sql/language-elements/scope-resolution-operator-transact-sql?view=sql-server-ver16
[tsql-bit]: https://docs.microsoft.com/en-us/sql/t-sql/language-elements/bitwise-operators-transact-sql?view=sql-server-ver16
[tsql-compound]: https://docs.microsoft.com/en-us/sql/t-sql/language-elements/compound-operators-transact-sql?view=sql-server-ver16
[tsql-comp]: https://docs.microsoft.com/en-us/sql/t-sql/language-elements/comparison-operators-transact-sql?view=sql-server-ver16
[trino]: https://trino.io/docs/current/functions/list.html#id1
[trino-arg]: https://trino.io/docs/current/functions/table.html#argument-passing-conventions
[trino-lambda]: https://trino.io/docs/current/functions/lambda.html#lambda-expressions
[trino-obj]: https://trino.io/docs/current/functions/json.html?highlight=json#json-object
[trino-row]: https://trino.io/docs/current/sql/match-recognize.html#row-pattern-syntax