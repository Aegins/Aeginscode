# API调用

### 调用方法 <a href="#tiao-yong-fang-fa" id="tiao-yong-fang-fa"></a>

除了 `/APIAccessTokenService/getAPIAccessToken` 接口外，其他的所有接口都需要：

1. 在HTTP Header中传递`X-Edge-Access-Token`令牌数据，以便于我们认证用户是否有接口访问的权限，此令牌通过 `/APIAccessTokenService/getAPIAccessToken` 接口获取，具体请参考 [认证](https://goedge.cn/docs/API/Auth.md) 一节。
2. 所有请求数据需要以 `POST` 方法上传一个完整的JSON数据，接口响应数据也是JSON数据

比如：

```
POST /HTTPAccessLogService/ListHTTPAccessLogs...X-Edge-Access-Token: n8adDybtPCAGdbORkXjfpJgL28EGkOLz...​{    "serverId": 23,    "day": "20210101",    "size": 100,    "reverse": true}
```

可以在[这里](https://goedge.cn/docs/API/Auth.md)查看令牌获取方法。

### CURL示例 <a href="#curl-shi-li" id="curl-shi-li"></a>



```bash
curl -XPOST -H"X-Edge-Access-Token: hZFW3yg1geeKYqLPjhmi5OyAtYoKingiNoemNkqjLWIsCXJcmaHDaUL1ELX6vtPrjvwiXiTuBN9mAVK8cUhn6PpuN1eLYbtN1seAFMpf2h6aZtFgkhAxI3cYUSZIwLQg"  "http://192.168.1.6:8004/HTTPAccessLogService/ListHTTPAccessLogs" -d '{  "size":100,   "day":"20211217"}'
```

你需要把IP地址、X-Edge-Access-Token换成你自己的

