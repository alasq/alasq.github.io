---
title: 图片base64转文件
date: 2021-09-26 07:17:28
tags: 代码片段
---
```js
/**
 * base64格式图片转二进制文件
 * @param {string} base64str 
 * @returns  
 */
function base64ToFile(base64str) {
  let mimeType=base64str.match(/:(.*?);/)[1];
  let base64=base64str.slice(base64str.indexOf(';')+1)
  let bstr=atob(base64),
  n=bstr.length,
  u8Arr=new Uint8Array(n);
  while(n--){
    u8Arr[n]=bstr.charCodeAt(n);
  }
  const file=new Blob([u8Arr],{type:mimeType})
  return file
}
```