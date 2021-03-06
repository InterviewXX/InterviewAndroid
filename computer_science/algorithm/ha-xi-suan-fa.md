# 哈希算法

### 什么是哈希算法？

将任意长度的二进制数据映射为固定长度的二进制串。映射的方法就是哈希算法 ，生成的二进制串叫做哈希值。

### 需要满足的条件

* 从哈希值不能反向推导出原始数据
* 输入数据改动很小，输出的哈希值也会变化很大
* 对于不同的数据，哈希冲突的概率很小
* 执行效率高，针对较长的数据也能很快计算哈希值

### 常见的哈希算法

[MD5](https://zh.wikipedia.org/wiki/MD5) SHA256

###  为什么哈希冲突不可避免？

鸽巢原理（也叫抽屉原理）。这个原理本身很简单，它是说，如果有 10 个鸽巢，有 11 只鸽子，那肯定有 1 个鸽巢中的鸽子数量多于 1 个，换句话说就是，肯定有 2 只鸽子在 1 个鸽巢内。

哈希算法计算的哈希值位数是固定的，但计算的原数据却无穷无尽，因此可能存在冲突。

### 哈希算法的应用

#### 安全加密

对用户密码\(加一段salt\)做哈希后再存储

#### 唯一标识

对文件的数据进行哈希，得到文件的唯一标识，用于确定文件是否存在、内容是否相同。

#### 数据校验

确认下载的文件没有被篡改。

#### 哈希函数

用作哈希表的哈希函数，对哈希冲突要求不严格，但要求速度快、哈希值分布均匀。

#### 负载均衡

对用户的ip、会话id做哈希，再对机器数量取模，将请求映射到不同的机器，并且保证同一用户的后续请求都在同一机器上处理。

#### 数据分片

针对海量数据问题，对数据计算哈希值然后映射到不同的机器上进行处理。

#### 分布式存储

对数据计算哈希值，分配到不同的机器上，使用一致性哈希算法处理机器增加问题。



> [数据结构与算法之美：21、22](https://time.geekbang.org/column/article/65312)
>
>  [什么是一致性Hash算法？](https://zhuanlan.zhihu.com/p/34985026)

