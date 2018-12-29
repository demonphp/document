# 第三方校验token值

## 接口简介

## 接口详情

### 请求地址
http://qk.ouynix12.com/auth/checktoken

### 请求类型
POST

### 请求参数
| 参数名 | 类型 | 必填 | 描述 | 默认值 |
| --- | :---: | :---: | --- | --- |
| uid | string | 是 | uid | 34 |
| access_token | string | 是 | 登录后 | 394c83ff355420e52203b638c89ea5cc |


### 返回JSON示例
```javascript
{
    "message": "ok",
    "statusCode": 200,
    "data": {
        "partnerid": "xinyou",
        "user_id": "34"
    }
}
```

### 返回JSON示例
```javascript
{
    "message": "access_token值错误",
    "statusCode": 300
}
```

### 备注说明
app_ctype的值为own 的时候 app_uid 的值为own的用户uid
