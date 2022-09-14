# 认证

在调用API时，需要通过令牌（AccessToken）对用户权限进行认证。

### 步骤1：创建AccessKey <a href="#bu-zhou-1-chuang-jian-accesskey" id="bu-zhou-1-chuang-jian-accesskey"></a>



用户AccessKey

在用户平台”访问控制”页面中点击”创建AccessKey”，然后创建一个AccessKey。



### 步骤2：调用API获取AccessToken <a href="#bu-zhou-2-tiao-yong-api-huo-qu-accesstoken" id="bu-zhou-2-tiao-yong-api-huo-qu-accesstoken"></a>

#### 接口地址 <a href="#jie-kou-di-zhi" id="jie-kou-di-zhi"></a>

```
/APIAccessTokenService/getAPIAccessToken
```

#### 请求方法 <a href="#qing-qiu-fang-fa" id="qing-qiu-fang-fa"></a>

POST。

#### 请求参数 <a href="#qing-qiu-can-shu" id="qing-qiu-can-shu"></a>

```json
{    "type": "admin",    "accessKeyId": "zr9cmR42AEZxRyIV",    "accessKey": "2w5p5NSZZuplUPsfPMzM7dFmTrI7xyja"}
```

其中

* `type` - 如果是用户（即平台用户）AccessKey，则值为 `user`；如果是管理员（即系统用户）AccessKey，则值为 `admin`；
* `accessKeyId` 和 `accessKey` 换成你在步骤1中创建的AccessKey对应的数据。

#### 响应结果 <a href="#xiang-ying-jie-guo" id="xiang-ying-jie-guo"></a>

```json
{   "code": 200,   "data": {      "token": "IKNSMufZ1vDiXp5rSd9QR01m1174Oum5sah4amWFgbRb7lOKjuk62Spl7hgcazctzGhGG7jPgfmYUPojulC0FK5cLbrj8n7kxW7BtSawH9gWW14IWOzBY6UcpyXQndFu",      "expiresAt": 1609686945   },   "message": "ok"}
```

其中：

* `code` - 如果是 `200` 表示成功，否则表示失败
* `token` - 就是AccessToken，可以在别的接口中通过HTTP Header `X-Edge-Access-Token` 传入；
* `expiresAt` - 过期时间戳，默认为N个小时，过期后请及时重新获取。

多次调用此接口会导致先前获取的AccessToken失效。

#### CURL示例 <a href="#curl-shi-li" id="curl-shi-li"></a>

对管理员来说，可以使用curl命令调用接口获得Token：

```bash
curl -XPOST "http://192.168.1.6:8004/APIAccessTokenService/getAPIAccessToken" -d '{   "type":"admin",   "accessKeyId":"zr9cmR42AEZxRyIV",    "accessKey":"2w5p5NSZZuplUPsfPMzM7dFmTrI7xyja"}'
```

你需要把API地址、accessKeyId、accessKey换成你自己的。

对平台用户来说，可以使用curl命令调用接口获得Token：

```bash
curl -XPOST "http://192.168.1.6:8004/APIAccessTokenService/getAPIAccessToken" -d '{   "type":"user",   "accessKeyId":"JOvsyXIFqkQbh5kl",    "accessKey":"t0RY8YO3R58VbJJNp0RqKw9KWNpObwtE"}'
```

你需要把API地址、accessKeyId、accessKey换成你自己的。

### 步骤3：调用API <a href="#bu-zhou-3-tiao-yong-api" id="bu-zhou-3-tiao-yong-api"></a>

在 [API列表](https://goedge.cn/docs/API/List.md) 找到要调用的API，然后以POST方式调用 `/服务/方法` 组合后的URL，在Header中加入 `X-Edge-Access-Token` ，值为步骤2中的生成的AccessToken接口，具体可以参考 [API调用概述](https://goedge.cn/docs/API/Summary.md) 。
