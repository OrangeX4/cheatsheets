---
title: javascript
categories: language
---

## get started

### React Query

```js
function getQuery(search) {
  const result = {}
  if (search.length > 1) {
      const query = search.substring(1)
      const vars = query.split("&")
      for (let i = 0; i < vars.length; i++) {
          let pair = vars[i].split("=")
          if (pair.length === 2) {
            result[pair[0]] = pair[1]
          }
      }
  }
  return result
}
const search = window.location.search
const query = getQuery(search)
```

### Download File

```js
function downloadFile(filename, text) {
    const elementA = document.createElement('a')

    // 文件的名称为时间戳加文件名后缀
    elementA.download = filename
    elementA.style.display = 'none'

    // 生成一个blob二进制数据，内容为文本数据
    const blob = new Blob([text])

    //生成一个指向blob的URL地址，并赋值给a标签的href属性
    elementA.href = URL.createObjectURL(blob)
    document.body.appendChild(elementA)
    elementA.click()
    document.body.removeChild(elementA)
}
```
