版本提交
git commit -m 'message'

版本回退
git reset HEAD 


删除版本库中的文件

前提是出现了版本不一的情况，也就是版本库中的文件还在，工作区的没了，并且只能是这一种情况。
git rm <file> ---->git commit
git add 和git rm都是对缓存区的操作，删除也是改变的一种，只是要将这种改变加到暂存区需要用特殊的命令rm。