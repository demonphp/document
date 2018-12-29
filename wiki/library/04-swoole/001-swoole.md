### 官网地址swoole
https://wiki.swoole.com/wiki/page/6.html

### 源码安装
```shell
wget https://github.com/nghttp2/nghttp2/releases/download/v1.30.0/nghttp2-1.30.0.tar.bz2 tar -jxvf nghttp2-1.30.0.tar.bz2 cd nghttp2-1.30.0 ./configure make && make install

wget https://codeload.github.com/swoole/swoole-src/tar.gz/v4.2.11
tar -zxvf v4.2.11
mv swoole-src* swoole-src
cd swoole-src && phpize && ./configure --with-php-config=/usr/local/php/bin/php-config
 --enable-coroutine
 --enable-openssl  
 --enable-http2  
 --enable-async-redis
 --enable-sockets
 --enable-mysqlnd
 && make clean && make && sudo make install
```

### 直接安装
```shell
pecl install swoole
```

### tcp协议,tcp.php
```php
//创建Server对象，监听 127.0.0.1:9501端口
$serv = new swoole_server("127.0.0.1", 9501);
//监听连接进入事件
$serv->on('connect', function ($serv, $fd) {  
    echo "Client: Connect.\n";
});
//监听数据接收事件
$serv->on('receive', function ($serv, $fd, $from_id, $data) {
    $serv->send($fd, "Server: ".$data);
});
//监听连接关闭事件
$serv->on('close', function ($serv, $fd) {
    echo "Client: Close.\n";
});
//启动服务器
$serv->start();
```

### 启动
```shell
php tcp.php
```

### 测试
```shell
telnet 127.0.0.1 9501
hello
Server: hello
```

### 检查端口
netstat -an | grep 端口
