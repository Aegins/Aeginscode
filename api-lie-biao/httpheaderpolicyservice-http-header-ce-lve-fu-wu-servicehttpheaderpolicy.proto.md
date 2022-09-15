# HTTPHeaderPolicyService - HTTP Header策略服务 service\_http\_header\_policy.proto

#### 方法列表

* findEnabledHTTPHeaderPolicyConfig - 查找策略配置
* createHTTPHeaderPolicy - 创建策略
* updateHTTPHeaderPolicyAddingHeaders - 修改AddHeaders
* updateHTTPHeaderPolicySettingHeaders - 修改SetHeaders
* updateHTTPHeaderPolicyAddingTrailers - 修改AddTrailers
* updateHTTPHeaderPolicyReplacingHeaders - 修改ReplaceHeaders
* updateHTTPHeaderPolicyDeletingHeaders - 修改删除的Headers

| 查找策略配置 adminuserRPC findEnabledHTTPHeaderPolicyConfig _(FindEnabledHTTPHeaderPolicyConfigRequest)_ returns _(FindEnabledHTTPHeaderPolicyConfigResponse)_HTTP POST /HTTPHeaderPolicyService/findEnabledHTTPHeaderPolicyConfig |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledHTTPHeaderPolicyConfigRequest：**_                                                                                                                                                                         |
| <pre><code>message FindEnabledHTTPHeaderPolicyConfigRequest {
	int64 headerPolicyId = 1;
}</code></pre>                                                                                                                      |
| _**输出对象：FindEnabledHTTPHeaderPolicyConfigResponse：**_                                                                                                                                                                        |
| <pre><code>message FindEnabledHTTPHeaderPolicyConfigResponse {
	bytes headerPolicyJSON = 1;
}</code></pre>                                                                                                                   |

| 创建策略 adminuserRPC createHTTPHeaderPolicy _(CreateHTTPHeaderPolicyRequest)_ returns _(CreateHTTPHeaderPolicyResponse)_HTTP POST /HTTPHeaderPolicyService/createHTTPHeaderPolicy |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：CreateHTTPHeaderPolicyRequest：**_                                                                                                                                      |
| <pre><code>message CreateHTTPHeaderPolicyRequest {

}</code></pre>                                                                                                             |
| _**输出对象：CreateHTTPHeaderPolicyResponse：**_                                                                                                                                     |
| <pre><code>message CreateHTTPHeaderPolicyResponse {
	int64 headerPolicyId = 1;
}</code></pre>                                                                                  |

| 修改AddHeaders adminuserRPC updateHTTPHeaderPolicyAddingHeaders _(UpdateHTTPHeaderPolicyAddingHeadersRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPHeaderPolicyService/updateHTTPHeaderPolicyAddingHeaders |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPHeaderPolicyAddingHeadersRequest：**_                                                                                                                                                    |
| <pre><code>message UpdateHTTPHeaderPolicyAddingHeadersRequest {
	int64 headerPolicyId = 1;
	bytes headersJSON = 2;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理</a></p>              |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                    |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                           |

| 修改SetHeaders adminuserRPC updateHTTPHeaderPolicySettingHeaders _(UpdateHTTPHeaderPolicySettingHeadersRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPHeaderPolicyService/updateHTTPHeaderPolicySettingHeaders |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：UpdateHTTPHeaderPolicySettingHeadersRequest：**_                                                                                                                                                      |
| <pre><code>message UpdateHTTPHeaderPolicySettingHeadersRequest {
	int64 headerPolicyId = 1;
	bytes headersJSON = 2;
}</code></pre>                                                                           |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                       |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                              |

| 修改AddTrailers adminuserRPC updateHTTPHeaderPolicyAddingTrailers _(UpdateHTTPHeaderPolicyAddingTrailersRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPHeaderPolicyService/updateHTTPHeaderPolicyAddingTrailers |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPHeaderPolicyAddingTrailersRequest：**_                                                                                                                                                       |
| <pre><code>message UpdateHTTPHeaderPolicyAddingTrailersRequest {
	int64 headerPolicyId = 1;
	bytes headersJSON = 2;
}</code></pre>                                                                            |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                        |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                               |

| 修改ReplaceHeaders adminuserRPC updateHTTPHeaderPolicyReplacingHeaders _(UpdateHTTPHeaderPolicyReplacingHeadersRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPHeaderPolicyService/updateHTTPHeaderPolicyReplacingHeaders |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPHeaderPolicyReplacingHeadersRequest：**_                                                                                                                                                              |
| <pre><code>message UpdateHTTPHeaderPolicyReplacingHeadersRequest {
	int64 headerPolicyId = 1;
	bytes headersJSON = 2;
}</code></pre>                                                                                   |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                        |

| 修改删除的Headers adminuserRPC updateHTTPHeaderPolicyDeletingHeaders _(UpdateHTTPHeaderPolicyDeletingHeadersRequest)_ returns _(RPCSuccess)_HTTP POST /HTTPHeaderPolicyService/updateHTTPHeaderPolicyDeletingHeaders |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateHTTPHeaderPolicyDeletingHeadersRequest：**_                                                                                                                                                        |
| <pre><code>message UpdateHTTPHeaderPolicyDeletingHeadersRequest {
	int64 headerPolicyId = 1;
	repeated string headerNames = 2;
}</code></pre>                                                                   |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                          |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                 |
