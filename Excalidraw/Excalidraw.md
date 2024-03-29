# Excalidraw 

```dataviewjs
let current = dv.current()
let currentFolder = current.file.folder
console.log('current',current)
let arr = dv.pages(`"${currentFolder}"`)
let reg_head = /^_index_of_.*/
let outArr = arr
/*
因为点开文件夹能显示内容是Floder Note 插件的功能
当你新建了一个文件夹 用ctrl + click 点击会在 该点击文件夹里面建立一个新的与文件夹同名的md文件作为文件夹主页描述文件

过滤出文件夹层级相同 或者 比当前文件夹层级深一级的文件
*/
.filter (item => {

	let currentFolderDeep = currentFolder.split('/').length
	let itemFolderDeep = item.file.folder.split('/').length
	if(currentFolderDeep === itemFolderDeep ||
	currentFolderDeep + 1 === itemFolderDeep
	) return true
	else {
		return false
	}
})
/*
过滤出同一级文件夹中的文章以及下一级文件夹的主页描述文件
*/
.filter(item=>{
	let fileFolder = item.file.folder.split('/')
	let folderEnd = fileFolder[fileFolder.length - 1]
	return (
		item.file.folder===current.file.folder||
		folderEnd===item.file.name
	)
})
/*
去除—_index_of_开头的文件
*/
.filter(item => {
	return !reg_head.test(item.file.name)
})
/*
去除自身描述文件
*/
.filter(item => {
	console.log (item.file.path === current.file.path)
	return !(item.file.path === current.file.path)
})
.sort(p=>p.file.ctime,'asc').map(p=>p.file.link)
dv.list(outArr)

console.log(outArr.values)

```




```ccard
type: folder_brief_live
```
 

