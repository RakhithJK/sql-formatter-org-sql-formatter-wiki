No such statement in SQL standard, but it's widely supported across implementations:

[BigQuery][]:

    TRUNCATE TABLE table_name

[DB2][]:

    TRUNCATE [TABLE] table_name
      [DROP STORAGE | REUSE STORAGE]
      [IGNORE DELETE TRIGGERS | RESTRICT WHEN DELETE TRIGGERS]
      [RESTRICT WHEN DELETE TRIGGERS]
      IMMEDIATE

[Hive][]:

    TRUNCATE [TABLE] table_name
      [PARTITION partition_spec]

[MariaDB][]:

    TRUNCATE [TABLE] table_name
      [WAIT n | NOWAIT]

[MySQL][]:

    TRUNCATE [TABLE] table_name

[N1QL][]:

_No support for TRUNCATE_

[PL/SQL][]:

    TRUNCATE TABLE table_name
      [{PRESERVE | PURGE} MATERIALIZED VIEW LOG]
      [{DROP [ALL] | REUSE} STORAGE]
      [CASCADE]

[PostgreSQL][]:

    TRUNCATE [TABLE] [ONLY] table_name ["*"] ["," ...]
      [RESTART IDENTITY | CONTINUE IDENTITY]
      [CASCADE | RESTRICT]

[Redshift][]:

    TRUNCATE [TABLE] table_name

[SingleStoreDB][]:

    TRUNCATE [TABLE] table_name

[Snowflake][]:

    TRUNCATE [TABLE] [IF EXISTS] table_name

[Spark][]:

    TRUNCATE TABLE table_name
      [PARTITION "(" name "=" value [","...] ")"]

[SQLite][]:

_No support for TRUNCATE_

[Transact-SQL][]:

    TRUNCATE TABLE table_name
    [WITH "(" PARTITIONS "(" {partition_number | partition_number TO partition_number} ["," ...] ")" ")"]

[Trino][]:

    TRUNCATE TABLE table_name

[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/dml-syntax#truncate_table_statement
[db2]: https://www.ibm.com/docs/en/db2/9.7?topic=statements-truncate
[hive]: https://cwiki.apache.org/confluence/display/Hive/LanguageManual+DDL#LanguageManualDDL-TruncateTable
[mariadb]: https://mariadb.com/kb/en/truncate-table/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/index.html
[pl/sql]: https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/TRUNCATE-TABLE.html
[postgresql]: https://www.postgresql.org/docs/current/sql-truncate.html
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/r_TRUNCATE.html
[singlestoredb]: https://docs.singlestore.com/managed-service/en/reference/sql-reference/data-definition-language-ddl/truncate.html
[snowflake]: https://docs.snowflake.com/en/sql-reference/sql/truncate-table.html
[spark]: https://spark.apache.org/docs/3.3.0/sql-ref-syntax-ddl-truncate-table.html
[sqlite]: https://www.sqlite.org/lang.html
[transact-sql]: https://docs.microsoft.com/en-us/sql/t-sql/statements/truncate-table-transact-sql?view=sql-server-ver16
[trino]: https://trino.io/docs/current/sql/truncate.html
