No such statement in SQL standard, but it's supported in several implementations:

[BigQuery][]:

    MERGE [INTO] table_name [[AS] alias]
      USING {table_name | query}
      ON condition
      when_clause...

    when_clause:
        WHEN MATCHED [AND condition] THEN action
      | WHEN NOT MATCHED [BY TARGET] [AND condition] THEN action
      | WHEN NOT MATCHED BY SOURCE [AND condition] THEN action

    action:
        UPDATE SET set_clause_list
      | DELETE
      | INSERT [columns_list] {VALUES values_list | ROW}

[DB2][]:

    MERGE INTO table_name [correlation_clause]
      USING table_name
      ON condition
      when_clause...
      [ELSE IGNORE]
      [WITH {RR | RS | CS | UR}

    when_clause:
      WHEN [NOT] MATCHED [AND condition] THEN action

    action:
        UPDATE SET set_clause_list
      | DELETE
      | INSERT [columns_list] VALUES values_list

[Hive][]:

    MERGE INTO table_name [[AS] alias]
      USING expr [[AS] alias]
      ON condition
      WHEN [NOT] MATCHED [AND condition] THEN action

    action:
        UPDATE SET set_clause_list
      | DELETE
      | INSERT VALUES value_list}

[MariaDB][]:

_No support for MERGE_

[MySQL][]:

_No support for MERGE_

[N1QL][]:

    MERGE INTO table_name [[AS] alias]
      [use_index_clause]
      USING expr [[AS] alias] [hints]
      ON [[PRIMARY] KEY] condition
      when_clause...
      [limit_clause]
      [returning_clause]

    use_index_clause:
      USE INDEX "(" index_ref [","...] ")"

    when_clause:
        WHEN MATCHED THEN action [unset_clause] [where_clause]
      | WHEN MATCHED THEN action [where_clause]
      | WHEN NOT MATCHED THEN action [where_clause]

    action:
      | UPDATE SET set_clause_list
      | DELETE
      | INSERT expr
      | INSERT "(" [KEY] key ["," [VALUE] value] ["," [OPTIONS] options] ")"

[PL/SQL][]:

    MERGE [hint] INTO table_name [[AS] alias]
      USING {table_name | query} [[AS] alias]
      ON "(" condition ")"
      when_clause...
      [error_logging_clause]

    when_clause:
        WHEN MATCHED THEN action [where_clause] [DELETE where_clause]
      | WHEN NOT MATCHED THEN action [where_clause]

    action:
        UPDATE SET set_clause_list
      | INSERT columns_list VALUES values_list

[PostgreSQL][]:

_No support for MERGE_

[Redshift][]:

_No support for MERGE_

[Spark][]:

_No support for MERGE_

[SQLite][]:

_No support for MERGE_

[Transact-SQL][]:

    [WITH common_table_expression ["," ...]]
    MERGE [TOP (expression) [PERCENT]] [INTO] table_name
      [WITH (merge_hint)] [[AS] alias]
      USING table_source [[AS] alias]
      ON condition
      when_clause...
      [output_clause]
      [OPTION (query_hint [","...])]

    when_clause:
      WHEN [NOT] MATCHED [BY TARGET | BY SOURCE] [AND condition] THEN action

    action:
        UPDATE SET set_clause_list
      | DELETE
      | INSERT column_list {VALUES values_list | DEFAULT VALUES}

[Trino][]:

_No support for MERGE_

[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/dml-syntax#merge_statement
[db2]: https://www.ibm.com/docs/en/db2/9.7?topic=statements-merge
[hive]: https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=82903069#LanguageManualDML-Merge
[mariadb]: https://mariadb.com/kb/en/truncate-table/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/truncate-table.html
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/merge.html
[pl/sql]: https://docs.oracle.com/en/database/oracle/oracle-database/19/sqlrf/MERGE.html
[postgresql]: https://www.postgresql.org/docs/current/sql-commands.html
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/c_SQL_commands.html
[spark]: https://spark.apache.org/docs/3.3.0/sql-ref-syntax.html
[sqlite]: https://www.sqlite.org/lang.html
[transact-sql]: https://docs.microsoft.com/en-us/sql/t-sql/statements/merge-transact-sql?view=sql-server-ver16
[trino]: https://trino.io/docs/current/sql.html
