## vue方法

### vue方法使用图片

```javascript
data: {
    img: require('@/assets/bg.jpg')
}
```

### ref删除节点

```javascript
<div ref="refStartPoint"></div>
this.$refs.refStartPoint.remove()
```

### ref添加样式

```javascript
// 单个添加样式
this.$refs.test.style.width = "200px"
// 批量操作样式
this.$refs.test.style.cssText = "padding-top: 12px; padding-top: 12px; ....."
```

### ref获取标签高度

```javascript
this.$refs.refHeader.offsetHeight
```

### 删除URL拼接的参数

```javascript
delete obj.id
例：
const params = {
        id: "1"
      }
delete params.id
```

## 组件

### 上传压缩图片

````javascript
// 安装
npm i image-conversion

// 引入
import * as imageConversion from 'image-conversion';
````

### screenfull 实现全屏

```javascript
// 安装
npm install screenfull
// 按需引入
import screenfull from 'screenfull';

// 使用 => 拿到这个元素，让这个元素全屏
screenfull.request(this.$refs.test.$el)
// 退出全屏
screenfull.exit()
```

### AES算法加密

```javascript
使用算法库：crypto-js

安装：npm install crypto-js

引入：import CryptoJS from 'crypto-js'

const key = CryptoJS.enc.Hex.parse("ibexibex65819988") // 十六位十六进制数作为密钥
mode：表示加密类型；
padding：表示结果是否自动补齐（zero：自动补齐）
// 加密方法
Encrypt (word) {
  let srcs = CryptoJS.enc.Utf8.parse(word)
  let encrypted = CryptoJS.AES.encrypt(srcs, key, { mode: CryptoJS.mode.ECB, padding: CryptoJS.pad.ZeroPadding })
  return encrypted.ciphertext.toString().toUpperCase() //显示结果为 Hex类型编码：D7071AF38B54D3D6C0B2DB0139EBB7B2
  // return encrypted.toString() // 显示结果为 Base64； 打印结果：1wca84tU09bAstsBOeu3sg==
}
this.Encrypt('世纪东方')


// 解密方法
Decrypt (word) {
  let encryptedHexStr = CryptoJS.enc.Hex.parse(word); // Hex 表示数据类型
  let srcs = CryptoJS.enc.Base64.stringify(encryptedHexStr);
  let decrypt = CryptoJS.AES.decrypt(srcs, key, { mode: CryptoJS.mode.ECB, padding: CryptoJS.pad.ZeroPadding });
  let decryptedStr = decrypt.toString(CryptoJS.enc.Utf8);
  return decryptedStr.toString();
}
this.Decrypt('1wca84tU09bAstsBOeu3sg==') // 数据类型为：base64
this.Decrypt('D7071AF38B54D3D6C0B2DB0139EBB7B2') // 数据类型为：Hex
```

