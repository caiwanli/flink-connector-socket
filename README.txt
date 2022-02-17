这是一个flink-connector-socket Demo，能够实时读取Socket数据
元数据：
CREATE TABLE UserScores (name STRING, score INT)
WITH (
  'connector' = 'socket',
  'hostname' = 'localhost',
  'port' = '9000',
  'byte-delimiter' = '10',
  'format' = 'changelog-csv',
  'changelog-csv.column-delimiter' = ','
);

启动项目前，运行nc -lk 9000命令打开Socket端口监听
插入数据格式：
INSERT,Alice,12
INSERT,Bob|5
DELETE,Alice,12
INSERT,Alice,18












