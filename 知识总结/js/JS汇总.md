## JS浏览器

### localStorage

储存数据

```javascript
window.localStorage.setItem('username', username)
```

获取数据

```javascript
window.localStorage.getItem('username')

转化为json对象
JSON.parse(window.localStorage.getItem('username'))
```
### cookie

获取数据

```javascript
getCookie (name) {
  const strcookie = document.cookie
  const arrcookie = strcookie.split('; ')
  for (let i = 0; i < arrcookie.length; i++) {
    var arr = arrcookie[i].split('=')
    if (arr[0] === name) {
      return arr[1]
    }
  }
  return ''
}

使用：this.getCookie('name名')
例：this.getCookie('admin-token')
```


### 禁用F12调试网页

```javascript
document.onkeydown = function () {
  var e = window.event || arguments[0]
  if (e.keyCode === 123) {
    alert("F12被禁用")
    return false
  }
}
```

### 禁用右键调试网页

```javascript
document.oncontextmenu = function () {
  alert('右键被禁用')
  return false
}
```

### 禁用ctrl+s保存

```javascript
document.onkeydown = function (e) {
  if (e.ctrlKey && e.keyCode === 83) {
    alert("ctrl+s被禁用")
    return false
  }
}
```


### HTTP和HTTPS

```javascript
HTTP协议传输的数据都是未加密的，也就是明文传输，因此HTTP协议不适合传输一些敏感信息，比如信用卡、密码等支付信息；
为了解决这一缺陷，HTTPS在HTTP的基础上加入了SSL协议，SSL依靠证书来验证服务器的身份，并为浏览器和服务器之间的通信加密并且。
```

## JS方法

### indexOf()

```javascript
// 返回某个指定的字符串值在字符串中首次出现的位置;
// 如果没有找到匹配的字符串则返回 -1;
// indexOf() 方法区分大小写;
const str = "Hello world, welcome to the universe.";
str.indexOf("welcome")
```

### map()

```javascript
// 返回 如果成立返回true，否则为false
例：this.jsonTableData.map(item => { item.equipment = this.formInformation.equipmentNumber + '000000' })
```

### forEach()

```javascript
// 返回 undefined
例：
this.jsonTableData.forEach(item => { return item.equipment === this.formInformation.equipmentNumber + '000000' })
```

### filter()

```javascript
// 返回 成立项
例：
this.jsonTableData.filter(item => { return item.equipment === this.formInformation.equipmentNumber + '000000' })
```

### 合并数组

```javascript
// 合并两个数组
var arr = [1, 2, 3]
var brr = [4, 5, 6]

// 方法1：
Array.prototype.push.apply(arr, brr)
console.log(arr);

// 方法2：
arr.push(brr)
console.log(arr);

// 方法3：
arr = [...arr, ...brr]
console.log(arr);
```

### 获取当前电脑时间

```javascript
getTime (ti) {
  const dateTime = new Date();
  dateTime.setDate(dateTime.getDate() + ti);
  const Year = dateTime.getFullYear();
  const Month = ((dateTime.getMonth() + 1) > 9 ? (dateTime.getMonth() + 1) : '0' + (dateTime.getMonth() + 1));
  const date = (dateTime.getDate() > 9 ? dateTime.getDate() : '0' + dateTime.getDate());
  const Hours = (dateTime.getHours() > 9 ? dateTime.getHours() : '0' + dateTime.getHours());
  const Minutes = (dateTime.getMinutes() > 9 ? dateTime.getMinutes() : '0' + dateTime.getMinutes());
  const Seconds = (dateTime.getSeconds() > 9 ? dateTime.getSeconds() : '0' + dateTime.getSeconds());
  const time = Year + '-' + Month + '-' + date + ' ' + Hours + ':' + Minutes + ':' + Seconds;
  return time;
}

getTime(0) // 获取当前时间
getTime(-7) // 获取当日前七天时间
getTime(7); // 获取当日后七天时间
```

### URL拼接参数格式 start[]："1"

```javascript
// 转成字符串
JSON.stringify()
例：
JSON.stringify(test)
```

### 去掉数组里面数据外面的引号

去掉数组里面数据外面的引号：例：arr = ["1,2,3,4,5,......"]

```javascript
var arr = ["1,2,3,4,5,......"]
JSON.parse(JSON.stringify(arr).replaceAll('"',''))
```

### 求数组中的最大值

```javascript
<!-- 求数组中的最大值 -->
<script>
  var nums = [45, 12, 46, 77, 35, 66, 55, 100]
  const maxNUM = Math.max.apply(Math, nums)
  console.log(maxNUM);
</script>
```



### 给每条数据增加参数

```javascript
// 说明 ↓
// item：每一项数据
// isAdd：加入的属性
// false：加入的值
Array.forEach(item => {
    item["isAdd"] = false
})
```

### 字符串转数组

```javascript
const testData = "123"
new Array(testData)
console.log(testData)
```

### 去掉数组外面双引号

```javascript
const arr = "[]"
JSON.parse(arr)
```

### 截取

```javascript
// substring(start, end)  
// 备注： start：起始位置从索引0开始；	end：从索引1开始数到最后； end也可以不加，则后面的全部
var arr = "12345678"
console.log(arr.substring(6, 7))
```

### 16转10进制

