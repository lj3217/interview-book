### 解决tomcat启动出现乱码

```javascript
1、找到目录：apache-tomcat-7.0.103\conf
2、打开logging.properties文件
3、找到java.util.logging.ConsoleHandler.encoding = UTF-8 // 在47行
4、修改为java.util.logging.ConsoleHandler.encoding = GBK
5、重启tomcat
```
