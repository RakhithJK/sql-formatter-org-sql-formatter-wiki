SQL standard supports single-quoted strings `'..'` with repeated quote `''` used for escaping.
The real world implementations have lots of variation:

- [BigQuery][]:
  - `".."`, `'..'`, `"""..."""`, `'''..'''` (backslash `\` used for escaping)
  - `R".."`, `r'''..'''` denotes raw strings (backslashes not used for escaping)
  - `B".."`, `b'''..'''` denotes binary strings (backslashes not used for escaping)
  - `RB".."`, `br'''..'''` the same as above, raw and binary (backslashes not used for escaping)
- [DB2][]:
  - `'..'` (two single quotes `''` are used for escaping)
  - `X'..'` a hex string (no escaping)
  - `G'..'`, `N'..'` a graphic string
  - `BX'..'` a binary hex string (no escaping)
  - `GX'..'` a graphic hex string (no escaping)
  - `UX'..'` a Unicode hex string / UCS-2 graphic string (no escaping)
  - `U&'..'` [a Unicode string][db2-unicode] (two single quotes `''` are used for escaping)
- [Hive][]: `'..'`, `".."` (backslash `\` used for escaping)
- [MariaDB][]:
  - `'..'`, `".."`<sup>2</sup> (backslash `\`<sup>1</sup> or repeated single-quote `''` used for escaping)
  - `x'..'`, `X'..'` [hex string][mariadb-hex]
  - `b'..'`, `B'..'` a binary string
- [MySQL][]:
  - `'..'`, `".."`<sup>2</sup> (backslash `\`<sup>1</sup> or repeated quote (`''` or `""`) used for escaping)
  - `x'..'`, `X'..'` [hex string][mysql-hex]
  - `N'..'`, `n'..'` a string using a natural character set
- [N1QL][]: `".."` (backslash `\` used for escaping)
- [PL/SQL][]:
  - `'..'` (two single quotes `''` are used for escaping)
  - `N'..'`, `n'..'` a string using a natural character set
  - `Q'x..x'`, `q'x..x'` where `x` is a custom delimiter character
  - `q'{..}'`, `q'[..]'`, `q'<..>'`, `q'(..)'` special handling for certain delimiters in above syntax
- [PostgreSQL][]:
  - `'..'` (two single quotes `''` are used for escaping)
  - `E'..'`, `e'..'` string with C-style escapes (backslash `\` or repeated single-quote `''` used for escaping)
  - `U&'..'`, `u&'..'` string with unicode escapes
  - `$$..$$`, `$delim$..$delim$` dollar-quoted string with optional custom delimiters
  - `B'..'`, `b'..'` bit string
  - `X'..'`, `x'..'` hex string
- [Redshift][]: `'..'`
- SingleStoreDB:<sup>5</sup>
  - `'..'`, `".."` (backslash `\` or repeated quote (`''` or `""`) used for escaping)
  - `x'..'`, `X'..'` hex string
  - `b'..'`, `B'..'` a binary string
- [Spark][]:
  - `'..'`, `".."` (backslash `\` used for escaping)
  - `r'..'`, `r".."`, `R'..'`, `R".."` raw string (no escaping)
  - `X'..'`, `X".."` hex string
- [SQLite][]:
  - `'..'`, (`".."`<sup>4</sup>) (two quotes `''` are used for escaping)
  - `X'..'`, `x'..'` hex string
- [Transact-SQL][]:
  - `'..'` (two single quotes `''` are used for escaping)
  - (`".."`<sup>3</sup>)
  - `N'..'` (`N".."`<sup>3</sup>) unicode strings
- [Trino][]:
  - `'..'` (two single quotes `''` are used for escaping)
  - `X'..'`, `x'..'` hex string
  - `U&'..'`, `u&'..'` string with unicode escapes (two single quotes `''` are used for escaping)

### Notes:

1. unless the SQL_MODE has been set to NO_BACKSLASH_ESCAPES.
2. unless ANSI_QUOTES mode is enabled.
3. if the QUOTED_IDENTIFIER option has been set OFF.
4. SQLite sometimes [bends its quoting rules.][sqlite-note] It treats double-quoted identifiers as strings when they appear in the context where strings are expected, but identifiers are not.
5. Tested SingleStoreDB manually. Haven't found any actual documentation about string syntax.

[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/lexical#string_and_bytes_literals
[db2]: https://www.ibm.com/docs/en/db2/9.7?topic=elements-constants
[db2-unicode]: https://www.ibm.com/docs/en/db2/9.7?topic=database-language-aware-collation
[hive]: https://cwiki.apache.org/confluence/display/hive/languagemanual%20types#LanguageManualTypes-StringsstringStrings
[mariadb]: https://mariadb.com/kb/en/string-literals/
[mariadb-hex]: https://mariadb.com/kb/en/hexadecimal-literals/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/string-literals.html
[mysql-hex]: https://dev.mysql.com/doc/refman/8.0/en/hexadecimal-literals.html
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/literals.html#strings
[pl/sql]: https://docs.oracle.com/cd/B19306_01/server.102/b14200/sql_elements003.htm#i42617
[postgresql]: https://www.postgresql.org/docs/current/sql-syntax-lexical.html#SQL-SYNTAX-CONSTANTS
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/r_Examples_with_character_types.html
[spark]: https://spark.apache.org/docs/latest/sql-ref-literals.html#string-literal
[sqlite]: https://www.sqlite.org/lang_expr.html#literal_values_constants_
[sqlite-note]: https://www.sqlite.org/lang_keywords.html
[transact-sql]: https://docs.microsoft.com/en-us/sql/t-sql/data-types/constants-transact-sql?view=sql-server-ver15
[trino]: https://github.com/trinodb/trino/blob/ca7dcaa873b9dd24185e9a69cecdd1dd8717694c/core/trino-parser/src/main/antlr4/io/trino/sql/parser/SqlBase.g4#L1146-L1159
