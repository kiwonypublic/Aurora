```
kiwony@kiwonymac.com:/Users/kiwony/Downloads> aws rds   copy-db-cluster-parameter-group \
--source-db-cluster-parameter-group-identifier test02-cluster \
--target-db-cluster-parameter-group-identifier test03-cluster \
--target-db-cluster-parameter-group-description test03-cluster
kiwony@kiwonymac.com:/Users/kiwony/Downloads> aws rds   copy-db-cluster-parameter-group \
--source-db-cluster-parameter-group-identifier test02-cluster \
--target-db-cluster-parameter-group-identifier test04-cluster \
--target-db-cluster-parameter-group-description test04-cluster
kiwony@kiwonymac.com:/Users/kiwony/Downloads> aws rds   copy-db-cluster-parameter-group \
--source-db-cluster-parameter-group-identifier test02-cluster \
--target-db-cluster-parameter-group-identifier test05-cluster \
--target-db-cluster-parameter-group-description test05-cluster

```

```
kiwony@kiwonymac.com:/Users/kiwony/Downloads> aws rds   copy-db-parameter-group \
--source-db-parameter-group-identifier test02-db \
--target-db-parameter-group-identifier test03-db \
--target-db-parameter-group-description test03-db
kiwony@kiwonymac.com:/Users/kiwony/Downloads> aws rds   copy-db-parameter-group \
--source-db-parameter-group-identifier test02-db \
--target-db-parameter-group-identifier test04-db \
--target-db-parameter-group-description test04-db
kiwony@kiwonymac.com:/Users/kiwony/Downloads> aws rds   copy-db-parameter-group \
--source-db-parameter-group-identifier test02-db \
--target-db-parameter-group-identifier test05-db \
--target-db-parameter-group-description test05-db
```

```
aws rds create-db-cluster --db-cluster-identifier test02 \
--vpc-security-group-ids sg-00922c6998217e41e \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--master-username admin \
--master-user-password Octank#1234 \
--tags Key=Name,Value="test02" \
--engine-mode provisioned \
--db-cluster-parameter-group-name test02-cluster \
--availability-zones ap-northeast-2a

aws rds create-db-instance \
--db-instance-identifier inst02 \
--db-instance-class db.r5.4xlarge \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--db-cluster-identifier test02 \
--db-parameter-group-name test02-db \
--availability-zone ap-northeast-2a

aws rds create-db-cluster --db-cluster-identifier test03 \
--vpc-security-group-ids sg-00922c6998217e41e \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--master-username admin \
--master-user-password Octank#1234 \
--tags Key=Name,Value="test03" \
--engine-mode provisioned \
--db-cluster-parameter-group-name test03-cluster \
--availability-zones ap-northeast-2a

aws rds create-db-instance \
--db-instance-identifier inst03 \
--db-instance-class db.r5.4xlarge \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--db-cluster-identifier test03 \
--db-parameter-group-name test03-db \
--availability-zone ap-northeast-2a

aws rds create-db-cluster --db-cluster-identifier test04 \
--vpc-security-group-ids sg-00922c6998217e41e \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--master-username admin \
--master-user-password Octank#1234 \
--tags Key=Name,Value="test04" \
--engine-mode provisioned \
--db-cluster-parameter-group-name test04-cluster \
--availability-zones ap-northeast-2a

aws rds create-db-instance \
--db-instance-identifier inst04 \
--db-instance-class db.r5.4xlarge \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--db-cluster-identifier test04 \
--db-parameter-group-name test04-db \
--availability-zone ap-northeast-2a

aws rds create-db-cluster --db-cluster-identifier test05 \
--vpc-security-group-ids sg-00922c6998217e41e \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--master-username admin \
--master-user-password Octank#1234 \
--tags Key=Name,Value="test05" \
--engine-mode provisioned \
--db-cluster-parameter-group-name test05-cluster \
--availability-zones ap-northeast-2a

aws rds create-db-instance \
--db-instance-identifier inst05 \
--db-instance-class db.r5.4xlarge \
--engine aurora-mysql \
--engine-version "5.7.mysql_aurora.2.09.0" \
--db-cluster-identifier test05 \
--db-parameter-group-name test05-db \
--availability-zone ap-northeast-2a

```
