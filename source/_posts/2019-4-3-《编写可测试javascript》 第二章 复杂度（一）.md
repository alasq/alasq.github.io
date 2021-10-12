---
layout:     post
title:     《编写可测试javascript》 第二章 复杂度（一）
date:       2019-4-3
author:     Alasq
header-img: img/post-bg-universe.jpg
catalog: true
tags:
    - 读书笔记
---




## 目录
1. 代码大小
2. JSLint
3. 圈复杂度
4. 重用
5. 扇出
6. 扇入
7. 耦合（耦合度由大到小排列）
  内容耦合
  公共耦合
  控制耦合
  印记耦合
  数据耦合
  无耦合
  实例化
8. 耦合性度量
9. 现实中耦合
10. 依赖注入
11. 注释
YUIDoc JSDoc Docco/Rocco
12. 人工测试
13. 小结

### 1.代码大小
**定义**：函数的行数（包括注释行数）
减少该复杂度的方式 **拆函数**
* 命令（command）和 查询（query）分离
 命令（command）：没有return 的函数
 查询（query）：带return 的函数
### 2.JSLint
**规范书写语法**，简洁代码，减少复杂度
### 3.圈复杂度
**定义**：获得100%代码覆盖率需要编写的**单元测试个数**（if/else/switch/then 的使用）
最佳实践：**方法的圈复杂度应该小于10个**，>25个一定有bug；>100个，bug越改越多
检测工具：jscheckstyle
> `npm i -g jscheckstyle` 

**理论与实践**：
我做的项目中有一个判断基站颜色显示的逻辑，绘制canvas站点的fillStyle
入参包括
* 是否规划站 黄色
* 是否现网站 蓝色
* 是否新建站 绿色
* 天线型号 2t2t 4t4r 8t8r 16t16r  基于站点类型增加颜色饱和度
* 是否离线站点  灰色
* 是否搜索结果  红色
这些放在一个方法里面的圈复杂度应该是
圈复杂度=天线4*站点类型3*是否离线2*是否搜索结果2=48
```javascript
function getColor(siteType,trType,isSearchResult,isOffAir){
  var color='blue'
  if(isSearchResult){
      return color='red'
  }
  if(isOffAir){
   return color='gray'
  }
//这里项目中用的if else if else 的嵌套结构，太恶心，这里用switch优化了下
  switch(siteType){
        case 'current':  
           if(trType=='2t2r')color='淡蓝'
           if(trType=='4t4r')color='浅蓝'
           if(trType=='8t8r')color='蓝'
           if(trType=='16t16r')color='深蓝'
           break;
        case 'new': 
           if(trType=='2t2r')color='淡绿'
           if(trType=='4t24')color='浅绿'
           if(trType=='8t8r')color='绿'
           if(trType=='16t16r')color='深绿'
           break;
        case 'plan': 
           if(trType=='2t2r')color='淡黄'
           if(trType=='4t24')color='浅黄'
           if(trType=='8t8r')color=' 黄'
           if(trType=='16t16r')color='深黄'
           break;
         default:
          
  }
 return color
}
```
尝试降低上面这个方法的圈复杂度
```javascript
getColor(siteType,trType,isSearchResult,isOffAir){
var colorMap={
    current:{
   '2t2r':'淡蓝',
   '4t4r':'浅蓝',
   '8t8r':'蓝',
   '16t16r':'深蓝'
},
    'new':{
   '2t2r':'淡蓝',
   '4t4r':'浅蓝',
   '8t8r':'蓝',
   '16t16r':'深蓝'
},
    plan:{
   '2t2r':'淡蓝',
   '4t4r':'浅蓝',
   '8t8r':'蓝',
   '16t16r':'深蓝'
 }
}
  var color='blue'
  if(isSearchResult){
      return color='red'
  }
  if(isOffAir){
   return color='gray'
  }
  
  try{
    color =colorMap[siteType][trType]
  }catch(e){
    console.log('colorMap 中没有定义这个颜色')
  }

return color
}
```
后续如果增加新的站点类型或者天线类型，只要维护mapColor这个hash表就行了，不会再增加代码的圈复杂度，代码的可读与可维护性大大增强
### 4.重用
**同样的代码不要写两次** 没什么好说的，就像出轨有了第一次就一定有第二次......
另外就是能使用框架，就不要自己造轮子
### 5.扇出Fan-Out（这个词好难理解），对应的还有扇入Fan-In
**定义**：函数直接或间接使用的模块或者对象数量
个人理解：`扇出就衡量一个函数做多少事。类比于人做事情，就是这个人指挥别人做的+他自己做的`
**复杂度计算公式**：` (fan_in * fan_out)²`
**扇出计算公式**：扇出=内部流程数量（指挥别人做的）+所更新数据结构数量（自己做的）
**最佳实践**：函数的**扇出应该小于等于4**，绝对不要大于7，超过的话就需要重构
解决方式：拆分模块，依赖注入
例子：requirejs定义一个模块，下面的就需要拆分了
```javascript
//拆分前
define([a,b,c,d,e,f,g,h],function(a,b,c,d,e,f,g,h){//定义一个模块，依赖了7个小模块
var module={
    a,b,c,d,e,f,g,h
  }
    return module
})
//拆分后
define([],function(a,b,c,d){
    function SubModule(){
        this.a=new a()
        this.b=new b()
        this.c=new c()
        this.d=new d()
    }
    subModule.prototype.getA=function(){return this.a}
    subModule.prototype.getB=function(){return this.b}
    subModule.prototype.getC=function(){return this.c}
    subModule.prototype.getD=function(){return this.d}
    return subModule
})
define([subModule,e,f,g,h],function(subModule,e,f,g,h){//仅仅减小扇出，但无实际意义
var module={
    a:subModule.getA(),
    b:subModule.getB(),
    c:subModule.getC(),
    d:subModule.getD(),
    e,f,g,h
  }
    return module
})
```
### 6.扇入（入参？）
定义：过程A的扇入是  过程A的内部流程数量 与 欲从过程A中获取信息的数据结构总和
高扇入复用程度越高，底层函数应该扇入高，扇出低。上层函数应该扇入低，扇出高。这样能保证函数的复杂度都比较低。
### 7.耦合
[《编写可测试javascript》 第二章 复杂度（二）](https://www.jianshu.com/p/33faf9d810f0)

