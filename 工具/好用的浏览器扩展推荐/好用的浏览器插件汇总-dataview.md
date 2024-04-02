---
date_created: 2024-03-31日 星期日 , 11:02:17 晚上
date_modified: 2024-03-31日 星期日 , 11:42:29 晚上
---


[[好用的浏览器扩展列表]]



```dataviewjs
let current = dv.current()
console.log(current)

let tableData = dv.pages('"工具/好用的浏览器扩展推荐/好用的浏览器扩展列表"')
  .sort(b => b.rating)
  .map(item => [item.file.link, item["类型"], item["描述"], item["特点"], item["评分"]])

dv.table(["名称", "类型", "描述", "特点", "评分"], tableData)




```
