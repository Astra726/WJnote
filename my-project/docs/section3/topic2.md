# SQLite Manager (VSCode Extension)
If you're already using Visual Studio Code, you can install the "SQLite" extension and visualize the database directly from your code editor.
##  Installation:
		1. Open VSCode.
		2. Go to the Extensions view (Ctrl+Shift+X).
		3. Search for **SQLite** and install the extension.
## Steps:
		1. Open the command palette (Ctrl+Shift+P) and search for "SQLite: Open Database".
		2. Select your .db file, and the tables will appear in a side panel.
		3. You can view table data, execute queries, and visualize relationships.

# 对我当前的数据库生成 er 关系，可以生成  .gv 我自己在线转换
 
你可以使用 eralchemy 工具来生成数据库的 ER 关系，并输出为 .gv 文件，之后你可以将该文件上传到在线工具转换为图像格式。

## 生成 .gv 文件的步骤：
安装 ERAlchemy: 确保你已经安装了 eralchemy，你可以使用以下命令来安装它：

bash
复制代码
pip install eralchemy
生成 ER 图 .gv 文件: 使用 eralchemy 生成 .gv 文件，具体命令如下：

`eralchemy -i sqlite:///account_book.db -o erd.gv`

这里 sqlite:///account_book.db 是你 SQLite 数据库的路径，erd.gv 是生成的输出文件。

## .gv 文件在线转换
生成 .gv 文件后，你可以将其上传到以下在线工具进行图像转换：

Graphviz Online
WebGraphviz
这些工具可以将 .gv 文件解析为可视化的 ER 图。

你只需要上传 .gv 文件，或者直接复制文件内容到工具中即可查看数据库的 ER 关系图。