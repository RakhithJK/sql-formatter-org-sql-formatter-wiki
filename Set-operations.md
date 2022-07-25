[SQL standard][] defines the following set operations:

      UNION [ALL | DISTINCT]
    | EXCEPT [ALL | DISTINCT]
    | INTERSECT [ALL | DISTINCT]

All dialects support `UNION`, with rest there are variations:

[BigQuery][]:

      UNION {ALL | DISTINCT}
    | EXCEPT DISTINCT
    | INTERSECT DISTINCT

[DB2][]:

      UNION [ALL]
    | EXCEPT [ALL]
    | INTERSECT [ALL]

[Hive][]:

    UNION [ALL | DISTINCT]

[MariaDB][]:

      UNION [ALL | DISTINCT]
    | EXCEPT [ALL | DISTINCT]
    | INTERSECT [ALL | DISTINCT]
    | MINUS [ALL | DISTINCT]

[MySQL][]:

    UNION {ALL | DISTINCT}

[N1QL][]:

      UNION [ALL]
    | EXCEPT [ALL]
    | INTERSECT [ALL]

[PL/SQL][]:

      UNION [ALL]
    | EXCEPT
    | INTERSECT

[PostgreSQL][]:

      UNION [ALL | DISTINCT]
    | EXCEPT [ALL | DISTINCT]
    | INTERSECT [ALL | DISTINCT]

[Redshift][]:

      UNION [ ALL ]
    | EXCEPT
    | INTERSECT
    | MINUS

[Spark][]:

      UNION [ALL | DISTINCT]
    | EXCEPT [ALL | DISTINCT]
    | INTERSECT [ALL | DISTINCT]

[SQLite][]:

      UNION [ALL]
    | EXCEPT
    | INTERSECT

[Transact-SQL][]:

      UNION [ALL]
    | EXCEPT
    | INTERSECT

[Trino][]:

      UNION [ALL | DISTINCT]
    | EXCEPT [ALL | DISTINCT]
    | INTERSECT [ALL | DISTINCT]

[sql standard]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#query-expression-body
[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/query-syntax#set_clause
[db2]: https://www.ibm.com/docs/en/db2/9.7?topic=queries-fullselect
[hive]: https://cwiki.apache.org/confluence/display/Hive/LanguageManual+Union
[mariadb]: https://mariadb.com/kb/en/joins-subqueries/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/select.html
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/union.html
[pl/sql]: https://docs.oracle.com/database/121/SQLRF/queries001.htm
[postgresql]: https://www.postgresql.org/docs/current/sql-select.html#SQL-UNION
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/r_UNION.html
[spark]: https://spark.apache.org/docs/latest/sql-ref-syntax-qry-select.html
[sqlite]: https://www.sqlite.org/lang_select.html#compound_select_statements
[transact-sql]: https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-except-and-intersect-transact-sql?view=sql-server-ver15
[trino]: https://trino.io/docs/current/sql/select.html#set-operations
