---
cover: https://fristnamecao.github.io/img/imgs/0_8.jpg
title: Map
date: 2023-02-12 14:14:23
tags: Map封装
categories: new Map()
---

# Map的封装

```<script>
  class Map2 {

    constructor() {

      this._keys = [] // 用来存储每组映射的key

      this._vals = [] // 用来存储每组映射的val

    }

    get(key) {

      var keyIdx = this._keys.indexOf(key)

      if (keyIdx >= 0) {

        return this._vals[keyIdx]

      }

    }

    has(key) { // 判断映射中是否存在某个key的映射

      var keyIdx = this._keys.indexOf(key)

      if (keyIdx >= 0) {

        return true

      }

      return false

    }

    set(key, val) { // 设置key的映射目标为val

      var keyIdx = this._keys.indexOf(key)

      if (keyIdx >= 0) {

        this._vals[keyIdx] = val

      } else {

        this._keys.push(key)

        this._vals.push(val)

      }

      return this

    }

    delete(key) { // 删除key的映射对

      var keyIdx = this._keys.indexOf(key)

      if (keyIdx >= 0) {

        this._keys.splice(keyIdx, 1)

        this._vals.splice(keyIdx, 1)

        return true

      }

      return false

    }

    clear() { // 清空所有的映射

      this._keys = []

      this._vals = []

    }

    // size() { // 返回当前Map中映射对的数量

    //   return this._keys.length

    // }

  }

  class Map3 {

    #keys = [] // private class field

    #vals = [] // private class field

    constructor() {

    }

    get(key) {

      var keyIdx = this.#keys.indexOf(key)

      if (keyIdx >= 0) {

        return this.#vals[keyIdx]

      }

    }

    has(key) { // 判断映射中是否存在某个key的映射

      var keyIdx = this.#keys.indexOf(key)

      if (keyIdx >= 0) {

        return true

      }

      return false

    }

    set(key, val) { // 设置key的映射目标为val

      var keyIdx = this.#keys.indexOf(key)

      if (keyIdx >= 0) {

        this.#vals[keyIdx] = val

      } else {

        this.#keys.push(key)

        this.#vals.push(val)

      }

      return this

    }

    delete(key) { // 删除key的映射对

      var keyIdx = this.#keys.indexOf(key)

      if (keyIdx >= 0) {

        this.#keys.splice(keyIdx, 1)

        this.#vals.splice(keyIdx, 1)

        return true

      }

      return false

    }

    clear() { // 清空所有的映射

      this.#keys = []

      this.#vals = []

    }

    size() { // 返回当前Map中映射对的数量

      return this.#keys.length

    }

  }  

  class Stack {

    #size = 0

    #top = null // 用于存储栈内元素的链表的头结点，由于头结点是栈顶，所以起名top

```



```
// 将元素val放入栈顶
push(val) {
  var node = {
    val: val,
    next: this.#top,
  }

  this.#top = node
  this.#size++

  return this
}
// 返回栈顶元素并将其出栈
pop() {
  if (this.#top) {
    var result = this.#top.val
    this.#top = this.#top.next
    this.#size--
    return result
  }
}
// 查看栈顶元素的值，但不让它出栈
peek() {
  if (this.#top) {
    return this.#top.val
  }
}
size() {
  return this.#size
}
```

  }

  // 使用链表实现队列的抽象数据结构
  class Queue {
    constructor() {

```
}

// 进队
enqueue(val) {

}
// 出队，将队头元素返回并从队列里删除
dequeue() {

}
// 查看队头元素的值
peek() {

}
size() {

}
```

  }

  // 表示一个集合：不重复的无序元素组成东西。
  class Group {
    constructor() {

```
}
// 为集合中添加一个元素
add(val) {

  return this
}
// 返回集合中是否有val这个元素
has(val) {

}
// 从集合中删除val元素，返回是否删除成功
delete(val) {

}
size() {

}
```

  }

  // 二维向量
  class Vector {
    constructor(x, y) {

```
}
// 用当前向量加上一个向量v，返回新的结果向量
plus(v) {

}
// 用当前向量减去一个向量v，返回新的结果向量
minus(v) {

}

length() {

}
```

  }

  // 实现复数及其四则运算
  class Complex {
    constructor(real, imag) {

```
}
plus(c) {

}
minus(c) {

}
mul(c) {

}
divide(c) {

}

// 以 (3+2j) 的形式返回复数的字符串形式
toString() {

}
```

  }

  var c1 = new Complex(2, 3)
  var c2 = new Complex(5, -1)
  var c3 = c1.mul(c2)

</script>