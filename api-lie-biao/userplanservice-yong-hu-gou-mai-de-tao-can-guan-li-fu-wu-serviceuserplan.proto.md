# UserPlanService - 用户购买的套餐管理服务 service\_user\_plan.proto

#### 方法列表

* buyUserPlan - 购买套餐
* renewUserPlan - 续费套餐
* findEnabledUserPlan - 查找单个已购套餐信息
* updateUserPlan - 修改已购套餐
* deleteUserPlan - 删除已购套餐
* countAllEnabledUserPlans - 计算已购套餐数
* listEnabledUserPlans - 列出单页已购套餐
* findAllEnabledUserPlansForServer - 查找所有服务可用的套餐

| 购买套餐 adminuserRPC buyUserPlan _(BuyUserPlanRequest)_ returns _(BuyUserPlanResponse)_HTTP POST /UserPlanService/buyUserPlan                                                    |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：BuyUserPlanRequest：**_                                                                                                                                                |
| <pre><code>message BuyUserPlanRequest {
	int64 userId = 1;
	int64 planId = 2;
	string dayTo = 3;
	string period = 4;
	int32 countPeriod = 5;
	string name = 6;
}</code></pre> |
| _**输出对象：BuyUserPlanResponse：**_                                                                                                                                               |
| <pre><code>message BuyUserPlanResponse {
	int64 userPlanId = 1;
}</code></pre>                                                                                                |

| 续费套餐 adminuserRPC renewUserPlan _(RenewUserPlanRequest)_ returns _(RPCSuccess)_HTTP POST /UserPlanService/renewUserPlan                        |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：RenewUserPlanRequest：**_                                                                                                               |
| <pre><code>message RenewUserPlanRequest {
	int64 userPlanId = 1;
	string dayTo = 3;
	string period = 4;
	int32 countPeriod = 5;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                         |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                |

| 查找单个已购套餐信息 adminuserRPC findEnabledUserPlan _(FindEnabledUserPlanRequest)_ returns _(FindEnabledUserPlanResponse)_HTTP POST /UserPlanService/findEnabledUserPlan |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledUserPlanRequest：**_                                                                                                                           |
| <pre><code>message FindEnabledUserPlanRequest {
	int64 userPlanId = 1;
}</code></pre>                                                                            |
| _**输出对象：FindEnabledUserPlanResponse：**_                                                                                                                          |
| <pre><code>message FindEnabledUserPlanResponse {
	UserPlan userPlan = 1;
}</code></pre>                                                                          |

| 修改已购套餐 adminRPC updateUserPlan _(UpdateUserPlanRequest)_ returns _(RPCSuccess)_HTTP POST /UserPlanService/updateUserPlan                                 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateUserPlanRequest：**_                                                                                                                        |
| <pre><code>message UpdateUserPlanRequest {
	int64 userPlanId = 1;
	int64 planId = 2;
	string dayTo = 3;
	bool isOn = 4;
	string name = 5;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                   |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                          |

| 删除已购套餐 adminuserRPC deleteUserPlan _(DeleteUserPlanRequest)_ returns _(RPCSuccess)_HTTP POST /UserPlanService/deleteUserPlan                         |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteUserPlanRequest：**_                                                                                                                    |
| <pre><code>message DeleteUserPlanRequest {
	int64 userPlanId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                               |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                      |

| 计算已购套餐数 adminuserRPC countAllEnabledUserPlans _(CountAllEnabledUserPlansRequest)_ returns _(RPCCountResponse)_HTTP POST /UserPlanService/countAllEnabledUserPlans |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllEnabledUserPlansRequest：**_                                                                                                                       |
| <pre><code>message CountAllEnabledUserPlansRequest {
	bool isAvailable = 1;
	bool isExpired = 2;
	int32 expiringDays = 3;
	int64 userId = 4;
}</code></pre>       |
| _**输出对象：RPCCountResponse：**_                                                                                                                                      |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                        |

| 列出单页已购套餐 adminuserRPC listEnabledUserPlans _(ListEnabledUserPlansRequest)_ returns _(ListEnabledUserPlansResponse)_HTTP POST /UserPlanService/listEnabledUserPlans                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListEnabledUserPlansRequest：**_                                                                                                                                                     |
| <pre><code>message ListEnabledUserPlansRequest {
	bool isAvailable = 1;
	bool isExpired = 2;
	int32 expiringDays = 3;
	int64 userId = 4;
	int64 offset = 5;
	int64 size = 6;
}</code></pre> |
| _**输出对象：ListEnabledUserPlansResponse：**_                                                                                                                                                    |
| <pre><code>message ListEnabledUserPlansResponse {
	repeated UserPlan userPlans = 1;
}</code></pre>                                                                                          |

| 查找所有服务可用的套餐 adminuserRPC findAllEnabledUserPlansForServer _(FindAllEnabledUserPlansForServerRequest)_ returns _(FindAllEnabledUserPlansForServerResponse)_HTTP POST /UserPlanService/findAllEnabledUserPlansForServer |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindAllEnabledUserPlansForServerRequest：**_                                                                                                                                                                   |
| <pre><code>message FindAllEnabledUserPlansForServerRequest {
	int64 userId = 1;
	int64 serverId = 2;
}</code></pre>                                                                                                   |
| _**输出对象：FindAllEnabledUserPlansForServerResponse：**_                                                                                                                                                                  |
| <pre><code>message FindAllEnabledUserPlansForServerResponse {
	repeated UserPlan userPlans = 1;
}</code></pre>                                                                                                        |
