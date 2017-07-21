1. 正则筛选一个字符串是否为IP地址：
    ``` python
    # 设输入一个字符串为ip_string
    import re
    pattern = re.compile(r'((?:25[0-5]|2[0-4]\d|1\d{2}|[1-9]?\d)\.){3}(?:25[0-5]|2[0-4]\d|1\d{2}|[1-9]?\d)$')
    result = re.match(pattern, ip_string)
    ```
    复习内容：re.match的使用；(...)的使用，?:的意义；正则无判断大于小于的操作符。

2. 使用python操作linux目录和文件

    [python的os库操作文档](https://docs.python.org/3/library/os.html)，[Python os模块常用部分功能](http://developer.51cto.com/art/201003/186045.htm)
