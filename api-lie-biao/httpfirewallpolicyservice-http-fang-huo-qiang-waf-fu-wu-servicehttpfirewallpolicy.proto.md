# HTTPFirewallPolicyService - HTTP防火墙（WAF）服务 service\_http\_firewall\_policy.proto

#### 方法列表

* findAllEnabledHTTPFirewallPolicies - 获取所有可用策略
* createHTTPFirewallPolicy - 创建防火墙策略
* createEmptyHTTPFirewallPolicy - 创建空防火墙策略
* updateHTTPFirewallPolicy - 修改防火墙策略
* updateHTTPFirewallPolicyGroups - 修改分组信息
* updateHTTPFirewallInboundConfig - 修改inbound信息
* countAllEnabledHTTPFirewallPolicies - 计算可用的防火墙策略数量
* listEnabledHTTPFirewallPolicies - 列出单页的防火墙策略
* deleteHTTPFirewallPolicy - 删除某个防火墙策略
* findEnabledHTTPFirewallPolicyConfig - 查找单个防火墙配置
* findEnabledHTTPFirewallPolicy - 获取防火墙的基本信息
* importHTTPFirewallPolicy - 导入策略数据
* checkHTTPFirewallPolicyIPStatus - 检查IP状态

| 获取所有可用策略 adminRPC findAllEnabledHTTPFirewallPolicies _(FindAllEnabledHTTPFirewallPoliciesRequest)_ returns _(FindAllEnabledHTTPFirewallPoliciesResponse)_HTTP POST /HTTPFirewallPolicyService/findAllEnabledHTTPFirewallPolicies |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindAllEnabledHTTPFirewallPoliciesRequest：**_                                                                                                                                                                            |
| <pre><code>message FindAllEnabledHTTPFirewallPoliciesRequest {

}</code></pre>                                                                                                                                                   |
| _**输出对象：FindAllEnabledHTTPFirewallPoliciesResponse：**_                                                                                                                                                                           |
| <pre><code>message FindAllEnabledHTTPFirewallPoliciesResponse {
	repeated HTTPFirewallPolicy firewallPolicies = 1;
}</code></pre>                                                                                                |

| 创建防火墙策略 adminuserRPC createHTTPFirewallPolicy _(CreateHTTPFirewallPolicyRequest)_ returns _(CreateHTTPFirewallPolicyResponse)_HTTP POST /HTTPFirewallPolicyService/createHTTPFirewallPolicy                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateHTTPFirewallPolicyRequest：**_                                                                                                                                                                                |
| <pre><code>message CreateHTTPFirewallPolicyRequest {
	bool isOn = 1;
	string name = 2;
	string description = 3;
	repeated string httpFirewallGroupCodes = 4;
	int64 serverId = 5;
	int64 serverGroupId = 6;
}</code></pre> |
| _**输出对象：CreateHTTPFirewallPolicyResponse：**_                                                                                                                                                                               |
| <pre><code>message CreateHTTPFirewallPolicyResponse {
	int64 httpFirewallPolicyId = 1;
}</code></pre>                                                                                                                      |

| 创建空防火墙策略 adminuserRPC createEmptyHTTPFirewallPolicy _(CreateEmptyHTTPFirewallPolicyRequest)_ returns _(CreateEmptyHTTPFirewallPolicyResponse)_HTTP POST /HTTPFirewallPolicyService/createEmptyHTTPFirewallPolicy |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateEmptyHTTPFirewallPolicyRequest：**_                                                                                                                                                                 |
| <pre><code>message CreateEmptyHTTPFirewallPolicyRequest {
	bool isOn = 1;
	string name = 2;
	string description = 3;
	int64 serverId = 4;
	int64 serverGroupId = 5;
}</code></pre>                               |
| _**输出对象：CreateEmptyHTTPFirewallPolicyResponse：**_                                                                                                                                                                |
| <pre><code>message CreateEmptyHTTPFirewallPolicyResponse {
	int64 httpFirewallPolicyId = 1;
}</code></pre>                                                                                                       |

