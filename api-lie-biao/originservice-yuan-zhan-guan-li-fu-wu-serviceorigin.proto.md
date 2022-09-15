# OriginService - 源站管理服务 service\_origin.proto

#### 方法列表

* createOrigin - 创建源站
* updateOrigin - 修改源站
* findEnabledOrigin - 查找单个源站信息
* findEnabledOriginConfig - 查找源站配置

| 创建源站 adminuserRPC createOrigin _(CreateOriginRequest)_ returns _(CreateOriginResponse)_HTTP POST /OriginService/createOrigin                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateOriginRequest：**_                                                                                                                                                                                                                                                                                                                                                                      |
| <pre><code>message CreateOriginRequest {
	string name = 1;
	NetworkAddress addr = 2;
	string description = 3;
	int32 weight = 4;
	bool isOn = 5;
	bytes connTimeoutJSON = 6;
	bytes readTimeoutJSON = 7;
	bytes idleTimeoutJSON = 8;
	int32 maxConns = 9;
	int32 maxIdleConns = 10;
	repeated string domains = 11;
	bytes certRefJSON = 12;
	string host = 13;
	bool followPort = 14;
}</code></pre> |
| _**输出对象：CreateOriginResponse：**_                                                                                                                                                                                                                                                                                                                                                                     |
| <pre><code>message CreateOriginResponse {
	int64 originId = 1;
}</code></pre>                                                                                                                                                                                                                                                                                                                        |

| 修改源站 adminuserRPC updateOrigin _(UpdateOriginRequest)_ returns _(RPCSuccess)_HTTP POST /OriginService/updateOrigin                                                                                                                                                                                                                                                                                                         |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateOriginRequest：**_                                                                                                                                                                                                                                                                                                                                                                                            |
| <pre><code>message UpdateOriginRequest {
	int64 originId = 1;
	string name = 2;
	NetworkAddress addr = 3;
	string description = 4;
	int32 weight = 5;
	bool isOn = 6;
	bytes connTimeoutJSON = 7;
	bytes readTimeoutJSON = 8;
	bytes idleTimeoutJSON = 9;
	int32 maxConns = 10;
	int32 maxIdleConns = 11;
	repeated string domains = 12;
	bytes certRefJSON = 13;
	string host = 14;
	bool followPort = 15;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                                                                                                                                                     |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                                                                                                                                            |

| 查找单个源站信息 adminuserRPC findEnabledOrigin _(FindEnabledOriginRequest)_ returns _(FindEnabledOriginResponse)_HTTP POST /OriginService/findEnabledOrigin |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledOriginRequest：**_                                                                                                                 |
| <pre><code>message FindEnabledOriginRequest {
	int64 originId = 1;
}</code></pre>                                                                    |
| _**输出对象：FindEnabledOriginResponse：**_                                                                                                                |
| <pre><code>message FindEnabledOriginResponse {
	Origin Origin = 1;
}</code></pre>                                                                    |

| 查找源站配置 adminuserRPC findEnabledOriginConfig _(FindEnabledOriginConfigRequest)_ returns _(FindEnabledOriginConfigResponse)_HTTP POST /OriginService/findEnabledOriginConfig |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledOriginConfigRequest：**_                                                                                                                                 |
| <pre><code>message FindEnabledOriginConfigRequest {
	int64 originId = 1;
}</code></pre>                                                                                    |
| _**输出对象：FindEnabledOriginConfigResponse：**_                                                                                                                                |
| <pre><code>message FindEnabledOriginConfigResponse {
	bytes originJSON = 1;
}</code></pre>                                                                                 |

\
