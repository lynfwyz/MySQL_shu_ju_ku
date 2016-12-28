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

##### 第四课（内置函数）
**字符串函数**

`select concat(name,"age is",age) from users;`

`select insert('abcdefg',2,3,'hello);`

从位置2开始的三个字母替换为hello（位置从1开始计）

`select insert(name,3,2,'00') from users;`

name是users表的一个字段

`select * from users where upper(name)='AAA';`

`select left('abcd',2),right('abcd',2);`

最左边的两个字符和最右边的两个字符，如果个数为null，那么返回为null

lpad(str,n,pad)和rpad(str,n,pad)-用字符串pad对str进行左边填充或者右边填充，直到str变为n个字符为止

trim(str):去掉str两边的空格

ltrim(str):去掉str左边的空格

rtrim(str):去掉str右边的空格

\G表示将结果立起来展示

replace(str,a,b)：将str中的字符串a替换为字符串b

strcmp(str1,str2):字符串比较函数，str1小于str2返回-1,相等返回0，大于返回1

substring(str,a,b):取子字符串函数，取str中位置a开始的b个字符

**数值函数**

abs(x):x的绝对值

ceil(x):大于x的最小整数

floor(x):小于x的最大整数

mod(x,y):x/y的模

rand():0-1之间的随机数

round(x,y):x四舍五入后有y位小数的值

truncate(x,y):x截断剩余y位小数的值

** 日期函数 **

curdate():当前日期

curtime():当前时间

now():当前日期和时间

unix_timestamp(now()):返回当前时刻时间戳

from_unixtime(时间戳)：由时间戳返回日期和时间

week(now()):返回年的第几周

year(now()):返回年

hour(curtime()),minute(curtime()):返回小时和分

monthname(now()):返回月的名字

** 流程控制函数 **

if(value,t,f)

`select id,salary,if(value>3000,'high','low') from salary;`如果工资大于3000显示为high,否则显示为low

`select id,salary ifnull(salary,0.0) from salary;`

ifnull(value1,value2):如果value1不为空返回value1,为空返回value2

case when...then...else...end

`select case when salary>=3000 then 'high' else 'low' end from salary;`

** 其他函数 **

database()

version()

user():当前登录的用户

inet_aton('ip'):ip地址表示为数字式的网络字节

inet_ntoa(上面的结果):将网络字节转换为字符串的ip

\s：显示数据库当前状态

password(str):将str加密的字符串，应用于数据库本身的用户密码加密

md5(str)：加密，应用于程序中的加密

























