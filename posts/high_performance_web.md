# 《高性能web网站》笔记

## 尽可能少的HTTP Request
- 使用css spirte
- 使用[data:url scheme](https://en.wikipedia.org/wiki/Data_URI_scheme)
- 合并JavaScript、css文件

## 使用[CDN](http://baike.baidu.com/link?url=hgs85G_qCysyL77W3gsiXazJG5EAc9Mg3Z0BQTjEO9q08NIhHKZNokEny_B5kkzliCqGz2peCPavzKAhsgrxGq)

## 增加Expires Header
- 设置一个长时间的expire HTTP header
```
eg:
Expires: Sat,19 Jan 2099 00:00:00 GMT

```

- 设置一个Cache-Control Header
- 当资源发生变化的时候，改变URL地址，这样不用客户清掉缓存

## 启用Gzip或deflate压缩
- 对HTML、JavaScript、css进行压缩
- 开启Apache的mod_gzip,mod_deflate

## 把css文件置于头部head标签里

## 避免用css表达式

## 使用外部css,js文件(这样可以对css,js文件进行缓存)

## 减少DNS Lookups
- 设置Connection:Keep-alive
- 减少域名数量

## 压缩js

## 避免重定向

## 减少重复的脚本

## 配置ETags

## 使Ajax可以缓存