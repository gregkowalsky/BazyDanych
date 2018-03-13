# Transactions in MySQL

Experiment with transactions - try inserting several rows into a table in one MySQL shell, and at the same time try to query that table in another shell:

First shell:

```
START TRANSACTION;

INSERT INTO test_table values (0, NOW(), NOW());
INSERT INTO test_table values (0, '2018-03-01', '2018-09-01');

```

Second shell:

```
SELECT * FROM test_table;

Empty set (0.00 sec)

```

Go back to first shell and COMMIT the transaction:

```
COMMIT;
```

Now in the second shell:

```
SELECT * from test_table;

+----+----------------+----------------+
| id | date_of_rental | date_of_return |
+----+----------------+----------------+
|  1 | 2018-03-13     | 2018-03-13     |
|  2 | 2018-03-01     | 2018-09-01     |
+----+----------------+----------------+
2 rows in set (0.00 sec)


```

# Isolation levels

See what happens when we try to update a row in 2 connections, please specify the isolation level explicitly before beginning transaction:

```
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
START TRANSACTION;
UPDATE test_table SET date_of_return='2018-04-01' WHERE id=2;

```

Second connection:

```
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
START TRANSACTION;
SELECT * from test_table where id=2;
```

See what happens when you commit the first transaction;
Experiment with different isolation levels;

