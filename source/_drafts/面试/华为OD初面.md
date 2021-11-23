---
title: 华为OD岗位初面
date: 2021-10-26 07:25:40
tags: 面试
---
### 基础部分
1. 跨域解决方法
2. chrome最近版本升级,导致了哪些问题,怎么解决
3. https服务器怎么搭建
4. vue响应式原理
5. 事件循环
6. http2相对http1.1改进点
7. 华为sso单点登录原理，遇到登录后无限重定向，然后提示登录次数太多，怎么解决

### 笔试部分
#### 题目一,实现 `add(1)(3)(3)===9`
我直接跟面试官说实现不了,面试官改了题目,`add(1)(3)(3)==9`
我说还是实现不了,需要改成`add(1)(3)(3)()`,才能实现,因为不知道怎么触发运算,面试官提醒我可以用`valueOf`去做,我恍然大悟。

```js
function add(val) {
  let ret=[val]
  function _add(val2) {
    ret.push(val2)
    return _add
  }
  _add.valueOf=function () {
    return ret.reduce((prev,next)=>prev+next,0)
  }
  return _add
}

console.assert(add(1)(2) == 3)
console.assert(add(1)(2)(3) == 6)
```

#### 题目二,实现二叉树查找
```js
const root = {
  val: 1,
  left: {
    val: 2,
    left: {
      val: 4,
      right: {
        val: 8
      }
    },
    right: {
      val: 5
    }
  },
  right: {
    val: 3,
    left: {
      val: 6,
      left: {
        val: 9
      },
      right: {
        val: 10
      }
    },
    right: {
      val: 7
    }
  }
}

// 这个现场写的,面试官说我投机取巧,使用了不存在的parent属性
function findPath(root, val) {
  let ret, result = []
  function getNext(obj) {
    if (obj.val == val) {
      ret = obj
      return
    }
    if (obj.left) {
      obj.left.parent = obj
      getNext(obj.left)
    }
    if (obj.right) {
      obj.right.parent = obj
      getNext(obj.right)
    }

  }
  getNext(root)
  if (ret) {
    result.unshift(ret.val)
    while (ret = ret.parent) {
      result.unshift(ret.val)
    }
    return result
  }
  return []
}


// 这个网上查的
function findPath(root, val) {
  let ret = [];

  try {
    function getNext(obj,level) {
      ret[level]=obj
      if (obj.val == val) {
        throw 'aaa'
      }
      if (obj.left) {
        getNext(obj.left,level+1)
      }
      if (obj.right) {
        getNext(obj.right,level+1)
      }
  
    }
    getNext(root,0)
  } catch (error) {
    
  }

  return ret.map(i=>i.val)
}

// 这个面试官让我带上path写深度查找,事后写的,应该是面试官希望看的版本
function findPath2(root, val) {

  try {
    function getNext(obj,stack) {
      stack.push(obj.val)//入栈
      if (obj.val == val) {
        throw stack
      }
      if (obj.left) {
        getNext(obj.left,stack)
      }
      if (obj.right) {
        getNext(obj.right,stack)
      }
      stack.pop()//出栈
    }
    getNext(root,[])
  } catch (error) {
    return error ||[]
  }
}

console.log(findPath2(root, 55))
```

## 总结
华为的技术面试官好牛叉,人肉调试器,我写的代码哪里有问题,一眼就能看出来。本来是面试我，最后变成教我改代码了。
