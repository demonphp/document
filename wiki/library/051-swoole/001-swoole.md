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

### 相关框架
https://doc.swoft.org/master/zh-CN/quickstart/env-config.html
