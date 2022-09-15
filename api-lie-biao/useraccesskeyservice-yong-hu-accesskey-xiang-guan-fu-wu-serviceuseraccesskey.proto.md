# UserAccessKeyService - 用户AccessKey相关服务 service\_user\_access\_key.proto

#### 方法列表

* createUserAccessKey - 创建AccessKey
* findAllEnabledUserAccessKeys - 查找所有的AccessKey
* deleteUserAccessKey - 删除AccessKey
* updateUserAccessKeyIsOn - 设置是否启用AccessKey
* countAllEnabledUserAccessKeys - 计算AccessKey数量

| 创建AccessKey adminuserRPC createUserAccessKey _(CreateUserAccessKeyRequest)_ returns _(CreateUserAccessKeyResponse)_HTTP POST /UserAccessKeyService/createUserAccessKey |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateUserAccessKeyRequest：**_                                                                                                                                 |
| <pre><code>message CreateUserAccessKeyRequest {
	int64 userId = 1;
	int64 adminId = 3;
	string description = 2;
}</code></pre>                                         |
| _**输出对象：CreateUserAccessKeyResponse：**_                                                                                                                                |
| <pre><code>message CreateUserAccessKeyResponse {
	int64 userAccessKeyId = 1;
}</code></pre>                                                                            |

| 查找所有的AccessKey adminuserRPC findAllEnabledUserAccessKeys _(FindAllEnabledUserAccessKeysRequest)_ returns _(FindAllEnabledUserAccessKeysResponse)_HTTP POST /UserAccessKeyService/findAllEnabledUserAccessKeys |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindAllEnabledUserAccessKeysRequest：**_                                                                                                                                                               |
| <pre><code>message FindAllEnabledUserAccessKeysRequest {
	int64 userId = 1;
	int64 adminId = 2;
}</code></pre>                                                                                                |
| _**输出对象：FindAllEnabledUserAccessKeysResponse：**_                                                                                                                                                              |
| <pre><code>message FindAllEnabledUserAccessKeysResponse {
	repeated UserAccessKey userAccessKeys = 1;
}</code></pre>                                                                                          |

| 删除AccessKey adminuserRPC deleteUserAccessKey _(DeleteUserAccessKeyRequest)_ returns _(RPCSuccess)_HTTP POST /UserAccessKeyService/deleteUserAccessKey |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteUserAccessKeyRequest：**_                                                                                                                |
| <pre><code>message DeleteUserAccessKeyRequest {
	int64 userAccessKeyId = 1;
}</code></pre>                                                            |
| _**输出对象：RPCSuccess：**_                                                                                                                                |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                       |

| 设置是否启用AccessKey adminuserRPC updateUserAccessKeyIsOn _(UpdateUserAccessKeyIsOnRequest)_ returns _(RPCSuccess)_HTTP POST /UserAccessKeyService/updateUserAccessKeyIsOn |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateUserAccessKeyIsOnRequest：**_                                                                                                                            |
| <pre><code>message UpdateUserAccessKeyIsOnRequest {
	int64 userAccessKeyId = 1;
	bool isOn = 2;
}</code></pre>                                                        |
| _**输出对象：RPCSuccess：**_                                                                                                                                                |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                       |

| 计算AccessKey数量 adminuserRPC countAllEnabledUserAccessKeys _(CountAllEnabledUserAccessKeysRequest)_ returns _(RPCCountResponse)_HTTP POST /UserAccessKeyService/countAllEnabledUserAccessKeys |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllEnabledUserAccessKeysRequest：**_                                                                                                                                            |
| <pre><code>message CountAllEnabledUserAccessKeysRequest {
	int64 adminId = 1;
	int64 userId = 2;
}</code></pre>                                                                             |
| _**输出对象：RPCCountResponse：**_                                                                                                                                                                |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                                                      |

\
