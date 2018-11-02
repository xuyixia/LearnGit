# GitFlow

GF是一种基于分支的开发流程（或者说分支策略，或者说开发模式）。它给如何在项目中合理地运用分支使其提高开发效率提供了一种思想模式。  
GF开发流程的几个特征：  

1. 每个分支用分支名表示了当前分支所处的开发状态；
2. 流程中设置了专门的发布管理员，负责管理软件和发布release; 


GF在理解和实践上过于复杂，这直接导致开发过程中出错率较高。为了解决这个问题，建议使用辅助工具git-flow,它能有效保障流程的正确性。  

## git-flow

git-flow安装事项见[链接：git-flow](https://github.com/nvie/gitflow/wiki/Installation)，根据页面描述可知git已包含git-flow工具。  

````dos
C:\Windows\System32>git flow
usage: git flow <subcommand>

Available subcommands are:
   init      Initialize a new git repo with support for the branching model.
   feature   Manage your feature branches.
   bugfix    Manage your bugfix branches.
   release   Manage your release branches.
   hotfix    Manage your hotfix branches.
   support   Manage your support branches.
   version   Shows version information.
   config    Manage your git-flow configuration.
   log       Show log deviating from base branch.

Try 'git flow <subcommand> help' for details.
````

命令打印结果中的subcommands栏比参考资料中的要多几项，可见该工具一直在持续发展中。  
通过命令打印结果，