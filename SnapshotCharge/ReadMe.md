**Testing Condition**

| Node type | Initilal Data | Data Change | Manual Snapshot |
| --------- | ------------- | ----------- | --------------- |
| Inst1     | 10G           | N           | N               |
| Inst2     | 10G           | N           | Y               |
| Inst3     | 10G           | Y           | N               |
| Inst4     | 10G           | Y           | Y               |

**RDS Aurora MYSQL dump import with ERROR 1227**

Need to remove

For a logical backup taken via mysqldump, ensure that the "SET @@GLOBAL" and the "SET @@SESSION" lines are removed from the dump file [1] [2]. After removing these lines you may then proceed to import the dump file to the target RDS instance.
[1] - https://bugs.mysql.com/bug.php?id=77845
[2] - http://www.ducea.com/2007/07/25/dumping-mysql-stored-procedures-functions-and-triggers/
