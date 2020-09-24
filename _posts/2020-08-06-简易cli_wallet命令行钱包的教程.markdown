---
layout: post
title: 简易cli_wallet命令行钱包的教程
author: "binggo"
categories: 
tags: 
---


可参考的：    
<https://www.jianshu.com/p/aac211014c79> 
 
---

Windows系统:
   
从下面下载windows代码包：   
<https://github.com/bitshares/bitshares-core/releases/tag/5.0.0>    
bitshares-core-5.0.0-win64-bin.zip

下载解压，打开文件夹：
打开本地文件夹下的命令行窗口（请自行百度）...   
Win10系统下本地文件夹工具栏会有：“文件”-“打开 Windows PowerShell（R)"-"打开 Windows PowerShell"

命令行窗口输入：
```
  ./cli_wallet -s wss://ws.gdex.top
```
wss://ws.gdex.top可以替换成其它可连接节点，如果是测试网的话，请替换成测试网节点。

按[ENTER]后，出现：
``` 
  new >>>
```
输入：
 ```
  new >>>set_password 新钱包密码
 ```
出现：
``` 
  null
  locked >>>
 ```
输入：
 ```
  locked >>>unlock 新设置的钱包密码
 ```
出现:
 ```
  null
  unlocked >>>
 ```
下面这个命令是为了能够导入你的账户， import_key <账户名> <私钥>：
 ```
  unlocked >>>import_key <ACCOUNT_NAME> <WIF_KEY>
 ```
如果出现true，则代表导入成功：
 ```
  true
  unlocked >>>
 ```
之后就可以各种骚操作。


注意：最后退出的时候，要输入“lock”锁定账户，因为不会自动锁定:
```
  unlocked >>> lock
  
```

**按组合键Ctrl+C退出


下次再登录的时候：

第一步，进入bitshares core文件夹，打开命令行窗口，输入，后面这个节点如果连接不上的的话，找可用的节点替换：
```
./cli_wallet -s wss://ws.gdex.top

``` 
第二步：

      locked >>> unlock 密码
      unlocked >>>



-----


Linux操作系统 :

从下面下载Linux代码包：   
<https://github.com/bitshares/bitshares-core/releases/tag/5.0.0>  
bitshares-core-5.0.0-linux-amd64-bin.tar.bz2
###

打开bitshares-core文件夹，在此文件夹打开命令行窗口输入下列命令后按确认键

```
./cli_wallet -s wss://ws.gdex.top
```

如果第一次没有出现下面这个new，就再输入一下上面的命令:

    new >>> 

*输入set_password按确认键：

    new >>> set_password

出现下面这个，在后面设置一个密码，注意: 输入的时候密码是不显示的：

    Enter password:新钱包密码
      
 出现：
 ```
 locked >>>
 ```
 输入：
 ```
 locked >>> unlock
 ```
 出现:
 ```
 Enter password:输入新设置的密码
 ```
 出现,代表钱包解锁：
 ```
 unlocked >>>
 ```

下面这个命令是为了能够导入你的账户， import_key <账户名> <私钥>


    unlocked >>> import_key <ACCOUNT_NAME> <WIF_KEY>

之后就可以各种骚操作。

注意：最后退出的时候，要输入“lock”锁定账户，因为不会自动锁定：

    unlocked >>> lock

**按组合键Ctrl+C退出


下次再登录的时候：

第一步，进入bitshares core文件夹，打开终端，输入，后面这个节点如果连接不上的的话，找可用的节点替换：
```
./cli_wallet -s wss://ws.gdex.top

``` 
第二步：

      locked >>> unlock [ENTER]
      Enter password:
      unlocked >>>
     
之后就可以各种骚操作。

注意：最后退出的时候，要输入“lock”锁定账户，因为不会自动锁定：

    unlocked >>> lock    
    
    
    

更多信息参看:  [Wiki](https://github.com/bitshares/bitshares-core/wiki/CLI-Wallet-Cookbook).

