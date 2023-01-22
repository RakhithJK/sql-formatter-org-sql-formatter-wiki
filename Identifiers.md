## Normal identifiers

Most dialects support `[a-zA-Z_]` as first character and `[a-zA-Z0-9_]` as rest of the characters.
The differences from this are listed below:

- [BigQuery][]: single dashes (`-`) can be used, but not at the beginning or end.
- [DB2][]: first char can be an uppercase letter, [`@`, `#`, or `$`.][db2lib] (a lowercase letter gets converted to uppercase). See also [#550][issue550].
- [Hive][]: _(no differences)_
- [MariaDB][]: no first-letter restrictions. The characters `[a-zA-Z0-9_$]` and unicode letters are allowed everywhere. Can begin with digit, but can't only contain digits.
- [MySQL][]: same as MariaDB.
- [N1QL][]: _(no differences)_
- [PL/SQL][]: can't start with `_`. Allows `$`, `#` in rest of the identifier.
- [PostgreSQL][]: additionally `$` after first char. Also unicode letters are allowed.
- [Redshift][]: also unicode letters are allowed. `#` is allowed as the first char of [temporary table names][redshift-temp].
- SingleStoreDB: Same as MariaDB.<sup>5</sup>
- [Snowflake][]: additionally `$` after first char allowed.
- [Spark][]: _Seems like the usual syntax is allowed. But the docs are confusing._
- [SQLite][sqlite-syntax-pdf]: _(no differences)_
- [Transact-SQL][]: `@` and `#` are allowed as first chars plus `$` in the rest. Also unicode letters are allowed.
  Though the beginning `@` signifies a local variable or parameter and `#` a temporary table or procedure.
- [Trino][]: _(no differences)_<sup>4</sup>

## Delimited identifiers

SQL standard specifies double-quotes `".."` for delimited identifiers.
There is a considerable variation in implementations:

- `` `..` `` [BigQuery][]
- `".."` [DB2][] (repeated `"` used for escaping)
- `` `..` `` [Hive][] (repeated `` ` `` used for escaping)
- `` `..` ``, (`".."`<sup>1</sup>, `[..]`<sup>2</sup>) [MariaDB][] (repeated `` ` `` used for escaping)
- `` `..` ``, (`".."`<sup>1</sup>) [MySQL][] (repeated `` ` `` used for escaping)
- `` `..` `` SingleStoreDB<sup>5</sup>
- `` `..` `` [N1QL][]
- `".."` [PL/SQL][pl/sql-quotes] (escaping of quotes is not supported)
- `".."`, `U&".."` [PostgreSQL][] (repeated `"` used for escaping)
- `".."` [Redshift][] (repeated `"` used for escaping)
- `".."` [Snowflake][] (repeated `"` used for escaping)
- `` `..` `` [Spark][] (repeated `` ` `` used for escaping)
- `".."`, `` `..` ``, `[..]` [SQLite][sqlite-keywords] (repeated `"` or `` ` `` used for escaping)
- `".."`<sup>3</sup>, `[..]` [Transact-SQL][] (repeated `"` or `]` used for escaping)
- `".."`<sup>4</sup> [Trino][] (repeated `"` used for escaping)

Notes:

1. when ANSI_QUOTES mode enabled
2. when MSSQL mode enabled
3. unless QUOTED_IDENTIFIER option has been set OFF
4. Trino grammar lists `` `..` ``-quoted identifiers and identifiers starting with number, only to print an error message saying: these aren't supported.
5. Tested SingleStoreDB syntax manually. Haven't found any documentation for these low-level details.

[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/lexical
[db2]: https://www.ibm.com/docs/en/db2/9.7?topic=elements-identifiers
[db2lib]: https://jazz.net/sandbox01-clmhelp/index.jsp?topic=%2Fcom.ibm.team.scm.doc%2Ftopics%2Fr_RTCp_libraryparms.html
[issue550]: https://github.com/sql-formatter-org/sql-formatter/issues/550
[hive]: https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=27362034#LanguageManualDDL-AlterColumn
[mariadb]: https://mariadb.com/kb/en/identifier-names/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/identifiers.html
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/identifiers.html
[pl/sql]: https://docs.oracle.com/database/121/LNPLS/fundamentals.htm#LNPLS99973
[pl/sql-quotes]: https://docs.oracle.com/cd/B19306_01/server.102/b14200/sql_elements008.htm
[postgresql]: https://www.postgresql.org/docs/current/sql-syntax-lexical.html#SQL-SYNTAX-IDENTIFIERS
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/r_names.html
[redshift-temp]: https://docs.aws.amazon.com/redshift/latest/dg/r_CREATE_TABLE_NEW.html
[snowflake]: https://docs.snowflake.com/en/sql-reference/identifiers-syntax.html
[spark]: https://spark.apache.org/docs/latest/sql-ref-identifier.html
[sqlite-keywords]: https://www.sqlite.org/lang_keywords.html
[sqlite-syntax-pdf]: https://www.pearsonhighered.com/assets/samplechapter/0/6/7/2/067232685X.pdf
[transact-sql]: https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-identifiers?view=sql-server-ver15
[trino]: https://github.com/trinodb/trino/blob/ca7dcaa873b9dd24185e9a69cecdd1dd8717694c/core/trino-parser/src/main/antlr4/io/trino/sql/parser/SqlBase.g4#L1175-L1189
