
## Copy data into redshift from S3

| Node type | # of Nodes | # of Files | Total Filesize | Total Rownum | DIST Key | Sort key | Elapsed Time |
| --------- | ---------- | ---------- | -------------- | ------------ | -------- | -------- | ------------ |
|Inst1   | Data Size 10G          | 1          | 1.8G           | 9937969      | N/A      | N/A      | 44 sec       |
| dc2.large | 8          | 2          | 1.8G           | 9937969      | N/A      | N/A      | 22 sec       |
| dc2.large | 8          | 4          | 1.8G           | 9937969      | N/A      | N/A      | 12 sec       |
| dc2.large | 8          | 12         | 1.8G           | 9937969      | N/A      | N/A      | 9 sec        |
