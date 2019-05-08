## 不一样的html

#### 什么是同源？
1. 协议相同

2. 域名相同

3. 端口相同

`浏览器不同的域名不能访问相对应的cookie，但是内部表单不限制`

#### 如何设置同源策略 （hosts）
test1.abc.com 共享 test2.abc.com里面的cookie，  
如果想让test2 共享 test1里面的cookie 需要设置`document.domain = 'abc.com'`

例如：

```
  /*test1.abc.com*/
  <script>
    document.domain = 'abc.com';
    document.cookie = 'callback=test';
  </script>

  /*test2.abc.com*/
  <script>
    console.log(document.cookie);
  </script>

```

#### 如何突破同源策略
1. html标签 img， iframe
2. script<jsonp>
3. css样式 background, border-img ...
  
#### 同源策略限制的对象（跨域）
1. cookie, localStorage和indexDB无法读取
2. DOM 无法获得
3. aJax请求不能发送

