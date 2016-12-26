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













