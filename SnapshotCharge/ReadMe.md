**Testing Condition**

| Node type | Initilal Data | Data Change | Manual Snapshot |
| --------- | ------------- | ----------- | --------------- |
| Inst1     | 10G           | N           | N               |
| Inst2     | 10G           | N           | Y               |
| Inst3     | 10G           | Y           | N               |
| Inst4     | 10G           | Y           | Y               |

mysql> SELECT table_schema "DB Name",
-> ROUND(SUM(data_length + index_length) / 1024 / 1024, 1) "DB Size in MB"
-> FROM information_schema.tables
-> GROUP BY table_schema;
+--------------------+---------------+
| DB Name | DB Size in MB |
+--------------------+---------------+
| information_schema | 0.2 |
| mysql | 9.0 |
| performance_schema | 0.0 |
| sys | 0.0 |
| sysbench | 1084.4 |
| sysbench1 | 1116.9 |
| sysbench2 | 1116.9 |
| sysbench3 | 1063.9 |
| sysbench4 | 1116.9 |
| sysbench5 | 1072.9 |
| sysbench6 | 1116.9 |
| sysbench7 | 1067.9 |
| sysbench8 | 1116.9 |
| sysbench9 | 1065.9 |
+--------------------+---------------+
14 rows in set (0.09 sec)

**RDS Aurora MYSQL dump import with ERROR 1227**

Need to remove

For a logical backup taken via mysqldump, ensure that the "SET @@GLOBAL" and the "SET @@SESSION" lines are removed from the dump file [1] [2]. After removing these lines you may then proceed to import the dump file to the target RDS instance.
[1] - https://bugs.mysql.com/bug.php?id=77845
[2] - http://www.ducea.com/2007/07/25/dumping-mysql-stored-procedures-functions-and-triggers/
