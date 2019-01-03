### http请求
```code
http请求分为四个部分
请求行：包含三个内容
请求方式：GET/POST
URI：要请求的文件路径
协议版本：HTTP/1.1
请求头：请求头就是一项一项的规范（协议的真正内容），一个内容占一行
host：所请求的主机地址
accept-encoding：可以接受 的数据的编码，是什么流文件（文件内容）
referer：引用，指从哪个界面过来的（跳转过来）
connection：连接，在本次请求的过程中，直到服务器把数据全部交还给浏览器，两者之间一直保持连接状态
accept-language：可以接收的语言
cookie：浏览器携带提供给服务器的cookie数据（保存在浏览器cookie中的数据）
user-agent：浏览器信息
accept：浏览器可以接收服务器返回的数据类型
content-length（post）：浏览器提交给服务器的数据的长度
if-modified-since（get）：表示浏览器当前已经访问过某个界面，而进行再次访问，该时间是上次请求缓存文件的时间
content-type（post）：提交的文件的类型
空行：空行，用来区分请求头和请求主体
请求主体：只有post提交数据的时候才会有信息
```

### HTTP响应
```code
HTTP响应也包含四个部分
响应行
协议版本：HTTP/1.1
状态码：200
状态描述：对状态码的说明
响应头：与请求头相似，用来规范数据（数据说明）
server：服务器信息
date：响应的时间
last-modified：文件最后被修改的时间
content-length：响应主体的数据长度
content-type：响应主体的数据类型
location：重定向，立即重定向
refresh：刷新，指定时间后重定向
content-encodeing：数据内容的编码
cache-control：缓存控制，no-cache表示告诉浏览器不要缓存当前请求的界面
空行：用来区分响应头和响应主体
响应主体：具体的响应数据
```

### 响应状态码
```code
1XX：服务器接收请求，继续处理
2XX：成功处理
200：成功处理
3XX：重定向
302：请求文件已经重定向
4XX：请求错误
403：forbidden，请求了一个不该请求的东西
404：not found，找不到文件
5XX：响应错误
502：gateway，服务器向上级请求时，上级返回失败
```
