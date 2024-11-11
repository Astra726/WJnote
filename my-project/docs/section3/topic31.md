## python 连接 SQLite
创建一个查询函数
```
import sqlite3

# 创建一个查询函数
def query_database(query):
    # 创建 SQLite 连接
    conn = sqlite3.connect(db_file_path)
    cursor = conn.cursor()

    # 执行 SQL 查询
    cursor.execute(query)

    # 提交更改并关闭连接
    conn.commit()
    conn.close()
```
## Print result
### cursor.fetchall() 
返回列表，其中每一行都是一个元组。结果存在内存中。
```
# 获取所有结果，
result = cursor.fetchall()

# 获取指定第 n+1 行
result = cursor.fetchall()[n]
```
### cursor.fetchone() 
返回查询结果的第一行，如果存在多行，它只会返回第一行的内容。
```
# 指定输出第一行的第 n+1 个元素
result = cursor.fetchone()[n]
```
但是 .fetchone() 每次调用都会取出并移动到下一行，所以可以实现类似 .fetchall()[n] 的功能：
```
# 获取第 3 行
result = cursor.fetchone()
result = cursor.fetchone()
result = cursor.fetchone()

# 获取指定第 n+1 行
N = n
result = None
for _ in range(N):
    result = cursor.fetchone()
print(result)
```
## VSCode Extension
Install the **SQLite** extension and visualize the database directly from code editor.

Installation:

* Open VSCode.
* Go to the Extensions view ( Ctrl+Shift+X ).
* Search for **SQLite** and install the extension.

Steps:

* Open the command palette ( Ctrl+Shift+P ) and search for **"SQLite: Open Database"**.
* Select **.db** file, and the tables will appear in a side panel.

## Generate ER relationship
使用 eralchemy 来生成数据库的 ER 关系，并输出为 .gv 文件，之后上传到在线工具转换为图像格式。

* 安装 ERAlchemy: 
`pip install eralchemy`

* 生成 .gv 文件: 使用 eralchemy 生成 .gv 文件:
`eralchemy -i SQLitePath -o erd.gv`

    * PathtoSQLite: SQLite 数据库的路径。
    * erd.gv 是生成的输出文件。

* 上传 .gv 文件，或者直接复制文件内容到工具中即可查看数据库的 ER 关系图。
* 在线工具有 **Graphviz Online** 和 **WebGraphviz**。
