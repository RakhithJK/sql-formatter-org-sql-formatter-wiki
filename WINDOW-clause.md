[SQL standard][] defines the following syntax for WINDOW clause:

    WINDOW { identifier AS "(" window_specification ")" } ["," ...]

and the following syntax for [window functions][sql-win-func]:

    function_call OVER { window_name | "(" window_specification ")" }

where `window_specification` in both is as follows:

    window_specification:
      [identifier]
      [PARTITION BY { column [COLLATE collation] } ["," ...]]
      [ORDER BY sort_specification_list]
      [frame_definition]

    frame_definition:
      frame_units {frame_start | frame_between} [frame_exclusion]

    frame_units:
      ROWS | RANGE

    frame_start:
      UNBOUNDED PRECEDING | CURRENT ROW | unsigned_value PRECEDING

    frame_between:
      BETWEEN frame_bound AND frame_bound

    frame_bound:
      frame_start | UNBOUNDED FOLLOWING | unsigned_value FOLLOWING

    frame_exclusion:
        EXCLUDE CURRENT ROW
      | EXCLUDE GROUP
      | EXCLUDE TIES
      | EXCLUDE NO OTHERS

No dialect supports `COLLATE` in `PARTITION BY`.
Other than that, the following dialects support everything else:

|                           | WINDOW clause      | Window function    |
|---------------------------|--------------------|--------------------|
| [BigQuery][]              | :heavy_check_mark: | :heavy_check_mark: |
| [DB2][]                   |                    | :heavy_check_mark: |
| [Hive][]                  | :heavy_check_mark: | :heavy_check_mark: |
| [MySQL][]                 | :heavy_check_mark: | :heavy_check_mark: |
| [MariaDB][]               |                    | :heavy_check_mark: |
| [N1QL][]<sup>1</sup>      | :heavy_check_mark: | :heavy_check_mark: |
| [PL/SQL][]                |                    | :heavy_check_mark: |
| [PostgreSQL][]<sup>1</sup>| :heavy_check_mark: | :heavy_check_mark: |
| [Redshift][]              |                    | :heavy_check_mark: |
| [SingleStoreDB][]         |                    | :heavy_check_mark: |
| [Snowflake][]             |                    | :heavy_check_mark: |
| [Spark][]                 | :heavy_check_mark: | :heavy_check_mark: |
| [SQLite][]<sup>1</sup>    | :heavy_check_mark: | :heavy_check_mark: |
| [Trino][]<sup>1, 2</sup>  | :heavy_check_mark: | :heavy_check_mark: |
| [Transact-SQL][]          | :heavy_check_mark: | :heavy_check_mark: |

1. These dialects support an extra `GROUPS` option in `frame_units`:

        frame_units:
          ROWS | RANGE | GROUPS

2. [Trino][] supports an additional pattern matching syntax around `frame_definition`:

        trino_frame_definition:
          [MEASURES measure_definition ["," ...]]
          frame_definition
          [AFTER MATCH skip_to]
          [INITIAL | SEEK]
          [PATTERN "(" row_pattern ")"]
          [SUBSET subset_definition ["," ...]]
          [DEFINE variable_definition ["," ...]]

    [Trino][] does not support `frame_exclusion`.


[sql standard]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_7_11_window_clause
[sql-win-func]: https://jakewheat.github.io/sql-overview/sql-2008-foundation-grammar.html#_6_10_window_function
[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/window-function-calls#def_window_spec
[db2]: https://www.ibm.com/docs/en/db2/11.5?topic=expressions-olap-specification
[hive]: https://cwiki.apache.org/confluence/display/Hive/LanguageManual+Select
[mariadb]: https://mariadb.com/kb/en/window-functions-overview/
[mysql]: https://dev.mysql.com/doc/refman/8.0/en/select.html
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/select-syntax.html#window-clause
[pl/sql]: https://docs.oracle.com/cd/E11882_01/server.112/e41084/functions004.htm#SQLRF06174
[postgresql]: https://www.postgresql.org/docs/current/sql-select.html
[redshift]: https://docs.aws.amazon.com/redshift/latest/dg/r_Window_function_synopsis.html
[singlestoredb]: https://docs.singlestore.com/managed-service/en/developer-resources/functional-extensions/working-with-window-functions.html
[snowflake]: https://docs.snowflake.com/en/sql-reference/functions-analytic.html
[spark]: https://spark.apache.org/docs/latest/sql-ref-syntax-qry-select.html
[sqlite]: https://www.sqlite.org/lang_select.html
[transact-sql]: https://docs.microsoft.com/en-US/sql/t-sql/queries/select-window-transact-sql?view=sql-server-ver16&viewFallbackFrom=sql-server-ver15
[trino]: https://github.com/trinodb/trino/blob/c7b26825218d5d11e9469984977dee6856f362ff/core/trino-parser/src/main/antlr4/io/trino/sql/parser/SqlBase.g4#L696