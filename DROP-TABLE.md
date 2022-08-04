[SQL standard][] specifies the following DROP TABLE syntax:

    DROP TABLE table_name {CASCADE | RESTRICT}

Dialects have considerable variation:

[BigQuery][]:

    DROP [EXTERNAL | SNAPSHOT] TABLE [IF EXISTS] table_name

[DB2][]:

    DROP TABLE table_name

[Hive][]:

    DROP TABLE [IF EXISTS] table_name [PURGE]

[MariaDB][]:

    DROP [TEMPORARY] TABLE [IF EXISTS] table_name ["," ...]
      [WAIT n | NOWAIT]
      [RESTRICT | CASCADE]

[MySQL][]:

    DROP [TEMPORARY] TABLE [IF EXISTS] table_name ["," ...]
      [RESTRICT | CASCADE]

[N1QL][]:

_No support for DROP TABLE._

[PL/SQL][]:

    DROP TABLE table_name [CASCADE CONSTRAINTS] [PURGE]

[PostgreSQL][]:

    DROP TABLE [IF EXISTS] table_name ["," ...] [CASCADE | RESTRICT]

[Redshift][]:

    DROP TABLE [IF EXISTS] table_name ["," ...] [CASCADE | RESTRICT]

[Spark][]:

    DROP TABLE [IF EXISTS] table_name

[SQLite][]:

    DROP TABLE [IF EXISTS] table_name

[Transact-SQL][]:

    DROP TABLE [IF EXISTS] table_name ["," ...]

[Trino][]:

    DROP TABLE [IF EXISTS] table_name

[sql standard]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_11_21_drop_table_statement
[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#drop_table_statement
[db2]: https://www.ibm.com/docs/en/db2/9.7?topic=statements-drop
[hive]: https://cwiki.apache.org/confluence/display/Hive/LanguageManual+DDL#LanguageManualDDL-DropTable
[mariadb]: https://mariadb.com/kb/en/drop-table/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/drop-table.html
[n1ql]: https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/DROP-TABLE.html
[pl/sql]: https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/CREATE-TABLE.html
[postgresql]: https://www.postgresql.org/docs/current/sql-droptable.html
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/r_DROP_TABLE.html
[spark]: https://spark.apache.org/docs/latest/sql-ref-syntax-ddl-drop-table.html
[sqlite]: https://www.sqlite.org/lang_droptable.html
[transact-sql]: https://docs.microsoft.com/en-us/sql/t-sql/statements/drop-table-transact-sql?view=sql-server-ver15
[trino]: https://trino.io/docs/current/sql/drop-table.html
