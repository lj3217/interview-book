Nginx 接口反向代理

```javascript
location ^~ /api/{
	rewrite /api/(\d+)/(.+) /$2?$args break;
	proxy_pass https://www.ibex.com.cn:8010;
}
```
