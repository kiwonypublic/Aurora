**Install mysql-shell**

```
[ec2-user@ip-172-31-5-23 ~]$ aws s3 cp s3://shared-kiwony/mysql-shell-8.0.23-1.el7.x86_64.rpm .
[ec2-user@ip-172-31-5-23 ~]$ sudo yum install mysql-shell-8.0.23-1.el7.x86_64.rpm -y
```

**Connect and importTable**

```
[ec2-user@ip-172-31-5-23 ~]$ mysqlsh
 MySQL  JS > \connect admin@aurora572072.cluster-cf89zyffo8dr.ap-northeast-2.rds.amazonaws.com:3306/test_db
  MySQL  aurora572072.cluster-cf89zyffo8dr.ap-northeast-2.rds.amazonaws.com:3306 ssl  test_db  JS > util.importTable("/home/ec2-user/dummy-2g.csv", {schema: "test_db", table: "test_load1", dialect: "csv-unix", threads: 32, bytesPerChunk:"64M", showProgress: true})
...
100% (2.15 GB / 2.15 GB), 19.90 MB/s
File '/home/ec2-user/dummy-2g.csv' (2.15 GB) was imported in 40.3862 sec at 53.17 MB/s
Total rows affected in test_db.test_load1: Records: 13411485  Deleted: 0  Skipped: 0  Warnings: 0
 MySQL  aurora572072.cluster-cf89zyffo8dr.ap-northeast-2.rds.amazonaws.com:3306 ssl  test_db  JS >

```
