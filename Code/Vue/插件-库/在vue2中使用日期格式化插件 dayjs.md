# 在vue中使用日期格式化插件 dayjs

day.js 是代替修改本地 Date.prototype，day.js 对 Date 对象进行了封装，只需要调用 dayjs() 即可。 相对 moment.js， day.js 的体积更小，只有 2KB 左右；moment.min.js 有 16.7KB。

对应普通项目来说，对应时间的操作就只有那么几个（格式化、查询、计算），这些基于day.js完全足够。并且day.js的文档相对简单、清晰！

## 使用

#### 下载dayjs

`npm install dayjs --save  or yarn add dayjs`

#### 创建untils/formate.js

js

复制代码

```js
import dayjs from 'dayjs' import rTime from 'dayjs/plugin/relativeTime' // 全局使用中文 
dayjs.locale('zh-cn') // 对时间进行格式化 
export function formatTime(data = new Date(), type = 'YYYY-MM-DD') {   return dayjs(data).format(type) } // 其它例如相对时间，需要单独配置它自己的插件才可以使用 
dayjs.extend(rTime) export const relativeTime = value => {   return dayjs().to(dayjs(value)) } export default {   formatTime,   relativeTime }
```

#### 挂在全局，封装过滤器，main.js


```js
import { formatTime, relativeTime } from './utils/formate' 
Vue.prototype.$formatTime = formatTime 
Vue.prototype.$relativeTime = relativeTime // 过滤器 
Vue.filter('relativeTime', relativeTime) 
Vue.filter('formatTime', formatTime)`
```
js环境使用

`this.$formatTime(new Date(),'YYYY-MM-DD')`

#### 在vue模板中使用过滤器


 `{{new Date()|formatTime}}  {{new Date('2022-01-01')|relativeTime}}`

### 所有可用单位列表：

|单位|缩写|描述|
|---|---|---|
|week|w|周|
|day|d|星期(星期日0，星期六6)|
|month|M|月份(0-11)|
|year|y|年|
|hour|h|小时|
|minute|m|分钟|
|second|s|秒|
|millisecond|ms|毫秒|

### 判断一个日期是否在两个日期之间 isBetween


`注意: 此功能依赖IsBetween插件 此处也将演示如何使用 Day.js 的插件`


```js
import dayjs from 'dayjs'	// 引入dayjs 
import isBetween from 'dayjs/plugin/isBetween'	// 引入相关插件 
created() {    
	dayjs.extend(isBetween); // 挂载插件    // 使用插件    
	console.log(dayjs('2010-10-20').isBetween('2010-10-19', dayjs('2010-10-25')) ) 
}
```

注意： `isAfter、isBefore、isSame、IsBetween` 默认都是通过将日期转为 milliseconds 去比较的，所以这两个方法有第二个参数。即指定比较的粒度



```js
console.log('isBefore', dayjs('2022-04-20').isBefore('2015-01-01', 'year'))
```

Day.js 里面有 相同于之前 IsSameOrBefore 和 相同或之后 IsSameOrAfter 的方法，可根据实际需求使用，但这两个方法需要依赖相应的插件！

更多详细用法请参阅 [dayjs中文官网](https://link.juejin.cn/?target=https%3A%2F%2Fdayjs.fenxianglu.cn%2F "https://dayjs.fenxianglu.cn/")~