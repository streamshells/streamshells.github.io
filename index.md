## 简介

一种用于数据编排的语言

* 从左至右，不回退阅读，比如：((String) name).length 改为 name.string.length
* 减少嵌套
* 强类型推导

## 示例

item.getItem.ss

```
map int 
map shop.getShop
flatmap items
filter price > 1000
map name += " sale"
```

http://xxx/xxx.item.getItem.ss/1

### 注释

```
 * # 
 * #* *# 多行注释
 * #!
```

### 类型

 * bool (true, false)
 * int8, int16, int32, int64
   * byte = int8
   * int = int64
 * float32, float64
   * float = float128
 * complex64, complex128
   * complex = complex128
 * char (utf8, bigendian)
 * string (utf8, bigendian)
 * struct
 * stream
 * verctor, matrix, tensor

### 字面量

#### 字符

 * 字符串："abc"
 * 单字符：'a'
 * 多行字符：`abc \n def`

#### 字符串表达式

```
"Hello $item.name"
"Price ${item.price * 0.8}"
```

#### 布尔

 * true
 * false

#### 数字

 * 整型：123
 * 十六进制整型：0xff
 * 八进制整型：077
 * 二进制整型：0b1010
 * 浮点型：123.45
 * 浮点型科学计数法：6.022E23

#### 时间

 * 毫秒：1ms
 * 秒：1s
 * 分：1m
 * 小时：1h
 * 天：1d
 * 月：1m
 * 年：1y
 * 组合：1h15ms20s

#### 元组

```
("abc" 123)
```

#### 数组
```
[1 2 3]
```

#### 对象
```
{
a 1 
b 2 
c 3
}
```

### 函数

输入输入皆为流

#### 

#### 张量

 * 矩阵相乘
 * 矩阵卷积 eye(5) *+ center(3)
   * ```
        [[1 0 0 0 0]
         [0 1 0 0 0]
         [0 0 1 0 0]
         [0 0 0 1 0]
         [0 0 0 0 1]]
             x
        [[0 0 0]
         [0 1 0]
         [0 0 0]]
             =
     ```

##### 创建流：
 * from 从其它源读取流
 * just 直接从字面量生成数据流
 * empty 空数据流
 * rang 生成一个区间数据流
 * interval 按时间间隔产生数据流

##### 处理流：
 * map 值映射转换
 * flatMap 将子流展开
 * filter 按条件过滤流中的数据
 * filterNot 按条件取反过滤流中的数据
 * peek 不改变流中的数据额外处理
 
##### 流合并：
 * merge 合并为先到先处理流
 * concat 前后串联流
 * zip 合并成二元组流

##### 终结流：
 * forEach 处理每个元素
 * collect 收集每个元素

## 内存设计

### 编译执行 ARC

### 解译执行 GC

## 基础库

### 网络库

### 算法库

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
