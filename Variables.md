- [BigQuery][]: identifier syntax
- [DB2][]: identifier syntax
- [Hive][]: `${hivevar:name}`, `${hiveconf:name}`, `${system:name}` or `${name}`. These are substitution variables (as in Oracle SQL terminology).
  They behave more like string-interpolation, that is, the values aren't automatically escaped by the system.
  A common example is to place the variable inside a string: `SELECT * FROM users WHERE name = '${hivevar:USER_NAME}'`.
  Also one can use the variable to parameterize table or column name (`SELECT * FROM ${hivevar:my_table}`).
  See also [post in StackOverflow][hive-stackoverflow].
- [MariaDB][]: `@name` (where the name consists of alphanumeric characters, `.`, `_`, and `$`), `@'var name'`, `@"var name"`, `` @`var name` `` (can be quoted as string or identifier). Also `@@name` for [system variables.][mariadb-system-vars]
- [MySQL][]: Same as MariaDB. ([System variables][mysql-system-vars]).
- N1QL: _N/A_
- [PL/SQL][]: `&name` or `&&name` substitution variables (and `:name` bind variables - see [parameters][]).
- [PostgreSQL][]: identifier syntax (only in PL/pgSQL).
- Redshift: _N/A_
- [SingleStoreDB][]:<sup>1</sup> `@name` (where the name consists of alphanumeric characters, `_`, and `$`), `` @`var name` ``. Also `@@name` for system variables.
- [Snowflake][]: 
  - `$name` (using identifier syntax for name)
  - `$number` references the column at this place (from left to right) in the table, see [here](https://docs.snowflake.com/en/sql-reference/sql/select.html#parameters)
- [Spark][]: `${name}` Like with Hive, these are substitution variables.
- SQLite: _N/A_
- [Transact-SQL][]: `@name` (using identifier syntax for name)
- Trino: _N/A_

Notes:

1. Tested SingleStoreDB syntax manually. Found no full documentation of variable syntax.

[parameters]: ./parameters
[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/procedural-language
[db2]: https://www.ibm.com/docs/en/db2-for-zos/11?topic=pl-references-sql-parameters-variables
[hive]: https://cwiki.apache.org/confluence/display/Hive/LanguageManual+VariableSubstitution
[hive-stackoverflow]: https://stackoverflow.com/questions/12464636/how-to-set-variables-in-hive-scripts
[mariadb]: https://mariadb.com/kb/en/user-defined-variables/
[mariadb-system-vars]: https://mariadb.com/kb/en/set/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/user-variables.html]
[mysql-system-vars]: https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html
[pl/sql]: https://docs.oracle.com/en/database/oracle/oracle-database/21/sqpug/using-substitution-variables-sqlplus.html#GUID-0BEEC1D7-876B-495C-9327-17037652D3D2
[postgresql]: https://www.postgresql.org/docs/current/sql-declare.html
[singlestoredb]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/user-defined-variables/set.html
[snowflake]: https://docs.snowflake.com/en/sql-reference/session-variables.html
[spark]: https://stackoverflow.com/questions/65019868/how-to-use-variables-in-sql-queries
[transact-sql]: https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-identifiers?view=sql-server-ver15
