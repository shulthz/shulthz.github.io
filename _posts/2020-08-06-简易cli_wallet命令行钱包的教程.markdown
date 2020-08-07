---
layout: post
title: 简易cli_wallet命令行钱包的教程
author: "binggo"
categories: [Bitshares]
tags: [Bitshare]
---


可参考的：    
(https://www.jianshu.com/p/aac211014c79) 
 
这个只能看看，不能当真，因为是其它DPOS区块链的：  
(https://cn-dev.cocosbcx.io/docs/22-cli_wallet)    

Windows系统十有八九的会编译失败，所以只讲Linux操作系统  

下载linuxmint：   
(https://www.linuxmint.com/edition.php?id=281)     
(https://mirrors.bfsu.edu.cn/linuxmint-cd/stable/20/linuxmint-20-cinnamon-64bit.iso)  

下载Oracle VM VirtualBox：  
(https://www.virtualbox.org/)

怎么在window上面用虚拟机VirtualBox安装linuxmint，网上一搜就很多教程：  
(https://www.cnblogs.com/zhangjiuding/p/7581993.html)


开始
---------------
环境安装说明及附加文件如下：  
[Wiki](https://github.com/bitshares/bitshares-core/wiki).

### 构建


**构建依赖项**

    sudo apt-get update
    sudo apt-get install autoconf cmake make automake libtool git libboost-all-dev libssl-dev g++ libcurl4-openssl-dev doxygen

**构建脚本:**

    git clone https://github.com/bitshares/bitshares-core.git
    cd bitshares-core
    git checkout master # may substitute "master" with current release tag
    git submodule update --init --recursive
    mkdir build
    cd build
    cmake -DCMAKE_BUILD_TYPE=Release ..
    make


* BitShares 需要 [Boost](http://www.boost.org/) libraries to build, 版本支持 `1.58` to `1.69`.  
新版本可能支持，没有测试过。



* BitShares 需要 [OpenSSL](https://www.openssl.org/) 库来构建, 支持版本 `1.0.2` to `1.1.1`.


###

打开bitshares-core文件夹，在此文件夹打开命令行窗口输入下列命令后按确认键

    ./programs/witness_node/witness_node

会创建一个 `witness_node_data_dir`文件夹，等个1分钟，按 `Ctrl+C` 退出

然后输入下列命令按确认键开启cli_wallet，这个'wss://api.bts.ai/ws‘可以替换成其它的节点链接：

    ./programs/cli_wallet/cli_wallet --server-rpc-endpoint=wss://api.bts.ai/ws

如果第一次没有出现下面这个new，就再输入一下上面的命令：

    new >>> info

*输入set_password按确认键：

      new >>> set_password [ENTER]

出现下面这个，在后面设置一个密码，注意: 输入的时候密码是不显示的：

      Enter password:
      locked >>> unlock [ENTER]
      Enter password:
      unlocked >>>


下面这个命令是为了能够联系你的账户， import_key <账户名> <私钥>


    unlocked >>> import_key <ACCOUNT_NAME> <WIF_KEY>

之后就可以各种骚操作。

注意：最后退出的时候，要输入“lock”锁定账户，因为不会自动锁定。


    unlocked >>> lock

更多信息参看:  [Wiki](https://github.com/bitshares/bitshares-core/wiki/CLI-Wallet-Cookbook).

