# [LENGTH()](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_length) #



是计算字段的长度一个汉字是算三个字符,一个数字或字母算一个字符

返回字符串的长度 str，以字节为单位来测量。一个多字节字符算作多字节。这意味着，对于含有5个2字节字符，字符串 LENGTH()返回 10，而 CHAR_LENGTH()返回 5。

```
mysql> SELECT LENGTH('text');
        -> 4
```

> 注意 : 
> * 在 Length() 开放 GIS 空间功能被命名为 ST_Length() MySQL 中。