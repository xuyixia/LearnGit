Git在编码问题上未做限制，因此想要Git支持中文就需要一定的配置。

如果使用默认的BUSH,输入这条命令即可`git config --global core.quotepath false`，否则还该考虑是不是终端不支持中文。

也有的说用命令`git config --global gui.encoding utf-8`，但是我测试无效。

### 参考：
* [《mac下git中文乱码](https://www.cnblogs.com/ayseeing/p/4268655.html)
* [《Mac下 git 终端的utf-8 字符显示》](https://blog.csdn.net/mad2man/article/details/23267227)