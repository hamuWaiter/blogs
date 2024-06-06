## postgresql (11版本) 服务器启动流程

1、cd到bin目录

```
cd "D:\software\PostgreSQL\bin"
```

2、启动postgreSQL服务器

```
pg_ctl.exe start -D "D:\software\PostgreSQL\data"
```

```
// 查看服务启动状态
pg_ctl.exe status -D "D:\software\PostgreSQL\data"

// 结果如下表示启动成功：
pg_ctl: 正在运行服务器进程(PID: 12508)
C:/Program Files/PostgreSQL/11/bin/postgres.exe "-D" "C:/Program Files/PostgreSQL/11/data"
```

3、停止postgreSQL服务器

```
pg_ctl.exe stop -D "D:\software\PostgreSQL\data"
```
