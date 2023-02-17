## uniApp汇总

项目目录

![image-20220628151842043](Z:\Users\blog\book\assets\image-20220628151842043.png)

### uni-cli + Vant Weapp

```javascript
uni-cli创建项目 + Vant Weapp 配置
1、创建项目：vue create -p dcloudio/uni-preset-vue my-project
2、src目录下面新增wxcomponents文件夹；
3、Github => 搜索vant-weapp => clone下来将dist文件复制到wxcomponents目录下并把dist修改成vant名称；
4、src文件夹内 => manifest.json => mp-weixin => setting 添加"packNpmManually": true // 手动打包npm
5、pages.json => globalStyle下新增如下：
"globalStyle": {
	"navigationBarTextStyle": "black",
	"navigationBarTitleText": "uni-app",
	"navigationBarBackgroundColor": "#F8F8F8",
	"backgroundColor": "#F8F8F8",
++	"usingComponents": {
++		"van-button": "./wxcomponents/vant/button/index"
++	}
}

```

### uni-cli + uni-ui

```javascript
1、安装npm i sass -D
2、npm i sass-loader 或 npm i sass-loader@10.1.1 -D
注意：如果 node 版本小于 16 ，sass-loader 请使用低于 @11.0.0 的版本，sass-loader@11.0.0 不支持 vue@2.6.12  (opens new window) 如果 node 版本大于 16 ， sass-loader 建议使用 v8.x 版本
3、npm i @dcloudio/uni-ui
4、打开项目根目录下的 pages.json 并添加 easycom 节点：
例：// pages.json
{
++	"easycom": {
++		"autoscan": true,
++		"custom": {
			// uni-ui 规则如下配置
++			"^uni-(.*)": "@dcloudio/uni-ui/lib/uni-$1/uni-$1.vue"
++		}
++	},
	
	// 其他内容
	pages:[
		// ...
	]
}
```

