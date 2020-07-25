# 数据库复习（三、关系数据库标准语言SQL）

## 1. SQL语言概述

#### 一、SQL语言特点

- **综合统一**

- **高度非过程化**
- **面向集合的操作方式**
- **同一种语法结构，多种使用方式**
- **SQL语言简洁，易学易用**

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710124452646.png" alt="image-20200710124452646" style="zoom:67%;" />

#### 二、数据定义

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710124649585.png" alt="image-20200710124649585" style="zoom:67%;" />

## 2. 基本表的修改和删除

#### 一、建立基本表

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710125155780.png" alt="image-20200710125155780" style="zoom:67%;" />

#### 二、修改基本表

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710125247088.png" alt="image-20200710125247088" style="zoom:67%;" />

## 3. 数据查询

#### 一、数据查询语句

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710125423694.png" alt="image-20200710125423694" style="zoom:67%;" />

#### 二、基本查询

**DISTINCT：**消除重复元组

**查询条件：**

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710184443111.png" alt="image-20200710184443111" style="zoom:67%;" />

**ORDER BY子句：**升序ASC，降序DESC

#### 三、聚集函数

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710184642140.png" alt="image-20200710184642140" style="zoom:67%;" />

聚集函数只能用于SELECT子句和HAVING子句中。

#### 四、GROUP子句

将查询结果集合进行分组。

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710184940033.png" alt="image-20200710184940033" style="zoom:67%;" />

#### 五、HAVING子句

对于分组后的结果集合使用限定条件选择部分分组。

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200710185127290.png" alt="image-20200710185127290" style="zoom: 50%;" />

#### 六、多表连接查询

连接操作的执行方法：

- 嵌套循环法
- 排序合并法
- 索引连接法
- 哈希法

**自身连接**

**外连接**

#### 七、嵌套查询

将一个查询块嵌套在另一个查询块的**WHERE****子句或**HAVING**子句

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711084332199.png" alt="image-20200711084332199" style="zoom:67%;" />

**ANY(R)：**R中的任意一个值

**ALL(R)：**R中的所有值

**EXIST：**用于判断一个集合是否为空，EXIST(R)，R为非空则返回真。

**NOT EXIST：**语义与EXIST函数相反的逻辑函数

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711092512136.png" alt="image-20200711092512136" style="zoom:67%;" />

## 4. 数据更新

#### 一、插入数据

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711093107807.png" alt="image-20200711093107807" style="zoom:67%;" />

#### 二、修改数据

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711093346386.png" alt="image-20200711093346386" style="zoom:67%;" />

#### 三、删除数据

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711093425250.png" alt="image-20200711093425250" style="zoom:67%;" />

## 5. 视图

#### 一、建立视图

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711093907144.png" alt="image-20200711093907144" style="zoom:67%;" />

- 多表视图
- 基于视图的视图
- 带表达式的视图
- 分组视图

#### 二、删除视图

<img src="https://cdn.jsdelivr.net/gh/1090ym/image/img/image-20200711094047715.png" alt="image-20200711094047715" style="zoom:67%;" />

使用CASCADE级联删除语句，可以把该视图和由它导出的所有视图一起删除。

#### 三、查询视图

与查询基本表相同

#### 四、更新视图

视图不实际存储数据，因此，对视图的更新最终要转换为对基本表的更新。


**更新视图的限制：**一些视图是不可更新的，因为对这些视图的更新不能唯一地有意义地转换成对应基本表地更新。