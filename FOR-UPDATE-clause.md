Non-standard syntax. Supported by [Oracle][]:

```
FOR UPDATE
  [OF identifier {"," ... }]
  [NOWAIT | WAIT integer | SKIP LOCKED]
```

TODO: Research whether this syntax is also supported by some other SQL dialects besides Oracle.

[oracle]: https://docs.oracle.com/database/121/SQLRF/statements_10002.htm#i2126016