## 异步redis

### 安装扩展
yum install libhiredis-devel

### 代码片段
```php
echo "process-start-time".date('Y-m-d H:i:s').PHP_EOL;
$urls = [
    'http://baidu.com',
    'http://xinlang.com',
    'http://qq.com',
    'http://baidu.com?search=test1',
    'http://baidu.com?search=test2',
    'http://baidu.com?search=test3',
];

//原始写法
//foreach($urls as $v) {
//    $content = file_get_contents($v);
//}

//新的写法
for($i=0;$i<6;$i++) {
    $process = new swoole_process(function (swoole_process $process) use($urls,$i) {
        $content = curlData($urls[$i]);
        echo $content.PHP_EOL;
    }, true);
    $pid = $process->start();
    $workers[$pid] = $process;
}

foreach($workers as $process) {
    echo $process->read();
}

function curlData($url) {
    sleep(1);
    return $url.'success'.PHP_EOL;
}

echo "process-start-end".date('Y-m-d H:i:s').PHP_EOL;
```
