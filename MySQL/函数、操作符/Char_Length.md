# [函数、操作符](https://github.com/Summer-Felix/Database/blob/master/MySQL/函数、操作符.md) #

## [CHAR_LENGTH()](https://dev.mysql.com/doc/refman/5.7/en/string-functions.html#function_char-length) ##



不管汉字还是数字或者是字母都算是一个字符

返回字符串的长度 str，以字符测量。一个多字节字符算作一个字符。这意味着，对于含有5个2字节字符，字符串 LENGTH()返回 10，而 CHAR_LENGTH()返回 5。