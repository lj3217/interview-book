# InterviewSummary

## vue2生命周期

```javascript
// 选项式API
beforeCreat	实例创建前：data和el都未初始化。
created	   实例创建后：data初始化完成，第一次访问到data、methods等数据，el还未初始化。
beforeMount	页面渲染前：data和el都已经初始化，但还是虚拟DOM。
mounted	   页面渲染后：页面渲染已完成，DOM是最新的。
beforeUpdate 数据更新前：data更新时触发，data中的数据已完成更新，但页面还未更新。
updated		数据更新后：页面完成数据更新。
beforeDestroy 实例销毁前：data和methods，指令、过滤器等都处于可用状态，还没有真正被销毁。
destroyed    实例销毁后：data和methods，指令、过滤器等处于不可用状态，组件已经被销毁。
```

## vuex五个属性

```javascript
state：数据源，主要存储数据；
getters：按需取出数据源中的数据；
mutations：主要是改变state数据中的状态，不支持异步操作；
actions： actions和mutations不同的是，actions支持异步和同步的操作；
modules：主要是模块化，也就是每一个模块都有自己的state、getters、mutations、actions；
```

### vue中的data为什么是个函数

```javascript
因为当data是函数时，组件实例化的时候这个函数会被调用，返回一个对象，计算机会给这个对象分配一个内存地址，实例化几次就分配几个内存地址，它们的地址都不一样，所以每个组件中的数据互不影响；
```

## HTTP和HTTPS

```javascript
HTTP协议传输的数据都是未加密的，也就是明文传输，因此HTTP协议不适合传输一些敏感信息，比如信用卡、密码等支付信息；
为了解决这一缺陷，HTTPS在HTTP的基础上加入了SSL协议，SSL依靠证书来验证服务器的身份，并且为浏览器和服务器之间的通信加密。
```

## 闭包

```javascript
闭包就是能够读取其他函数内部变量的函数;
优点：
	1、可以读取其他函数的内部变量；
	2、可以将变量始终保存在内存中；
 	3、可以封装对象的私有属性和方法；
缺点：消耗内存、使用不当会造成内存溢出问题；
```

## var let const 区别

```javascript
相同点：var、let、const都可以声明变量；
不同点：
	1、var存在变量提升 而let、const不存在变量提升；
	2、var定义的变量可以声明多次，而let、const定义的变量只能声明一次；
	3、var、let声明的变量可以再次赋值，而const不能再次赋值；
	4、var没有块级作用域，而ler、const有块级作用域；
```

## H5新增语义化标签

```javascript
// article --- 内容标签
// section --- 块级标签
// aside --- 侧边栏标签
1、nav、header、footer、article、section、aside等；
```

## 什么是原型链

```javascript
原型链：就是实例对象和原型对象之间的链接,每一个对象都有原型,原型本身又是对象,所以原型又有原型,以此类推形成一个链式结构；
所以当一个对象在查找一个属性的时候，自身没有就会根据_proto _向它的原型进行查找，如果都没有，则向它的原型的原型继续查找，直到查到Object.prototype.proto_为null，这样也就形成了原型链；
```

## 跨域

```javascript
跨域：主要是由浏览器的同源策略造成的，同源也就是域名、协议、端口相同；
解决方案：
	1、使用JSONP请求方式，JSONP仅支持GET请求；
	2、跨域资源共享，服务端设置允许跨域即可，如果带cookie请求，前后端都需要设置；
	3、目前主流解决方式是：nginx代理跨域；
```

