### 启停
- 启动数据库实例
 ```db2start```

- 停止数据库实例
```db2stop```

- 打开命令行窗口
进入`BIN`目录，运行`db2cmd`，在运行`db2`

### 操作数据库命令

- 创建数据库
 `create db [db_name]`

- 连接到数据库
 `connect to [db_name] user [username] using [password]`

- 断开连接
 `connect reset`

- 列出所有数据库
 `list db directory`

- 列出所有激活的数据库
 `list active databases`

- 删除数据库
 `drop database [db_name]`

- 列出所有数据库配置 
 `get db cfg`


### 操作表命令
- 列出所有用户表
 `list tables`

- 列出所有系统表
` list tables for system`

- 列出所有表
 `list tables for all`

- 列出用户表
``list tables for user`

- 列出特定用户表
  `list tables for schema [username]`

- 创建一个与数据库中某个表(t2)结构相同的新表(t1) 
  `create table t1 like t2`

- 将一个表t1的数据导入到另一个表t2 
 `insert into t1 select * from t2`

- 显示表结构
 `DESCRIBE TABLE table_name`

- 修改列
 `ALTER TABLE [table_name] ALTER C [colum_name] set data type varchar(24) `

- 删除表
 `DROP TABLE table_name`

- 添加主键
 `ALTER TABLE {table_name} ADD PRIMARY KEY({column_name})`

- 添加外键
 `ALTER TABLE {table_name} ADD CONSTRAINT {constraint_name} FOREIGN KEY ({column_name}) REFERENCES {referenced_column_name}`

### 分页

 `SELECT * FROM (SELECT ROWNUMBER() OVER(ORDER BY col_name) AS ROWNUMBER, t.* FROM tb_name AS t ORDER BY {col_name}) WHERE ROWNUMBER BETWEEN 1 AND 10`
