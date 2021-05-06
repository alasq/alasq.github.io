---
layout:     post
title:    《编写可测试javascript》 第三章 
date:      2019-4-6
author:     陈诗樵
header-img: img/post-bg-universe.jpg
catalog: true
tags:
    - 读书笔记
---
通过事件解耦和隔离代码是javascript的一个原生特性,参考浏览器的DOM事件模型
# 3.1 基于事件的好处
* 应用程序都与消息传递有关
* 拿到其他对象的消息
全局对象（易污染）
函数参数传入（参数过多）
函数参数注入（要维护注入列表）
局部初始化（紧耦合）
* 函数是javascript的第一公民
* 浏览器 DOM是事件模型
* nodejs 利用回调实现异步编程
# 3.2事件集线器
* 一个中央处理器（110接警中心）
* 向中央处理器注册事件的处理器（派出所，交警，刑警，消防，120急救中心，等）
* 事件触发器（打110报警的用户）
```javascript
eventHub.fire('着火了'，{address:'南山腾讯大厦'，leave:'烧了10层'})
eventHub.listen('着火了'，killFire)
function killFire(msg){
    console.log(`出动消防车到${msg.address}去灭火，火灾等级${leave}`)
}
```
集线器属于**公共耦合**，但在集线器对象里，没有共享的状态
##  3.2.1使用事件集线器
##  3.2.2事件的响应
##  3.2.3基于事件的架构与MVC架构(思想一致)
MVC倡导 关注点分离与模块化，基于事件的架构都满足
事件集线器==Controller
事件传递的数据==Model数据库的行
事件推送的数据==View查询模型获得数据
## 3.2.4基于事件架构与面向对象编程（不冲突，可以一起用）
面向对象=》继承耦合
面向对象=》没有链式交互对象
事件架构=》数据都是私有的，仅通过事件API暴露
事件架构=》没有生命周期问题，对象存在于整个应用程序生命周期，不需要析构
## 3.2.5 基于事件的架构与软件及服务（促进关系）
软件及服务（SaaS），每个独立的服务都可以加入事件集线器

# 3.3 web应用程序
web应用程序大多与web服务器搅合在一起
让事件集线器成为web应用程序的中心，而不是web服务器
使用socke.io可以解决http同源的问题
# 3.4测试基于事件的架构
略……
# 3.5基于事件的架构说明
1. 可伸缩性
集线器宕机，则整个app宕机，所以，搞一组集线器负载匀衡
2. 广播
广播给所有客户端会产生大量通信流量，所以慎用
3. 运行时检查
函数和方法名 拼写错误，编译器能检查到，但是事件是字符串不能检查到，建议使用枚举值
4. 安全性
事件集线器实现“可信任”客户端身份验证
socket.io支持数据加密
5. 状态
web服务器通过会话cookie记录状态
事件集线器本身会将会话注入到事件中

# 3.6更智能的集线器，事件交换机
事件分组：广播，单播
特性：节省网络带宽，自动防故障安全部署
## 3.6.1部署
新版本部署=重启web服务（一般的web应用）
目标：模块完全独立于web服务的部署（跟微服务的架构很像啊）
条件：停用事件监听而不删除事件
方式：事件交换机
```javascript
eventSwitch.on('depositMoney',function(data){
  cash+=data.depositAmount;
  eventSwitch.emit('depositMoney',cash)
},{type:'unicast'})//告知注册的是单播事件
//eventClient:done 这个事件不能由已连接的客户端触发
//单播
eventHub.on('eventClient:done',function(event){
  process.exit(0)
})
//广播
eventHub.on('eventClient:done',function(event){
  eventHub.removeAllListeers(event)
})
```
## 3.6.2一种实现
https://github.com/zzo/EventHub
`npm install EventHub`安装
`npm start EventHub`启动 默认监听5883端口
## 3.6.3 会话
```javascript
eventHub=require('EventHub/clients/server/eventClient.js')
.getClientHub('http://localhost:5886?token=secret')
eventHub.on('user',function(obj){
 var sessionID=obj['eventHub:session']
})
```
## 3.6.4 可拓展性
socket.io 支持多种客户端，多种语言，不仅仅是javascript
一个例子[https:github.com/zzo/BidSilent ](https:github.com/zzo/BidSilent )

## 3.7 小结
* 基于事件的架构
高度模块化
松耦合
小依赖
高可重用性
便于创建可测试javascript

* 事件集线器构建在 socket.io 上
* MVC实际上是用事件进行了增强
* 基于事件的架构开启了软件即服务,根据需要对小而独立的功能进行动态增删
* 使用事件交换机部署基于事件的模块非常容易,允许单独关闭旧模块,而不丢任何事件
* 测试已经隔离的模块更简单














