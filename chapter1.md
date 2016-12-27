# 命令行命令
`mysql -u root -p`  登录数据库

#### 第三课(到21分钟）
`select * from products where price < 100;`检索价钱小于100的产品;

`select * from products where price < 100 and price > 50;`

`select * from products where price < 100 && price > 50;`

`select * from products where id != 10;`

`select * from products where id <> 10;`

查空值不能用等号，应该用is

`select * from products where desn is null;`

`select * from products where desn is not null;`

或者使用<=>,即可以用于空值比较

`select * from products where desn <=> null;`

like查询：_代表任意一个字符；%代表任意多个字符（包含0个字符）.下面是查询字段name以s作为结尾的

`select * from products where name like '%s';`

name中包含java的,不包含java的

`select * from products where name like '%java%';`

`select * from products where name not like '%java%';`

##### 多表查询 