```javascript
// 两个参数
// 第一个参数：需要转换的字符串
// 第二个参数：这个字符串属于几进制
parseInt("5F86D386", 16)
```

### GB2312解析中文

````javascript
const movieLength = this.row.message_original.substring(72, this.row.message_original.length - 6)	
*/ movieLength 等于，相当于：77726F6E67（16进制）
const movieArray = []
for (let i = 0; i < movieLength.length / 2; i++) {
	movieArray.push('0x' + movieLength.substring(i * 2, (i * 2) + 2))
}

打印movieArray结果为：["0x77", "0x72", "0x6F", "0x6E", "0x67"]
通过第三方(iconv-lite)解析为汉字
````

### 字符串转化成数字

```javascript
parseFloat("1000.01") // 1000.01
```

### JSON字符串转js对象

```javascript
JSON.parse()
var str = '{"name":"huangxiaojian","age":"23"}'
JSON.parse(str)

结果：
age: "23"
name: "huangxiaojian"
```

### JS对象转JSON字符串（通常为对象或数组）

```javascript
JSON.stringify()
var str = { name: huangxiaojian, age: 23 }
JSON.stringify(str)

结果：'{"name":"huangxiaojian","age":"23"}'
```



### 获取滚动条高度

```javascript
// ref 获取DOM下一级元素 this.$refs.refSroll.children[0]
// 监听滚动条高度
mounted () {
   this.listenSrollHeight()
}
 methods: {
     listenSrollHeight () {
      this.$refs.refSroll.addEventListener('scroll', () => {
      		console.log(this.$refs.refSroll.scrollTop)
      }, true)
	  }
 }

二、
window.onscroll = function (e){
	var scrolltop=document.documentElement.scrollTop
}
```

### replace()

```javascript
replace()：用于替换字符串中的符号
例：
方法一、只修改第一次出现项
var arr = '2022-1-1 0:0:0'
console.log(arr.replace('-', '/'))
结果：2022/1-1 0:0:0

方法二、修改全部项
var arr = '2022-1-1 0:0:0'
console.log(arr.replace(/-/g, '/'))
结果 2022/1/1 0:0:0
```

### split()字符串分割

```javascript
split()方法：把一个字符串分割成字符串数组
例：
const url = http://localhost:8080/massesMobileTerminal/massesHome?player_number=M800yj0001
url.split("=")
结果为：
['http://localhost:8080/massesMobileTerminal/massesHome?player_number', 'M800yj0001']
```

### slice()截取字符串

```javascript
slice()：截取字符串
例：只要前三位数
const arr = "123456789"
arr.slice(开始下标，结束下标)
arr.slice(0, 3)

备注：不会修改原数组；
```

### splice()操作数组中元素

```javascript
splice()：方法用于添加或删除数组中的元素。
例：
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2,1,"Lemon","Kiwi");
输出结果：Banana,Orange,Lemon,Kiwi,Mango

备注：会改变原始数组。
```

### substring()截取字符串

```javascript
substring()：截取字符串
例：只要前三位数
const arr = "123456789"
arr.substring(开始下标，结束下标)
arr.substring(0, 3)
```

### v-viewer 图片查看器

```javascript
一、 按钮使用：
<Button type="primary" @click="enlargeImgBtn(index)">确定</Button>

例：数据：
imagesData: [
          "https://picsum.photos/200/200",
          "https://picsum.photos/300/200",
          "https://picsum.photos/250/200"
        ]
this.$viewerApi({ images: this.imagesData }) // 显示多个图片，默认显示第一个
this.$viewerApi({ images: this.imagesData }).view(index) // 显示多个图片，view(索引)，指定显示第几个

二、第二种使用方式
这种方式不需要点击其他按钮，点击图片即可，点击哪个图片就会显示哪个
<viewer :images="imagesData">
   <img v-for="item in imagesData" :key="item" :src="item">
 </viewer>
    
```

### 获取URL

```javascript
window.location.href // 可以拿到完整url路径
window.location.href.split('?') // 拿到完整url路径，以？为分隔，以数组形式展示出来，如下图：↓
```

![getUrl](Z:\Users\blog\book\assets\getUrl.png)

### dayjs

```javascript
main.js 全局引入
import dayjs from 'dayjs'
import duration from 'dayjs/plugin/duration' // 时长插件

时间差异处理例：
var x = dayjs('结束时间')
var y = dayjs('开始时间')

var duration = dayjs.duration(x.diff(y))
```

### UTF-8转中文

```javascript
第一种：UTF-8类型解码
const str = '%u7535%u5F71%u767E%u5E74'
console.log(unescape(str))

第二种：UTF-8解码
const str = '&#x7535;&#x5F71;&#x767E;&#x5E74;'
console.log(unescape(str.replace(/&#x/g, '%u').replace(/;/g, '')))

结果为：电影百年
```

### 秒转换为标椎时间

```javascript
// 秒转换为标椎时间
timeSeconds (s) {
  var day = Math.floor(s / (24 * 3600))
  var hour = Math.floor((s - day * 24 * 3600) / 3600)
  var minute = Math.floor((s - day * 24 * 3600 - hour * 3600) / 60)
  var second = s - day * 24 * 3600 - hour * 3600 - minute * 60
  return day + '天' + hour + '时' + minute + '分' + second + '秒'
}
```



