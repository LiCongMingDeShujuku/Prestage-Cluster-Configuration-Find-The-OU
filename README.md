![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# Prestage群集配置 - 查找OU
#### Prestage Cluster Configuration – Find The OU
**发布-日期: 2016年7月6日 (评论)**

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
任何时候当你在后Server 2012环境中设置故障转移群集配置时…你需要在Active Directory中预安排群集对象。Microsoft提供了一些关于使用此处的清单执行创建Failover Cluster的步骤的一些很好的文档：
https://technet.microsoft.com/en-us/library/dn505754(v=ws.11).aspx  
在这里可以找到的实际预处理过程：
https://technet.microsoft.com/en-us/library/dn466519(v=ws.11).aspx

不幸的是，在如何获取所需信息上，没有太多的捷径。比如，找查找OU的计算机所在的位置上。好消息是你可以使用PowerShell中的快速单行程GET-ADComputer来实现。使用标准2节点示例实现故障转移群集（Failover Cluster）：

#THIS WORKS
get-adcomputer MyClusterName
get-adcomputer Server01
get-adcomputer Server02
#THIS ALSO WORKS
“MyClusterName”, “Server01”, “Server02” | get-adcomputer



## English
Whenever you’re setting up a Failover Cluster Configuration in a post Server 2012 world… You’ll need to prestage the cluster objects in Active Directory. Microsoft offers some good documentation on the steps to carry out creating the Failover Cluster using the a checklist found here: 
https://technet.microsoft.com/en-us/library/dn505754(v=ws.11).aspx 
and also the actual prestaging process found here: 
https://technet.microsoft.com/en-us/library/dn466519(v=ws.11).aspx

Unfortunately; there aren’t a great deal of short cut tips on how to get some of the information you need. For example; finding the OU’s a Computer resides in. The good news is you can do this with a quick one-liner in powershell. Get-ADComputer.

Using a standard 2 Node Example for Failover Cluster implementation:

#THIS WORKS
get-adcomputer MyClusterName
get-adcomputer Server01
get-adcomputer Server02
#THIS ALSO WORKS
“MyClusterName”, “Server01”, “Server02” | get-adcomputer

![#](images/Prestage-Cluster-Configuration-Find-The-OU-01.png?raw=true "#")

Alternatively there is also a quick one-liner you can do in Command Prompt if you want to get the OU where the server resides and that’s the following
dsquery computer –samid MyServerName$
Notice the dollar sign $ at the end of the Server Name. This is required in the script. In the results you’ll see the OU’s where the Server resides.

或者，如果你想要获取服务器所在的OU，还有一种可以在Command Prompt中做的快速单行程，以下是查找中的计算机- samid MyServerName$。
注意服务器末尾的美元符号$。这在脚本中是必需的。 在结果中，你会看到服务器所在的OU。


![#](images/Prestage-Cluster-Configuration-Find-The-OU-02.png?raw=true "#")


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")


