# UserIdentityService - 用户实名认证服务 service\_user\_identity.proto



* createUserIdentity - 创建实名认证信息
* findEnabledUserIdentity - 查找单个实名认证信息
* findEnabledUserIdentityWithOrgType - 查看某个类型的实名认证信息
* checkUserIdentityIsSubmitted - 检查是否正在审核中
* updateUserIdentity - 修改实名认证信息
* submitUserIdentity - 提交审核实名认证信息
* cancelUserIdentity - 取消提交实名审核认证信息
* resetUserIdentity - 重置用户实名认证信息
* rejectUserIdentity - 拒绝用户实名认证信息
* verifyUserIdentity - 通过用户实名认证信息

| 创建实名认证信息 userRPC createUserIdentity _(CreateUserIdentityRequest)_ returns _(CreateUserIdentityResponse)_HTTP POST /UserIdentityService/createUserIdentity                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateUserIdentityRequest：**_                                                                                                                                                                                                           |
| <pre><code>message CreateUserIdentityRequest {
	string orgType = 1;
	string type = 2;
	string realName = 3;
	string number = 4;
	repeated int64 fileIds = 5;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：CreateUserIdentityResponse：**_                                                                                                                                                                                                          |
| <pre><code>message CreateUserIdentityResponse {
	int64 userIdentityId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                                                   |

| 查找单个实名认证信息 adminuserRPC findEnabledUserIdentity _(FindEnabledUserIdentityRequest)_ returns _(FindEnabledUserIdentityResponse)_HTTP POST /UserIdentityService/findEnabledUserIdentity |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：FindEnabledUserIdentityRequest：**_                                                                                                                                           |
| <pre><code>message FindEnabledUserIdentityRequest {
	int64 userIdentityId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                    |
| _**输出对象：FindEnabledUserIdentityResponse：**_                                                                                                                                          |
| <pre><code>message FindEnabledUserIdentityResponse {
	UserIdentity userIdentity = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>              |

| 查看某个类型的实名认证信息 adminuserRPC findEnabledUserIdentityWithOrgType _(FindEnabledUserIdentityWithOrgTypeRequest)_ returns _(FindEnabledUserIdentityWithOrgTypeResponse)_HTTP POST /UserIdentityService/findEnabledUserIdentityWithOrgType |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledUserIdentityWithOrgTypeRequest：**_                                                                                                                                                                               |
| <pre><code>message FindEnabledUserIdentityWithOrgTypeRequest {
	int64 userId = 1; // 用户端不需要设置此参数
	string orgType = 2; // 阻止类型
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                    |
| _**输出对象：FindEnabledUserIdentityWithOrgTypeResponse：**_                                                                                                                                                                              |
| <pre><code>message FindEnabledUserIdentityWithOrgTypeResponse {
	UserIdentity userIdentity = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                  |

| 检查是否正在审核中 adminRPC checkUserIdentityIsSubmitted _(CheckUserIdentityIsSubmittedRequest)_ returns _(CheckUserIdentityIsSubmittedResponse)_HTTP POST /UserIdentityService/checkUserIdentityIsSubmitted |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CheckUserIdentityIsSubmittedRequest：**_                                                                                                                                                     |
| <pre><code>message CheckUserIdentityIsSubmittedRequest {
	int64 userId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                      |
| _**输出对象：CheckUserIdentityIsSubmittedResponse：**_                                                                                                                                                    |
| <pre><code>message CheckUserIdentityIsSubmittedResponse {
	bool isSubmitted = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                 |

| 修改实名认证信息 userRPC updateUserIdentity _(UpdateUserIdentityRequest)_ returns _(RPCSuccess)_HTTP POST /UserIdentityService/updateUserIdentity                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateUserIdentityRequest：**_                                                                                                                                                                                                                 |
| <pre><code>message UpdateUserIdentityRequest {
	int64 userIdentityId = 1;
	string type = 2;
	string realName = 3;
	string number = 4;
	repeated int64 fileIds = 5;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                |
| <pre><code>message RPCSuccess {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                                                                                                   |

| 提交审核实名认证信息 userRPC submitUserIdentity _(SubmitUserIdentityRequest)_ returns _(RPCSuccess)_HTTP POST /UserIdentityService/submitUserIdentity                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：SubmitUserIdentityRequest：**_                                                                                                                        |
| <pre><code>message SubmitUserIdentityRequest {
	int64 userIdentityId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                       |
| <pre><code>message RPCSuccess {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                          |

| 取消提交实名审核认证信息 userRPC cancelUserIdentity _(CancelUserIdentityRequest)_ returns _(RPCSuccess)_HTTP POST /UserIdentityService/cancelUserIdentity                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：CancelUserIdentityRequest：**_                                                                                                                        |
| <pre><code>message CancelUserIdentityRequest {
	int64 userIdentityId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                       |
| <pre><code>message RPCSuccess {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                          |

| 重置用户实名认证信息 adminRPC resetUserIdentity _(ResetUserIdentityRequest)_ returns _(RPCSuccess)_HTTP POST /UserIdentityService/resetUserIdentity                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ResetUserIdentityRequest：**_                                                                                                                        |
| <pre><code>message ResetUserIdentityRequest {
	int64 userIdentityId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                      |
| <pre><code>message RPCSuccess {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                         |

| 拒绝用户实名认证信息 adminRPC rejectUserIdentity _(RejectUserIdentityRequest)_ returns _(RPCSuccess)_HTTP POST /UserIdentityService/rejectUserIdentity                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：RejectUserIdentityRequest：**_                                                                                                                                            |
| <pre><code>message RejectUserIdentityRequest {
	int64 userIdentityId = 1;
	string reason = 2;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                           |
| <pre><code>message RPCSuccess {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                              |

| 通过用户实名认证信息 adminRPC verifyUserIdentity _(VerifyUserIdentityRequest)_ returns _(RPCSuccess)_HTTP POST /UserIdentityService/verifyUserIdentity                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：VerifyUserIdentityRequest：**_                                                                                                                        |
| <pre><code>message VerifyUserIdentityRequest {
	int64 userIdentityId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                       |
| <pre><code>message RPCSuccess {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                          |

\
