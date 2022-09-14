# ACMEUserService - ACME用户相关服务 service\_acme\_user.proto

#### 方法列表

* createACMEUser - 创建用户
* updateACMEUser - 修改用户
* deleteACMEUser - 删除用户
* countACMEUsers - 计算用户数量
* listACMEUsers - 列出单页用户
* findEnabledACMEUser - 查找单个用户
* findAllACMEUsers - 查找所有用户

| 创建用户 adminuserRPC createACMEUser _(CreateACMEUserRequest)_ returns _(CreateACMEUserResponse)_HTTP POST /ACMEUserService/createACMEUser                                |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateACMEUserRequest：**_                                                                                                                                     |
| <pre><code>message CreateACMEUserRequest {
	string email = 1;
	string description = 2;
	string acmeProviderCode = 3;
	int64 acmeProviderAccountId = 4;
}</code></pre> |
| _**输出对象：CreateACMEUserResponse：**_                                                                                                                                    |
| <pre><code>message CreateACMEUserResponse {
	int64 acmeUserId = 1;
}</code></pre>                                                                                     |

| 修改用户 adminuserRPC updateACMEUser _(UpdateACMEUserRequest)_ returns _(RPCSuccess)_HTTP POST /ACMEUserService/updateACMEUser |
| -------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateACMEUserRequest：**_                                                                                          |
| <pre><code>message UpdateACMEUserRequest {
	int64 acmeUserId = 1;
	string description = 2;
}</code></pre>                  |
| _**输出对象：RPCSuccess：**_                                                                                                     |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                            |

| 删除用户 adminuserRPC deleteACMEUser _(DeleteACMEUserRequest)_ returns _(RPCSuccess)_HTTP POST /ACMEUserService/deleteACMEUser |
| -------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteACMEUserRequest：**_                                                                                          |
| <pre><code>message DeleteACMEUserRequest {
	int64 acmeUserId = 1;
}</code></pre>                                           |
| _**输出对象：RPCSuccess：**_                                                                                                     |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                            |

| 计算用户数量 adminuserRPC countACMEUsers _(CountAcmeUsersRequest)_ returns _(RPCCountResponse)_HTTP POST /ACMEUserService/countACMEUsers |
| ---------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAcmeUsersRequest：**_                                                                                                  |
| <pre><code>message CountAcmeUsersRequest {
	int64 adminId = 1;
	int64 userId = 2;
	int64 acmeProviderAccountId = 3;
}</code></pre> |
| _**输出对象：RPCCountResponse：**_                                                                                                       |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                             |

| 列出单页用户 adminuserRPC listACMEUsers _(ListACMEUsersRequest)_ returns _(ListACMEUsersResponse)_HTTP POST /ACMEUserService/listACMEUsers |
| ------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：ListACMEUsersRequest：**_                                                                                                     |
| <pre><code>message ListACMEUsersRequest {
	int64 adminId = 1;
	int64 userId = 2;
	int64 offset = 3;
	int64 size = 4;
}</code></pre>  |
| _**输出对象：ListACMEUsersResponse：**_                                                                                                    |
| <pre><code>message ListACMEUsersResponse {
	repeated ACMEUser acmeUsers = 1;
}</code></pre>                                          |

| 查找单个用户 adminuserRPC findEnabledACMEUser _(FindEnabledACMEUserRequest)_ returns _(FindEnabledACMEUserResponse)_HTTP POST /ACMEUserService/findEnabledACMEUser |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：FindEnabledACMEUserRequest：**_                                                                                                                       |
| <pre><code>message FindEnabledACMEUserRequest {
	int64 acmeUserId = 1;
}</code></pre>                                                                        |
| _**输出对象：FindEnabledACMEUserResponse：**_                                                                                                                      |
| <pre><code>message FindEnabledACMEUserResponse {
	ACMEUser acmeUser = 1;
}</code></pre>                                                                      |

| 查找所有用户 adminuserRPC findAllACMEUsers _(FindAllACMEUsersRequest)_ returns _(FindAllACMEUsersResponse)_HTTP POST /ACMEUserService/findAllACMEUsers |
| ------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：FindAllACMEUsersRequest：**_                                                                                                              |
| <pre><code>message FindAllACMEUsersRequest {
	int64 adminId = 1;
	int64 userId = 2;
	string acmeProviderCode = 3;
}</code></pre>                 |
| _**输出对象：FindAllACMEUsersResponse：**_                                                                                                             |
| <pre><code>message FindAllACMEUsersResponse {
	repeated ACMEUser acmeUsers = 1;
}</code></pre>                                                   |

\
