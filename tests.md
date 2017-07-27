1. 正则筛选一个字符串是否为IP地址：
    ``` python
    # 设输入一个字符串为ip_string
    import re
    pattern = re.compile(r'((?:25[0-5]|2[0-4]\d|1\d{2}|[1-9]?\d)\.){3}(?:25[0-5]|2[0-4]\d|1\d{2}|[1-9]?\d)$')
    result = re.match(pattern, ip_string)
    ```
    复习内容：re.match的使用；(...)的使用，?:的意义；正则无判断大于小于的操作符。

1. 使用python操作linux目录和文件

    [python的os库操作文档](https://docs.python.org/3/library/os.html)，[Python os模块常用部分功能](http://developer.51cto.com/art/201003/186045.htm)

1. python中map，reduce，filter的用法

    [map、reduce和filter的文档](http://book.pythontips.com/en/latest/map_filter.html)

1. 使用python递归计算斐波那契数列
    ``` python
    def fibonacci(index):
        if index == 0:
            return 0
        elif index == 1:
            return 1
        else:
            return fibonacci(index - 1) + fibonacci(index - 1)
    ```

1. python表达二叉树并求两任意节点的最低公共父节点
    ``` python
    class Node(object):
    # 此处使用对象来表达节点
        def __init__(self, number):
            self.number = number # 默认unique
            self.left = None
            self.right = None
    
    def has_node(tree, node):
        # tree:当前在查找的节点, node:目标number
        if tree.number == node:
            return True
        left_found = right_found = False
        if tree.left:
            left_found = has_node(tree.left, node)
        if tree.right:
            right_found = has_node(tree.right, node)
        return left_found or right_found
        
    def find_nearest_common_node(node_root, node_1, node_2):
        left_found_1 = right_found_1 = left_found_2 = right_found_2 =False
        if node_root.left:
            left_found_1 = has_node(node_root.left, node_1)
            left_found_2 = has_node(node_root.left, node_2)
        if node_root.right:
            right_found_1 = has_node(node_root.left, node_1)
            right_found_2 = has_node(node_root.left, node_2)
        if left_found_1 and not right_found_1 and left_found_2 and not right_found_2:
            # 都在左边
            return find_nearest_common_node(node_root.left, node_1, node_2)
        elif not left_found_1 and right_found_1 and not left_found_2 and right_found_2:
            # 都在右边
            return find_nearest_common_node(node_root.left, node_1, node_2)
        else:
            # 左右各一
            return node_root.number
    ```
