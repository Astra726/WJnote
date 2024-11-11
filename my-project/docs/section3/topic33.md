

### 日期格式清洗函数
确保日期是标准的 YYYY-MM-DD 格式。

```
def clean_date(date_str):
    # 将日期分割成日期和时间部分
    date_part, time_part = date_str.split()

    # 检查日期分隔符并替换为标准格式的 '-'
    date_part = date_part.replace('/', '-')

    # 将日期部分转为标准格式 YYYY-MM-DD
    year, month, day = date_part.split('-')
    month = month.zfill(2)  # 补齐月的前导零
    day = day.zfill(2)      # 补齐日的前导零

    # 拼接回标准日期格式
    formatted_date = f"{year}-{month}-{day} {time_part}"

    return formatted_date
```