| 修改防火墙策略 adminRPC updateHTTPFirewallPolicy _(UpdateHTTPFirewallPolicyRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPFirewallPolicyService/updateHTTPFirewallPolicy                                                                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPFirewallPolicyRequest：**_                                                                                                                                                                                                                                                                                                                       |
| <pre><code>message UpdateHTTPFirewallPolicyRequest {
	int64 httpFirewallPolicyId = 1;
	bool isOn = 2;
	string name = 3;
	string description = 4;
	repeated string firewallGroupCodes = 5;
	bytes blockOptionsJSON = 6;
	bytes captchaOptionsJSON = 11;
	string mode = 7;
	bool useLocalFirewall = 8;
	bytes synFloodJSON = 9;
	bytes LogJSON = 10;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                                                                                            |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                                                                                   |

| 修改分组信息 adminuserRPC updateHTTPFirewallPolicyGroups _(UpdateHTTPFirewallPolicyGroupsRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPFirewallPolicyService/updateHTTPFirewallPolicyGroups |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPFirewallPolicyGroupsRequest：**_                                                                                                                                      |
| <pre><code>message UpdateHTTPFirewallPolicyGroupsRequest {
	int64 httpFirewallPolicyId = 1;
	bytes inboundJSON = 2;
	bytes outboundJSON = 3;
}</code></pre>                            |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                        |

| 修改inbound信息 adminuserRPC updateHTTPFirewallInboundConfig _(UpdateHTTPFirewallInboundConfigRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPFirewallPolicyService/updateHTTPFirewallInboundConfig |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPFirewallInboundConfigRequest：**_                                                                                                                                             |
| <pre><code>message UpdateHTTPFirewallInboundConfigRequest {
	int64 httpFirewallPolicyId = 1;
	bytes inboundJSON = 2;
}</code></pre>                                                            |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                         |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                |

| 计算可用的防火墙策略数量 adminRPC countAllEnabledHTTPFirewallPolicies _(CountAllEnabledHTTPFirewallPoliciesRequest)_ returns _(RPCCountResponse)_HTTP POST /HTTPFirewallPolicyService/countAllEnabledHTTPFirewallPolicies |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllEnabledHTTPFirewallPoliciesRequest：**_                                                                                                                                                        |
| <pre><code>message CountAllEnabledHTTPFirewallPoliciesRequest {
	string keyword = 1;
	int64 nodeClusterId = 2;
}</code></pre>                                                                                 |
| _**输出对象：RPCCountResponse：**_                                                                                                                                                                                  |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                                                                        |

| 列出单页的防火墙策略 adminRPC listEnabledHTTPFirewallPolicies _(ListEnabledHTTPFirewallPoliciesRequest)_ returns _(ListEnabledHTTPFirewallPoliciesResponse)_HTTP POST /HTTPFirewallPolicyService/listEnabledHTTPFirewallPolicies |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListEnabledHTTPFirewallPoliciesRequest：**_                                                                                                                                                                     |
| <pre><code>message ListEnabledHTTPFirewallPoliciesRequest {
	int64 offset = 1;
	int64 size = 2;
	string keyword = 3;
	int64 nodeClusterId = 4;
}</code></pre>                                                          |
| _**输出对象：ListEnabledHTTPFirewallPoliciesResponse：**_                                                                                                                                                                    |
| <pre><code>message ListEnabledHTTPFirewallPoliciesResponse {
	repeated HTTPFirewallPolicy httpFirewallPolicies = 1;
}</code></pre>                                                                                     |

| 删除某个防火墙策略 adminRPC deleteHTTPFirewallPolicy _(DeleteHTTPFirewallPolicyRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPFirewallPolicyService/deleteHTTPFirewallPolicy |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteHTTPFirewallPolicyRequest：**_                                                                                                                         |
| <pre><code>message DeleteHTTPFirewallPolicyRequest {
	int64 httpFirewallPolicyId = 1;
}</code></pre>                                                                |
| _**输出对象：RPCSuccess：**_                                                                                                                                              |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                     |

| 查找单个防火墙配置 adminuserRPC findEnabledHTTPFirewallPolicyConfig _(FindEnabledHTTPFirewallPolicyConfigRequest)_ returns _(FindEnabledHTTPFirewallPolicyConfigResponse)_HTTP POST /HTTPFirewallPolicyService/findEnabledHTTPFirewallPolicyConfig |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledHTTPFirewallPolicyConfigRequest：**_                                                                                                                                                                                    |
| <pre><code>message FindEnabledHTTPFirewallPolicyConfigRequest {
	int64 httpFirewallPolicyId = 1;
}</code></pre>                                                                                                                           |
| _**输出对象：FindEnabledHTTPFirewallPolicyConfigResponse：**_                                                                                                                                                                                   |
| <pre><code>message FindEnabledHTTPFirewallPolicyConfigResponse {
	bytes httpFirewallPolicyJSON = 1;
}</code></pre>                                                                                                                        |

| 获取防火墙的基本信息 adminuserRPC findEnabledHTTPFirewallPolicy _(FindEnabledHTTPFirewallPolicyRequest)_ returns _(FindEnabledHTTPFirewallPolicyResponse)_HTTP POST /HTTPFirewallPolicyService/findEnabledHTTPFirewallPolicy |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：FindEnabledHTTPFirewallPolicyRequest：**_                                                                                                                                                                   |
| <pre><code>message FindEnabledHTTPFirewallPolicyRequest {
	int64 httpFirewallPolicyId = 1;
}</code></pre>                                                                                                          |
| _**输出对象：FindEnabledHTTPFirewallPolicyResponse：**_                                                                                                                                                                  |
| <pre><code>message FindEnabledHTTPFirewallPolicyResponse {
	HTTPFirewallPolicy httpFirewallPolicy = 1;
}</code></pre>                                                                                              |

| 导入策略数据 adminRPC importHTTPFirewallPolicy _(ImportHTTPFirewallPolicyRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPFirewallPolicyService/importHTTPFirewallPolicy |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ImportHTTPFirewallPolicyRequest：**_                                                                                                                      |
| <pre><code>message ImportHTTPFirewallPolicyRequest {
	int64 httpFirewallPolicyId = 1;
	bytes httpFirewallPolicyJSON = 2;
}</code></pre>                          |
| _**输出对象：RPCSuccess：**_                                                                                                                                           |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                  |

| 检查IP状态 adminRPC checkHTTPFirewallPolicyIPStatus _(CheckHTTPFirewallPolicyIPStatusRequest)_ returns _(CheckHTTPFirewallPolicyIPStatusResponse)_HTTP POST /HTTPFirewallPolicyService/checkHTTPFirewallPolicyIPStatus                                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：CheckHTTPFirewallPolicyIPStatusRequest：**_                                                                                                                                                                                                                                                                                               |
| <pre><code>message CheckHTTPFirewallPolicyIPStatusRequest {
	int64 httpFirewallPolicyId = 1;
	string ip = 2;
}</code></pre>                                                                                                                                                                                                                      |
| _**输出对象：CheckHTTPFirewallPolicyIPStatusResponse：**_                                                                                                                                                                                                                                                                                              |
| <pre><code>message CheckHTTPFirewallPolicyIPStatusResponse {
	bool isOk = 1; // 是否查询成功
	string error = 2;
	bool isFound = 3; // 是否找到
	bool isAllowed = 4; // 是否允许
	IPList ipList = 5; // 匹配的IPList
	IPItem ipItem = 6; // 匹配的IPItem
	RegionCountry regionCountry = 7; // 匹配到封禁的地区
	RegionProvince regionProvince = 8; // 匹配到封禁的省份
}</code></pre> |
