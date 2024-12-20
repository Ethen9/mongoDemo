 # 一、MangoDB虚拟机操作记录

参考资料：https://www.runoob.com/mongodb/mongodb-linux-install.html

## 1.安装、启动服务

端口：27017

~~~ 
Xshell 5 (Build 0752)
Copyright (c) 2002-2015 NetSarang Computer, Inc. All rights reserved.

Type `help' to learn how to use Xshell prompt.
[c:\~]$ 

Connecting to 192.168.36.129:22...
Connection established.
To escape to local shell, press 'Ctrl+Alt+]'.

Last login: Fri Nov 24 15:07:56 2023
[worker@localhost ~]$ sudo yum install libcurl openssl

我们信任您已经从系统管理员那里了解了日常注意事项。
总结起来无外乎这三点：

    #1) 尊重别人的隐私。
    #2) 输入前要先考虑(后果和风险)。
    #3) 权力越大，责任越大。

[sudo] worker 的密码：
worker 不在 sudoers 文件中。此事将被报告。
[worker@localhost ~]$ su root
密码：
[root@localhost worker]# yum install libcurl openssl
已加载插件：fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: mirrors.ustc.edu.cn
 * extras: mirrors.ustc.edu.cn
 * updates: mirrors.aliyun.com
正在解决依赖关系
--> 正在检查事务
---> 软件包 libcurl.x86_64.0.7.29.0-59.el7 将被 升级
--> 正在处理依赖关系 libcurl = 7.29.0-59.el7，它被软件包 curl-7.29.0-59.el7.x86_64 需要
---> 软件包 libcurl.x86_64.0.7.29.0-59.el7_9.1 将被 更新
---> 软件包 openssl.x86_64.1.1.0.2k-19.el7 将被 升级
---> 软件包 openssl.x86_64.1.1.0.2k-26.el7_9 将被 更新
--> 正在处理依赖关系 openssl-libs(x86-64) = 1:1.0.2k-26.el7_9，它被软件包 1:openssl-1.0.2k-26.el7_9.x86_64 需要
--> 正在检查事务
---> 软件包 curl.x86_64.0.7.29.0-59.el7 将被 升级
---> 软件包 curl.x86_64.0.7.29.0-59.el7_9.1 将被 更新
---> 软件包 openssl-libs.x86_64.1.1.0.2k-19.el7 将被 升级
---> 软件包 openssl-libs.x86_64.1.1.0.2k-26.el7_9 将被 更新
--> 解决依赖关系完成

依赖关系解决

=====================================================================================================================================================================
 Package                                  架构                               版本                                          源                                   大小
=====================================================================================================================================================================
正在更新:
 libcurl                                  x86_64                             7.29.0-59.el7_9.1                             updates                             223 k
 openssl                                  x86_64                             1:1.0.2k-26.el7_9                             updates                             494 k
为依赖而更新:
 curl                                     x86_64                             7.29.0-59.el7_9.1                             updates                             271 k
 openssl-libs                             x86_64                             1:1.0.2k-26.el7_9                             updates                             1.2 M

事务概要
=====================================================================================================================================================================
升级  2 软件包 (+2 依赖软件包)

总计：2.2 M
Is this ok [y/d/N]: y
Downloading packages:
警告：/var/cache/yum/x86_64/7/updates/packages/curl-7.29.0-59.el7_9.1.x86_64.rpm: 头V3 RSA/SHA256 Signature, 密钥 ID f4a80eb5: NOKEY
从 file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 检索密钥
导入 GPG key 0xF4A80EB5:
 用户ID     : "CentOS-7 Key (CentOS 7 Official Signing Key) <security@centos.org>"
 指纹       : 6341 ab27 53d7 8a78 a7c2 7bb1 24c6 a8a7 f4a8 0eb5
 软件包     : centos-release-7-9.2009.0.el7.centos.x86_64 (@anaconda)
 来自       : /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
是否继续？[y/N]：y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  正在更新    : libcurl-7.29.0-59.el7_9.1.x86_64                                                                                                                 1/8 
  正在更新    : 1:openssl-libs-1.0.2k-26.el7_9.x86_64                                                                                                            2/8 
  正在更新    : 1:openssl-1.0.2k-26.el7_9.x86_64                                                                                                                 3/8 
  正在更新    : curl-7.29.0-59.el7_9.1.x86_64                                                                                                                    4/8 
  清理        : 1:openssl-1.0.2k-19.el7.x86_64                                                                                                                   5/8 
  清理        : curl-7.29.0-59.el7.x86_64                                                                                                                        6/8 
  清理        : libcurl-7.29.0-59.el7.x86_64                                                                                                                     7/8 
  清理        : 1:openssl-libs-1.0.2k-19.el7.x86_64                                                                                                              8/8 
  验证中      : curl-7.29.0-59.el7_9.1.x86_64                                                                                                                    1/8 
  验证中      : 1:openssl-libs-1.0.2k-26.el7_9.x86_64                                                                                                            2/8 
  验证中      : libcurl-7.29.0-59.el7_9.1.x86_64                                                                                                                 3/8 
  验证中      : 1:openssl-1.0.2k-26.el7_9.x86_64                                                                                                                 4/8 
  验证中      : libcurl-7.29.0-59.el7.x86_64                                                                                                                     5/8 
  验证中      : curl-7.29.0-59.el7.x86_64                                                                                                                        6/8 
  验证中      : 1:openssl-1.0.2k-19.el7.x86_64                                                                                                                   7/8 
  验证中      : 1:openssl-libs-1.0.2k-19.el7.x86_64                                                                                                              8/8 

更新完毕:
  libcurl.x86_64 0:7.29.0-59.el7_9.1                                                 openssl.x86_64 1:1.0.2k-26.el7_9                                                

作为依赖被升级:
  curl.x86_64 0:7.29.0-59.el7_9.1                                                openssl-libs.x86_64 1:1.0.2k-26.el7_9                                               

完毕！
[root@localhost worker]# ls
公共  模板  视频  图片  文档  下载  音乐  桌面
[root@localhost worker]# cd /
[root@localhost /]# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
[root@localhost /]# cd home
[root@localhost home]# ls
worker
[root@localhost home]# cd worker
[root@localhost worker]# ls
公共  模板  视频  图片  文档  下载  音乐  桌面
[root@localhost worker]# mkdir mangodb
[root@localhost worker]# ls
mangodb  公共  模板  视频  图片  文档  下载  音乐  桌面
[root@localhost worker]# cd mangodb
[root@localhost mangodb]# ls
[root@localhost mangodb]# wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-4.2.24.tgz
--2023-11-24 15:22:43--  https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-4.2.24.tgz
正在解析主机 fastdl.mongodb.org (fastdl.mongodb.org)... 13.226.210.112, 13.226.210.84, 13.226.210.71, ...
正在连接 fastdl.mongodb.org (fastdl.mongodb.org)|13.226.210.112|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度：133613384 (127M) [application/gzip]
正在保存至: “mongodb-linux-x86_64-rhel70-4.2.24.tgz”

100%[===========================================================================================================================>] 133,613,384 3.87MB/s 用时 27s    

2023-11-24 15:23:12 (4.64 MB/s) - 已保存 “mongodb-linux-x86_64-rhel70-4.2.24.tgz” [133613384/133613384])

[root@localhost mangodb]# ls
mongodb-linux-x86_64-rhel70-4.2.24.tgz
[root@localhost mangodb]# tar -zxvf mongodb-linux-x86_64-rhel70-4.2.24.tgz
mongodb-linux-x86_64-rhel70-4.2.24/THIRD-PARTY-NOTICES.gotools
mongodb-linux-x86_64-rhel70-4.2.24/README
mongodb-linux-x86_64-rhel70-4.2.24/THIRD-PARTY-NOTICES
mongodb-linux-x86_64-rhel70-4.2.24/MPL-2
mongodb-linux-x86_64-rhel70-4.2.24/LICENSE-Community.txt
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongodump
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongorestore
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongoexport
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongoimport
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongostat
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongotop
mongodb-linux-x86_64-rhel70-4.2.24/bin/bsondump
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongofiles
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongoreplay
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongod
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongos
mongodb-linux-x86_64-rhel70-4.2.24/bin/mongo
mongodb-linux-x86_64-rhel70-4.2.24/bin/install_compass
[root@localhost mangodb]# ls
mongodb-linux-x86_64-rhel70-4.2.24  mongodb-linux-x86_64-rhel70-4.2.24.tgz
[root@localhost mangodb]# mv mongodb-linux-x86_64-rhel70-4.2.24 /usr/local/mongodb4
[root@localhost mangodb]# ls
mongodb-linux-x86_64-rhel70-4.2.24.tgz
[root@localhost mangodb]# cd /usr/local
[root@localhost local]# ls
bin  etc  games  include  lib  lib64  libexec  mongodb4  sbin  share  src
[root@localhost local]# export PATH=/usr/local/mongodb4/bin:$PATH
[root@localhost local]# cd /var/lib/mongodb
bash: cd: /var/lib/mongodb: 没有那个文件或目录
[root@localhost local]# mkdir /var/lib/mongo
[root@localhost local]# mkdir -p /var/log/mongodb
[root@localhost local]# sudo mkdir -p /var/lib/mongo
[root@localhost local]# sudo chown `worker` /var/lib/mongo
bash: worker: 未找到命令...
chown: "/var/lib/mongo" 后缺少操作数
Try 'chown --help' for more information.
[root@localhost local]# sudo chown `whoami` /var/lib/mongo
[root@localhost local]# sudo chown `whoami` /var/log/mongodb
[root@localhost local]# mongod --dbpath /var/lib/mongo --logpath /var/log/mongodb/mongod.log --fork
about to fork child process, waiting until server is ready for connections.
forked process: 3615
child process started successfully, parent exiting
[root@localhost local]# # tail -10f /var/log/mongodb/mongod.log
[root@localhost local]# tail -10f /var/log/mongodb/mongod.log
2023-11-24T15:33:29.022+0800 I  STORAGE  [LogicalSessionCacheRefresh] createCollection: config.system.sessions with provided UUID: c1cbecbe-b333-4f3b-913a-47ae314e02c4 and options: { uuid: UUID("c1cbecbe-b333-4f3b-913a-47ae314e02c4") }
2023-11-24T15:33:29.022+0800 I  NETWORK  [listener] Listening on /tmp/mongodb-27017.sock
2023-11-24T15:33:29.022+0800 I  NETWORK  [listener] Listening on 127.0.0.1
2023-11-24T15:33:29.022+0800 I  NETWORK  [listener] waiting for connections on port 27017
2023-11-24T15:33:29.025+0800 I  INDEX    [LogicalSessionCacheRefresh] index build: done building index _id_ on ns config.system.sessions
2023-11-24T15:33:29.027+0800 I  INDEX    [LogicalSessionCacheRefresh] index build: starting on config.system.sessions properties: { v: 2, key: { lastUse: 1 }, name: "lsidTTLIndex", ns: "config.system.sessions", expireAfterSeconds: 1800 } using method: Hybrid
2023-11-24T15:33:29.027+0800 I  INDEX    [LogicalSessionCacheRefresh] build may temporarily use up to 200 megabytes of RAM
2023-11-24T15:33:29.027+0800 I  INDEX    [LogicalSessionCacheRefresh] index build: collection scan done. scanned 0 total records in 0 seconds
2023-11-24T15:33:29.028+0800 I  INDEX    [LogicalSessionCacheRefresh] index build: inserted 0 keys from external sorter into index in 0 seconds
2023-11-24T15:33:29.028+0800 I  INDEX    [LogicalSessionCacheRefresh] index build: done building index lsidTTLIndex on ns config.system.sessions
:q
^[^H^H^H^H
^C
[root@localhost local]# 

~~~

## 2.其他

安装包位置： /usr/local/mongodb4

> 虚拟机里面不行的话试试 ：/usr/local/mongodb4

### 启动

切换到bin目录下，./mongo

### 添加用户

db.createUser({ user: "yxy", pwd: "123456", roles: ["root"] })

huierYFB2023

huier19882022



# 二、MongoDB概念解析

## 1.命令

### 1.show dbs

显示所有的数据库

~~~　
$ ./mongo
MongoDB shell version: 3.0.6
connecting to: test
> show dbs
local  0.078GB
test   0.078GB
> 

~~~



### 2.db

显示当前数据库

~~~ 
$ ./mongo
MongoDB shell version: 3.0.6
connecting to: test
> db
test
> 

~~~



### 3.use

连接到某一数据库

~~~ 
> use local
switched to db local
> db
local
> 

~~~



## 2.数据库命名规范

* 不能为空

* 不能有特殊字符

  > 不得含有' '（空格)、.、$、/、\和\0 (空字符)。

* 全部小写

* 最多64字节



## 3.特殊数据库

* admin：关于访问权限
* local：存储本地服务器的任意集合
* config：当Mongo用于分片设置时，config数据库在内部使用，用于保存分片的相关信息



## 4.文档-Document

对应关系型数据库的行。

~~~ 
{"site":"www.runoob.com", "name":"菜鸟教程"}
~~~



需要注意的是：

1. 文档中的键/值对是有序的。
2. 文档中的值不仅可以是在双引号里面的字符串，还可以是其他几种数据类型（甚至可以是整个嵌入的文档)。
3. MongoDB区分类型和大小写。
4. MongoDB的文档不能有重复的键。
5. 文档的键是字符串。除了少数例外情况，键可以使用任意UTF-8字符。

文档键命名规范：

- 键不能含有\0 (空字符)。这个字符用来表示键的结尾。
- .和$有特别的意义，只有在特定环境下才能使用。
- 以下划线"_"开头的键是保留的(不是严格要求的)。



## 5.集合-collection

相当于RDBMS中的整个标，但是它没有固定的结构，即文档的集合，

~~~ 
{"site":"www.baidu.com"}
{"site":"www.google.com","name":"Google"}
{"site":"www.runoob.com","name":"菜鸟教程","num":5}

~~~



# 三、指令

## 1.创建数据/日志目录

~~~ bash
#创建存放数据的目录
mkdir -p /usr/local/mongodb/data/db
#创建存放日志的目录
mkdir -p /usr/local/mongodb/logs
#创建日志记录文件
touch /usr/local/mongodb/logs/mongodb.log
~~~



**注意：这里创建文件及文件夹非常重要，要使用-p参数**



## 2.启动MongoDB

### 2.1 前台启动

~~~ bash
#切换至指定目录
cd /usr/local/mongodb
#前台启动
bin/mongod --dbpath /usr/local/mongodb/data/db --logpath /usr/local/mongodb/logs/mongodb.log --logappend --port 27017 --bind_ip 0.0.0.0
~~~

* --dbpath：指定数据文件存放目录
* --logappend：指定日志文件，注意是指定文件不是目录
* --logappend：使用追加的方式记录日志
* --port：指定端口，默认27017
* --bind_ip：绑定服务ip，若为127.0.0.1，则只能本机访问，默认为本机访问

> ctrl+c 前台退出



### 2.2 后台启动

~~~ bash
#后台启动
bin/mongod --dbpath /usr/local/mongodb/data/db --logpath /usr/local/mongodb/logs/mongodb.log --logappend --port 27017 --bind_ip 0.0.0.0 --fork
#结束
bin/mongod --dbpath /usr/local/mongodb/data/db --logpath /usr/local/mongodb/logs/mongodb.log --logappend --port 27017 --bind_ip 0.0.0.0 --fork --shutdown
~~~



#### 配置文件

在bin目录下增加一个mongodb.conf配置文件

~~~ 
# 数据文件存放目录
dbpath = /usr/local/mongodb/data/db
# 日志文件存放目录
logpath = /usr/local/mongodb/logs/mongodb.log
# 以追加的方式记录日志
logappend = true
# 端口默认为 27017
port = 27017
#对访问IP地址不做限制，默认为本机地址
bind_ip = 0.0.0.0
# 以守护进程的方式启用，就在后台运行
fork = true
~~~



#### 配置文件启动

~~~ bash
bin/mongod -f bin/mongodb.conf
~~~

#### 配置文件关闭

~~~ bash
bin/mongod -f bin/mongodb.conf --shutdown
~~~



### 2.3 MongoDB函数关闭

~~~ bash
# 连接mongodb
bin/mongo
# 切换 admin数据库
use admin
# 执行以下函数（2选1）
db.shutdownServer()
db.runConmmand("shutdown")
~~~



## 3.环境变量

打开环境变量文件

~~~ bash
vim /etc/profile
# 在文件中添加如下内容
export MONGODB_HOME=/usr/local/mongodb
export PATH=$PATH:$MONGODB_HOME/bin

# 保存后退出
source /etc/profile

# 通过配置文件启动
mongod -f /usr/local/mongodb/bin/mongodb.conf
# 通过配置文件启动
mongod -f /usr/local/mongodb/bin/mongodb.conf --shutdown

# 进入mongo的shell
mongo
~~~



## 4.创建管理用户

~~~ shell
db.createUser({user:"uaad",pwd:"uaad",roles:[{role:"userAdminAnyDatabase",db:"admin"}]})
~~~



### 4.1 重启服务并开启认证

启动命令添加参数 --auth

~~~ bash
bin/mongod -f bin/mongodb.conf --auth
~~~

将参数写到配置文件中去

~~~ bash
vim /usr/local/mongodb/bin/mongodb.conf

~~~



### 4.2 登录

~~~bash
use admin
db.auth("uaad","uaad")
~~~



## 5.创建普通用户

创建一个test数据库，添加用户testuser，密码123456。该用户对test用户拥有读写权限。

### 5.1 管理员登录数据库

~~~ bash
use admin
db.auth("uaad","uaad")
~~~



### 5.2创建数据库

切换数据库时，如果数据库不存在，则会直接创建

~~~ bash
# 创建数据库
use test
# 创建用户
db.createUser({user:"testUser",pwd:"123456",roles:[{role:"readWrite",db:"test"}]})
~~~

登录后插入数据

~~~ bash
# 登录后认证
db.user.insert({"name":"zhangsan"})
~~~



## 6.使用GUI工具连接

* 记得密码验证选择sha256
* 连接不通时查看对应端口是否打开（27017）或者关闭防火墙（虚拟机可以这样做，实际不要这样）



## 7.数据去重：保留一个文档

huier_clients_info集合中，去除掉重复的ictid，只保留一个

~~~ javascript
db.huier_clients_info.aggregate([
    {
        $group: {
            _id: "$ictid",
            count: { $sum: 1 },
            dups: { $addToSet: "$_id" }
        }
    },
    {
        $match: { count: { $gt: 1 } }
    }
]).forEach(function(it) {
    it.dups.shift();
    db.huier_clients_info.remove({ _id: { $in: it.dups } });
});
~~~

> 参考文档：https://juejin.cn/post/7015480289736523784



## 8.数据去重：删除所有重复的文档

huier_clients_info集合

![image-20240522104520279](图片/image-20240522104520279.png)

~~~ javascript
function deleteDuplicateIctidDocs() {
  // 第一步：找到重复的 ictid 值
  const duplicateGroups = db.huier_clients_info.aggregate([
    {
      $group: {
        _id: "$ictid",
        count: { $sum: 1 },
        docs: { $push: "$$ROOT" }
      }
    },
    {
      $match: {
        count: { $gt: 1 }
      }
    },
    {
      $project: {
        _id: 1
      }
    }
  ], {
    allowDiskUse: true
  }).toArray();

  // 提取重复的 ictid 值
  const duplicateIctidValues = duplicateGroups.map(doc => doc._id);

  // 第三步：删除具有重复 ictid 的所有文档，并统计删除的数量
  const deleteResult = db.huier_clients_info.deleteMany({
    ictid: { $in: duplicateIctidValues }
  });

  // 输出删除的文档数量
  printjson({ deletedCount: deleteResult.deletedCount });
}

// 执行函数
deleteDuplicateIctidDocs();

~~~



## 9.数据去重：查找有重复ictid的文档

![image-20240522105207561](图片/image-20240522105207561.png)

~~~ javascript
db.huier_clients_info.aggregate([
  {
    $group: {
      _id: "$ictid",
      count: { $sum: 1 },
      docs: { $push: "$$ROOT" }
    }
  },
  {
    $match: {
      count: { $gt: 1 }
    }
  },
  {
    $project: {
      _id: 0,
      ictid: "$_id",
      docs: 1
    }
  }
], {
  allowDiskUse: true
});
~~~





## 10.删除所有文档的指定字段

ｍongo 原生语法，删除所有文档的fitting_records字段

~~~
db.getCollection('huier_clients_info').updateMany(
    {},
    { $unset: { fitting_records: "" } }
)
~~~



## 11.给集合中的文档添加字段

### 添加id字段，其值为_id的字符串形式（含嵌套文档）

huier_clients_info集合，给文档添加id，并且给fitting_records中的嵌套文档添加id，其值为fitting_record的_id的字符串形式；

~~~ javascript
db.huier_clients_info.find({}).forEach(function(doc) {
    // Check if the fitting_records field exists and is an array
    if (Array.isArray(doc.fitting_records)) {
        doc.fitting_records.forEach(function(record) {
            // Check if the _id field exists in the record
            if (record._id) {
                // Add the id field to each record in the fitting_records array
                record.id = record._id.str;
            } else {
                print("No _id found in record: ", tojson(record));
            }
        });

        // Update the document with the modified fitting_records array
        db.huier_clients_info.updateOne(
            { _id: doc._id },
            { $set: { fitting_records: doc.fitting_records } }
        );
    }
});

~~~

### 添加id字段，值为_id的字符串形式（不含嵌套文档）

~~~ 
db.huier_clients_info.find({}).forEach(function(doc) {
  db.huier_clients_info.updateOne(
    { _id: doc._id },
    { $set: { id: doc._id.str } }
  );
});
~~~



## 12.查找测听次数大于1的用户

huier_clients_info集合中，查找测听次数大于1的用户

~~~ javascript
db.huier_clients_info.find({
  $expr: {
    $gte: [{ $size: "$audiometry_records" }, 2]
  }
})
~~~



## 13.删除掉对象数组中的非对象元素：字符串元素

fitting_records字段

~~~javascript
db.huier_clients_info.find().forEach(doc => {
    // Log the document ID and fitting_records before processing
    print(`Processing document with _id: ${doc._id}`);
    print(`Original fitting_records: ${tojson(doc.fitting_records)}`);

    if (Array.isArray(doc.fitting_records)) {
        let updatedFittingRecords = doc.fitting_records.filter(item => typeof item === 'object' && !Array.isArray(item));

        // Log the filtered fitting_records
        print(`Updated fitting_records: ${tojson(updatedFittingRecords)}`);

        db.huier_clients_info.updateOne(
            { _id: doc._id },
            { $set: { fitting_records: updatedFittingRecords } }
        );
    } else {
        // Log if fitting_records is not an array
        print(`fitting_records is not an array for document with _id: ${doc._id}`);
    }
});

~~~





# 四、MongoDB相关知识

## 官方文档

https://docs.mongoing.com/can-kao/mongodb-limits-and-thresholds



## 1.文档大小 影响因素

### 引擎版本

| 引擎       | 最大单个文档 | 备注             |
| ---------- | ------------ | ---------------- |
| MMAPv1     | 16MB         |                  |
| WiredTiger | 48MB         | 阿里云使用此引擎 |

需要注意的是，虽然 MongoDB 支持存储大文档，但是在应用设计中，应该尽量避免使用过大的文档。因为大文档可能会影响查询性能和内存使用等方面的问题。

同时，使用 GridFS 存储大文件时，也需要考虑 GridFS 的性能和管理成本等问题。

> GridFS ：引用方式，会降低一些查询效率，相当于根据索引再查询一次



## 2.命名限制

### 数据库名称不区分大小写



### 数据库名称的长度

数据库名不能为空并且必须小于64个字符。





# 五、官方文档笔记

## 1.游标cursor

官方文档：https://www.mongodb.com/zh-cn/docs/manual/reference/method/js-cursor/

| 名称                                                         | 说明                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [`cursor.addOption()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.addOption/#mongodb-method-cursor.addOption) | 添加可修改查询行为的特殊传输协议标记。                       |
| [`cursor.allowDiskUse()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.allowDiskUse/#mongodb-method-cursor.allowDiskUse) | 允许 MongoDB 在处理阻塞排序操作时使用磁盘上的临时文件来存储超过 100 MB 系统内存限制的数据。 |
| [`cursor.allowPartialResults()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.allowPartialResults/#mongodb-method-cursor.allowPartialResults) | 如果一个或多个查询的分片不可用，则允许对分片集合进行 [`db.collection.find()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/db.collection.find/#mongodb-method-db.collection.find) 操作，以返回部分结果，而不是错误。 |
| [`cursor.batchSize()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.batchSize/#mongodb-method-cursor.batchSize) | 控制 MongoDB 将在单个网络消息中返回到客户端的文档数量。      |
| [`cursor.close()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.close/#mongodb-method-cursor.close) | 关闭游标并释放关联的服务器资源。                             |
| [`cursor.isClosed()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.isClosed/#mongodb-method-cursor.isClosed) | 如果游标关闭，则返回 `true`。                                |
| [`cursor.collation()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.collation/#mongodb-method-cursor.collation) | 指定 [`db.collection.find()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/db.collection.find/#mongodb-method-db.collection.find) |
| [`cursor.comment()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.comment/#mongodb-method-cursor.comment) | 将注释附加到查询，以允许在日志和 system.profile 集合中进行跟踪。 |
| [`cursor.count()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.count/#mongodb-method-cursor.count) | 修改游标，以返回结果集中的文档数量，而不是文档本身。         |
| [`cursor.explain()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.explain/#mongodb-method-cursor.explain) | 报告游标的查询执行计划。                                     |
| [`cursor.forEach()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.forEach/#mongodb-method-cursor.forEach) | 对游标中的每个文档应用 JavaScript 函数。                     |
| [`cursor.hasNext()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.hasNext/#mongodb-method-cursor.hasNext) | 如果游标包含文档且可迭代，则返回 true。                      |
| [`cursor.hint()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.hint/#mongodb-method-cursor.hint) | 强制 MongoDB 对查询使用特定索引。                            |
| [`cursor.isExhausted()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.isExhausted/#mongodb-method-cursor.isExhausted) | 如果游标已关闭`true`批处理中没有剩余对象，则返回 *且*。      |
| [`cursor.itcount()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.itcount/#mongodb-method-cursor.itcount) | 通过获取和迭代结果集，计算游标客户端中的文档总数。           |
| [`cursor.limit()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.limit/#mongodb-method-cursor.limit) | 限制游标结果集的大小。                                       |
| [`cursor.map()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.map/#mongodb-method-cursor.map) | 将函数应用于游标中的每个文档，并收集数组中的返回值。         |
| [`cursor.max()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.max/#mongodb-method-cursor.max) | 指定游标的独占索引上限。与 [`cursor.hint()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.hint/#mongodb-method-cursor.hint) |
| [`cursor.maxAwaitTimeMS()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.maxAwaitTimeMS/#mongodb-method-cursor.maxAwaitTimeMS) | 指定等待下一查询结果更新的时间限制（以毫秒为单位）。         |
| [`cursor.maxTimeMS()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.maxTimeMS/#mongodb-method-cursor.maxTimeMS) | 指定在游标上处理操作的累计时间限制（以毫秒为单位）。         |
| [`cursor.min()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.min/#mongodb-method-cursor.min) | 指定游标的包含式索引下限。与 [`cursor.hint()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.hint/#mongodb-method-cursor.hint) |
| [`cursor.next()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.next/#mongodb-method-cursor.next) | 返回游标中的下一个文档。                                     |
| [`cursor.noCursorTimeout()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.noCursorTimeout/#mongodb-method-cursor.noCursorTimeout) | 指示服务器避免在一段时间不活动后自动关闭游标。               |
| [`cursor.objsLeftInBatch()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.objsLeftInBatch/#mongodb-method-cursor.objsLeftInBatch) | 返回当前游标批处理中剩余文档的数量。                         |
| [`cursor.pretty()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.pretty/#mongodb-method-cursor.pretty) | 将游标配置为以易于阅读的格式显示结果。                       |
| [`cursor.readConcern()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.readConcern/#mongodb-method-cursor.readConcern) | 为 操作指定[``](https://www.mongodb.com/zh-cn/docs/manual/reference/method/db.collection.find/#mongodb-method-db.collection.find)。 |
| [`cursor.readPref()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.readPref/#mongodb-method-cursor.readPref) | 为游标指定[读取偏好](https://www.mongodb.com/zh-cn/docs/manual/reference/glossary/#std-term-read-preference)，以控制客户端如何将查询定向到[副本集](https://www.mongodb.com/zh-cn/docs/manual/reference/glossary/#std-term-replica-set) |
| [`cursor.returnKey()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.returnKey/#mongodb-method-cursor.returnKey) | 修改游标以返回索引键而不是文档。                             |
| [`cursor.showRecordId()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.showRecordId/#mongodb-method-cursor.showRecordId) | 向游标返回的每个文档添加内部存储引擎 ID 字段。               |
| [`cursor.size()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.size/#mongodb-method-cursor.size) | 应用 [`skip()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.skip/#mongodb-method-cursor.skip) 和 [`limit()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.limit/#mongodb-method-cursor.limit) 方法后，返回游标中文档的计数。 |
| [`cursor.skip()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.skip/#mongodb-method-cursor.skip) | 返回一个游标，该游标仅在传递或跳过多个文档后才开始返回结果。 |
| [`cursor.sort()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.sort/#mongodb-method-cursor.sort) | 根据排序规范返回排序的结果。                                 |
| [`cursor.tailable()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.tailable/#mongodb-method-cursor.tailable) | 将游标标记为循环式。仅对超过固定大小集合的游标有效。         |
| [`cursor.toArray()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.toArray/#mongodb-method-cursor.toArray) | 返回一个数组，其中包含游标返回的所有文档。                   |
| [`cursor.tryNext()`](https://www.mongodb.com/zh-cn/docs/manual/reference/method/cursor.tryNext/#mongodb-method-cursor.tryNext) | 返回迭代中的下一个元素（如果有），否则返回 null。            |





# 六、备份及恢复

## 通过物理备份文件（.xb）操作记录：

大费周折，终于把备份数据库迁移到本地了！

> 这里使用的虚拟机是：centos_MongoDB_test_node5，
>
> 后续如果还有恢复数据的需求，可以直接在data目录下，新建一个数据仓库，将备份文件在其中解压，再修改启动配置文件中的数据仓库即可；



### 背景：

误删除了集合数据，通过下载阿里云.xb自动备份文件，在自己数据库上恢复数据；



### 资料

| 网址                                                         | 备注                          |             |
| ------------------------------------------------------------ | ----------------------------- | ----------- |
| https://www.mongodb.com/try/download/community-kubernetes-operator | mongodb官网安装包下载         | 这里下载4.1 |
| https://www.bilibili.com/video/BV1gh411r7sT?p=3&vd_source=17e98111eb2d8d2912ccc19c1d1e22b8 | B站视频：安装mongodb          |             |
| https://help.aliyun.com/zh/mongodb/user-guide/restore-the-data-of-an-apsaradb-for-mongodb-instance-to-a-self-managed-mongodb-database-by-using-physical-backups?spm=a2c4g.11186623.0.i2#section-lxg-5xp-5fb | 阿里云：数据恢复至自建站      |             |
| https://www.cnblogs.com/muzlei/p/16555163.html               | 解压.xb文件所需要的依赖安装： |             |



### 恢复环境：

1. centos7虚拟机；

2. 需要安装与云数据库版本相近的mongodb；

3. 安装解压.xb文件的命令环境：

   > 参考资料：https://www.cnblogs.com/muzlei/p/16555163.html

   ~~~ 
   [root@centos7 ~]# yum -y install https://repo.percona.com/yum/percona-release-latest.noarch.rpm
   [root@centos7 ~]# yum -y  install percona-xtrabackup-24  
   [root@centos7 ~]# yum -y  install qpress  ##innobackupex支持压缩导出，这里安装压缩工具
    
   [root@centos7 ~]# innobackupex -version  ###如果出现如下提示表示安装成功，我这里2.4.15
   xtrabackup: recognized server arguments: --server-id=11 --datadir=/data/mysql_data --tmpdir=/tmp --log_bin=bin.log --innodb_page_size=8192 --innodb_buffer_pool_size=2G --innodb_io_capacity=4000 --innodb_flush_method=O_DIRECT --innodb_undo_tablespaces=3 --innodb_log_file_size=128M --innodb_log_buffer_size=16777216 
   innobackupex version 2.4.15 Linux (x86_64) (revision id: 544842a)
   [root@centos7 ~]# 
   ~~~

   

### 步骤：

1. 按照阿里云数据恢复指导步骤，进行操作；

2. 注意：

   1. mongodb创建文件及文件夹时，要加-p参数，不然会出现一些无法读取、权限不够的为你，但是又不会明确的指出来，这里可以参考B站视频；

   2. 要在mongo的data文件夹下，创建新的db目录，我是创建的db2目录，将.xb文件拷贝进去，然后进行解压等操作；

      > 创建db2目录时，注意要加-p参数

   3. 按照阿里云文档，写mongod.conf配置文件时，注意要改成自己的路径

3. 部分要用到的命令

   1. mongodb启动后，通过命令行进入mongo：

      ~~~ 
      mongo --host 127.0.0.1 -u root -p huierYFB2023 --authenticationDatabase admin
      ~~~

   2. 在bin目录下，将指定集合，按照json格式，导出至指定目录：

      > 使用mongoexport导出程序

      ~~~ 
      cd /usr/local/mongodb/bin
      ./mongoexport --host 127.0.0.1 --port 27017 --username root --password huierYFB2023 --authenticationDatabase admin --db hueir --collection hd_orders_info --out /path/to/save/hd_orders_info.json --jsonArray
      ~~~

      
