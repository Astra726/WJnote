## Table operation
```
# Delete table
DROP TABLE IF EXISTS TableName

# Change table name
ALTER TABLE TableName_Old RENAME TO TableName_New

# 获取总行数
SELECT COUNT(*) FROM TableName
total_rows = cursor.fetchone()[0]
```
## Column operation

## Character operation
执行 UPDATE 语句，以 ',' 为分隔符选择 ColumnName 列中固定第二部分：
```
UPDATE TableName
SET ColumnName = substr(ColumnName, instr(ColumnName, ',') + 1)
```

## Deduplication
GROUP BY 中要包括所有需要保持唯一的列
```
cursor.execute("""
    DELETE FROM TableName
    WHERE ROWID NOT IN (
        SELECT MIN(ROWID)
        FROM TableName
        GROUP BY ColumnName1, ColumnName2)
""")
```

>示例

>|ROWID|MEASURE_NAME|MEASURE_GROUP|DESCRIPTION|ACTUAL|
>|-----|------------|-------------|-----------|------|
>|1|Test1|Group1|Desc1|10|
>|2|Test1|Group1|Desc2|15|
>|3|Test2|Group2|Desc3|20|

> 如果 GROUP BY 是 MEASURE_NAME, MEASURE_GROUP， ROWID 1 和 ROWID 2 会被视为同一组，因为 MEASURE_NAME 和 MEASURE_GROUP 相同。

> 由于 MIN(ROWID) 的使用，ROWID 1 会被保留，ROWID 2 会被删除，即便 DESCRIPTION 和 ACTUAL 不同。

