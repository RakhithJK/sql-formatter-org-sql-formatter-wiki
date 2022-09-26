Some SQL dialects have special syntax for creating and manipulating Array and Map types.

## Literals

Array literals `[1, "two", 3]`. Supported by:

- [BigQuery][bigquery-literals].
- [N1QL][n1ql-literals].

Array literals `ARRAY[1, 2, 3]`. Supported by:

- [BigQuery][bigquery-literals].
- [PostgreSQL][postgres-literals].
- [Trino][]

Map literals in JSON style `{"foo": 1, "bar": "John"}`. Supported by:

- [N1QL][n1ql-literals].

## Accessors

Array and Map access using square brackets like `arr[1]` and `map['key']`.

Supported by:

- [Hive][]
- [Spark][]
- [N1QL][]
- [PostgreSQL][]
- [Snowflake][]<sup>1</sup>
- [Trino][]

Array subscript operator `arr[OFFSET(5)]`. Supported by:

- [BigQuery][]

Notes:

1. Snowflake also supports a dot syntax to access the values of keys. The first key has to be extracted with `:` after that, `.` can be used to access deeper nested values. 

[bigquery]: https://cloud.google.com/bigquery/docs/reference/standard-sql/operators#array_subscript_operator
[hive]: https://cwiki.apache.org/confluence/display/Hive/LanguageManual+UDF#LanguageManualUDF-OperatorsonComplexTypes
[spark]: https://stackoverflow.com/questions/34916038/sparksql-sql-syntax-for-nth-item-in-array
[n1ql-literals]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/datatypes.html#arrays
[n1ql]: https://docs.couchbase.com/server/current/n1ql/n1ql-language-reference/nestedops.html#field-selection
[postgresql]: https://www.postgresql.org/docs/current/arrays.html#ARRAYS-ACCESSING
[snowflake]: https://docs.snowflake.com/en/user-guide/querying-semistructured.html#traversing-semi-structured-data
[trino]: https://trino.io/docs/current/functions/array.html
[bigquery-literals]: https://cloud.google.com/bigquery/docs/reference/standard-sql/lexical#array_literals
[postgres-literals]: https://www.postgresql.org/docs/current/arrays.html
