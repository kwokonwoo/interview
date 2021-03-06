### 写一个`difference`方法：  
- 用于比较两个数组，返回两数组中不同的部分  
- 能实现多维数组的比较，能使用ES6的一些新特性来实现

```javascript
// 遍历两个数组，找出在另一个数组中不存在的元素push到结果数组中。
function diff(arr1, arr2) {
  var result = [];
  
  for (var i = 0; i < arr1.length; i++) {
    if (arr2.indexOf(arr1[i]) === -1) {
      result.push(arr[i]);
    }
  }
  
  for (var j = 0; j < arr2.length; j++) {
    if (arr1.indexOf(arr2[j] === -1) {
      result.push(arr2[j]);
    }
  }
  
  return result;
}
```

```javascript
function diff(arr1, arr2) {
  return arr1.filter(e => arr2.indexOf(e) === -1).concat(arr2.filter(e => arr1.indexOf(e) === -1));
}
```

```javascript
// ES7 includes
function diff(arr1, arr2) {
  // 先合并，再filter
  // includes解决了利用indexOf会对数组中的NaN返回-1的问题
  return arr1.concat(arr2).filter(e => !arr1.includes(e) || !arr2.includes(e));
}
```

#### 参考链接

 [Array.prototype.includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)  
 
 [比较两数组差异(Diff Two Arrays)](https://singsing.io/blog/fcc/intermediate-diff-two-arrays/)  
 
 [在 JavaScript 中，如何求出两个数组的交集和差集？](https://www.zhihu.com/question/19863166)
