## Pymysql

1. 安装mysql；

   启动、关闭mysql服务

   ```
   net start mysql
   net stop mysql
   ```

   

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
   sql = "SHOW TABLES;"
   cursor.execute(sql)
   # 输出sql执行结果
   cursor.fetchall()
   ```

## 常用 SQL

1. 常用数据类型

   可分为三类：数值、日期/时间和字符串(字符)类型

   |   类型   |     大小      |        范围         |
   | :------: | :-----------: | :-----------------: |
   |   INT    |    4 byte     |        2^32         |
   |  BIGINT  |    8 byte     |        2^64         |
   |  FLOAT   |    4 byte     |                     |
   |  DOUBLE  |    8 byte     |                     |
   |   DATE   |    3 byte     |     YYYY-MM-DD      |
   |   TIME   |    3 byte     |      HH:MM:SS       |
   | DATETIME |    8 byte     | YYYY-MM-DD HH:MM:SS |
   |   CHAR   |  0-255 bytes  |                     |
   | VARCHAR  | 0-65535 bytes |                     |

   

2. 常用语句

```sql
-- 创建db
create database if not exists dbname
-- 查询所有db
show databases
-- 选中db
use db_name
-- 查询数据库中所有表名
show tables;
-- 删除db
drop database db_name;

-- 创建表
CREATE TABLE if not exists my_music(
music_id INT NOT NULL AUTO_INCREMENT,
music_name VARCHAR(100) NOT NULL,
music_singer VARCHAR(40) NOT NULL,
music_path VARCHAR(100) NOT NULL,
submission_date DATE,
PRIMARY KEY ( music_id )
)ENGINE=InnoDB DEFAULT CHARSET=utf8;
-- 查看表
desc tb_name;
-- 删除表
drop table tb_name;

-- 插入数据
INSERT INTO runoob_tbl
(music_name, music_singer, music_path, submission_date)
VALUES
("song", "singer", "this path", '2020-11-09');
```

