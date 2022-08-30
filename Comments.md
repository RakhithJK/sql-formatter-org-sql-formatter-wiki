[Standard SQL][sql] supports two types of comments:

```sql
-- single line comment

/* multi line
   block comment */
```

These are supported by all dialects.

## Nested block comments

According to standard, block comments can also be nested, like:

```sql
/* main comment
   /* sub-comment */
*/
```

This is however only supported by some dialects:

- [PostgreSQL](https://www.postgresql.org/docs/8.0/sql-syntax.html#SQL-SYNTAX-COMMENTS)
- [Transact-SQL](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/slash-star-comment-transact-sql?view=sql-server-ver16)
- MariaDB and MySQL docs mention that nested comments might be supported in some places, but their support is deprecated and one is advised not to use them.

## Hash comments

Some dialects additionally support shell-style hash-comments:

```sql
# a comment
```

- [BigQuery](https://cloud.google.com/bigquery/docs/reference/standard-sql/lexical#comments)
- [MariaDB](https://mariadb.com/kb/en/comment-syntax/)
- [MySQL](https://dev.mysql.com/doc/refman/8.0/en/comments.html)
- SingleStoreDB?

## Links to comment syntax in all dialects

- [BigQuery](https://cloud.google.com/bigquery/docs/reference/standard-sql/lexical#comments)
- [DB2](https://www.ibm.com/docs/en/db2/9.7?topic=statements-sql-comments)
- [Hive](https://issues.apache.org/jira/browse/HIVE-15765)
- [MariaDB](https://mariadb.com/kb/en/comment-syntax/)
- [MySQL](https://dev.mysql.com/doc/refman/8.0/en/comments.html)
- [N1QL](https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/index.html#block-comments)
- [PL/SQL](https://docs.oracle.com/en/database/oracle/oracle-database/19/lnpls/comment.html)
- [PostgreSQL](https://www.postgresql.org/docs/8.0/sql-syntax.html#SQL-SYNTAX-COMMENTS)
- Redshift ???
- SingleStoreDB ???
- [Spark](https://stackoverflow.com/questions/68680440/commenting-in-spark-sql)
- [SQLite](https://www.sqlite.org/lang_comment.html)
- [Transact-SQL](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/slash-star-comment-transact-sql?view=sql-server-ver16)
- [Trino](https://github.com/trinodb/trino/blob/c7b26825218d5d11e9469984977dee6856f362ff/core/trino-parser/src/main/antlr4/io/trino/sql/parser/SqlBase.g4#L1202)

[sql]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#comment