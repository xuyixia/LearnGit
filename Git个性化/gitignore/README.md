使用Git大部分是用来协作开发，因此对一个开发项目来说，以下是需要ignore的：
1. 操作系统生成的文件
2. 编译后生成的中间文件或编译文件
3. 敏感信息的配置文件

.gitignore文件是可以被提交到版本库的，其内部指定的文件类型则不能。

# 如何编写gitignore文件？

github提供了配置文件选项清单，根据自身项目合理组合即可。
* 参考
    * [《A collection of useful .gitignore templates 》](https://github.com/xuyixia/gitignore)

# 如何检验gitignore文件？

`git check-ignore -v <target_file_name>`
