SSH协议是Git使用到的传输协议之一，SSH协议的关键元素就是key。

SSH需要单独生成key,生成SSH key的方法`$ ssh-keygen -t rsa -C "youremail@example.com"`。在这里抛出一个疑问，如果有人冒充别人填入他的邮箱生成SSH key,在GitHub上会不会冲突？SSH key的位置在用户主目录下，存在隐藏文件夹.ssh中。id_rsa和id_rsa.pub,顾名思义一个私钥一个公钥。