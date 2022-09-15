# HTTPHeaderService - HTTP Header管理服务 service\_http\_header.proto

#### 方法列表

* createHTTPHeader - 创建Header
* updateHTTPHeader - 修改Header
* findEnabledHTTPHeaderConfig - 查找配置

| 创建Header adminuserRPC createHTTPHeader _(CreateHTTPHeaderRequest)_ returns _(CreateHTTPHeaderResponse)_HTTP POST /HTTPHeaderService/createHTTPHeader                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateHTTPHeaderRequest：**_                                                                                                                                                                                                                                                                |
| <pre><code>message CreateHTTPHeaderRequest {
	string name = 1;
	string value = 2;
	repeated int32 status = 3;
	bool disableRedirect = 4;
	bool shouldAppend = 5;
	bool shouldReplace = 6;
	bytes replaceValuesJSON = 7;
	repeated string methods = 8;
	repeated string domains = 9;
}</code></pre> |
| _**输出对象：CreateHTTPHeaderResponse：**_                                                                                                                                                                                                                                                               |
| <pre><code>message CreateHTTPHeaderResponse {
	int64 headerId = 1;
}</code></pre>                                                                                                                                                                                                                  |

| 修改Header adminuserRPC updateHTTPHeader _(UpdateHTTPHeaderRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPHeaderService/updateHTTPHeader                                                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：UpdateHTTPHeaderRequest：**_                                                                                                                                                                                                                                                                                      |
| <pre><code>message UpdateHTTPHeaderRequest {
	int64 headerId = 1;
	string name = 2;
	string value = 3;
	repeated int32 status = 4;
	bool disableRedirect = 5;
	bool shouldAppend = 6;
	bool shouldReplace = 7;
	bytes replaceValuesJSON = 8;
	repeated string methods = 9;
	repeated string domains = 10;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                                                   |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                                          |

| 查找配置 adminuserRPC findEnabledHTTPHeaderConfig _(FindEnabledHTTPHeaderConfigRequest)_ returns _(FindEnabledHTTPHeaderConfigResponse)_HTTP POST /HTTPHeaderService/findEnabledHTTPHeaderConfig |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledHTTPHeaderConfigRequest：**_                                                                                                                                               |
| <pre><code>message FindEnabledHTTPHeaderConfigRequest {
	int64 headerId = 1;
}</code></pre>                                                                                                  |
| _**输出对象：FindEnabledHTTPHeaderConfigResponse：**_                                                                                                                                              |
| <pre><code>message FindEnabledHTTPHeaderConfigResponse {
	bytes headerJSON = 1;
}</code></pre>                                                                                               |

\
