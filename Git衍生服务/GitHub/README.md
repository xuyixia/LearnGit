GitHub的一些小贴士
Git Pages，一个账号可以创建一个Organization page和一个User Page，但是同时只能其中的一个绑定自定义域名。
SSH keys,作为服务器GitHub可以绑定任意多的key。在账户设置下的SSH keys是全局的，要想为单个仓库添加key,需要到仓库的设置中添加。

GitHub是为开源git项目提供托管服务的供应商。
GitHub除了支持Git外，还实现了对SVN的支持。  
GitHub在团队使用上，最好是创建一个Organization，这样一来团队成员会使用一个相同的界面来进行工作。  
GitHub会在某一个时间点进行维护，因此要时刻注意维护时间（大概在国内白天这样的一个时间段内）。  
虽然GitHub线上版功能好用，但是其对私有仓库采取了收费模式，并且费用较高，因此也诞生了一批类似的线上Git托管服务提供商，如国内的coding。它们对私有仓库也收费，但是仅针对较大规模的项目，对一般小团队是免费的，另外它们的收费模式相比GitHub更加容易接受。  
GitHub提供的Git托管服务除了有线上版的，还有一个(GHE)GitHub Enterprise版本。后者的出现主要解决客户在使用GitHub线上版的两个顾虑：

1. 被视为企业财产的代码在公网上传输（无关是否加密）；
2. 对GitHub公司的内部管理不信任；

由于GHE采取了收费模式并且费用不菲，因此出现了一批开源的、与GHE功能类似（但偏弱）的Git托管软件，它们在一定程度上可以取代GHE，但是需要考虑学习成本。  



# GitHub的API
GitHub为了给予用户更加灵活的操作性，开放了一批API接口。我们可以利用这些API实现一些自动化的功能。

比如我一直想有一个这样的功能，直接通过命令行的形式在GitHub上创建仓库。
[参考案例](https://blog.csdn.net/chent86/article/details/78575998)


参考：
[《一篇文章搞定Github API 调用 (v3）》](https://segmentfault.com/a/1190000015144126?utm_source=tag-newest)
[《官方文档V4》](https://developer.github.com/v4/)