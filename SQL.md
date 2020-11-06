## Pymysql

1. 安装mysql

2. 安装pymysql

   ```shell
   pip install PyMySQL
   ```

3. 一些基本操作

   ```python
   # 建立连接（不指定database）
   conn = pymysql.connect(host='localhost',user='root',password='psw',charset='utf8mb4')
   # 建立连接（指定database）
   conn = pymysql.connect(host='localhost',user='root',password='psw',charset='utf8mb4',database='db_name')
   
   # 建立游标
   cursor = conn.cursor()
   # 执行sql语句
   cursor.execute(sql)
   ```

## 常用 SQL

1. 常用数据类型

   可分为三类：数值、日期/时间和字符串(字符)类型

   |   类型   |  大小  |        范围         |
   | :------: | :----: | :-----------------: |
   |   INT    | 4 byte |        2^32         |
   |  BIGINT  | 8 byte |        2^64         |
   |  FLOAT   | 4 byte |                     |
   |  DOUBLE  | 8 byte |                     |
   |   DATE   |        |     YYYY-MM-DD      |
   |   TIME   |        |      HH:MM:SS       |
   | DATETIME |        | YYYY-MM-DD HH:MM:SS |

   

2. 常用语句

```sql
-- 创建db
create database if not exists dbname
-- 查询所有db
show databases
-- 选中db
use db_name
-- 查询数据库中所有表名
select table_name from information_schema.tables where table_schema='database_name' and table_type='base table';
-- 删除db
drop database db_name;

-- 创建表

```

