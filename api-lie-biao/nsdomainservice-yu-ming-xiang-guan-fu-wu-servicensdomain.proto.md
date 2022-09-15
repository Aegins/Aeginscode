# NSDomainService - 域名相关服务 service\_ns\_domain.proto

#### 方法列表

* createNSDomain - 创建单个域名
* createNSDomains - 批量创建域名
* updateNSDomain - 修改域名
* deleteNSDomain - 删除域名
* deleteNSDomains - 批量删除域名
* findNSDomain - 查找单个域名
* countAllNSDomains - 计算域名数量
* listNSDomains - 列出单页域名
* listNSDomainsAfterVersion - 根据版本列出一组域名
* findNSDomainTSIG - 查找TSIG配置
* updateNSDomainTSIG - 修改TSIG配置
* existNSDomains - 检查一组域名是否存在

| 创建单个域名 adminuserRPC createNSDomain _(CreateNSDomainRequest)_ returns _(CreateNSDomainResponse)_HTTP POST /NSDomainService/createNSDomain                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSDomainRequest：**_                                                                                                                                                            |
| <pre><code>message CreateNSDomainRequest {
	int64 nsClusterId = 1; // 所属集群
	int64 userId = 2; // 所属用户
	string name = 3; // 域名
	repeated int64 nsDomainGroupIds = 4; // 域名分组ID
}</code></pre> |
| _**输出对象：CreateNSDomainResponse：**_                                                                                                                                                           |
| <pre><code>message CreateNSDomainResponse {
	int64 nsDomainId = 1;
}</code></pre>                                                                                                            |

| 批量创建域名 adminuserRPC createNSDomains _(CreateNSDomainsRequest)_ returns _(CreateNSDomainsResponse)_HTTP POST /NSDomainService/createNSDomains                                                              |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSDomainsRequest：**_                                                                                                                                                                        |
| <pre><code>message CreateNSDomainsRequest {
	int64 nsClusterId = 1; // 所属集群
	int64 userId = 2; // 所属用户
	repeated string names = 3; // 一组域名
	repeated int64 nsDomainGroupIds = 4; // 域名分组ID
}</code></pre> |
| _**输出对象：CreateNSDomainsResponse：**_                                                                                                                                                                       |
| <pre><code>message CreateNSDomainsResponse {
	repeated int64 nsDomainIds = 1;
}</code></pre>                                                                                                              |

| 修改域名 adminuserRPC updateNSDomain _(UpdateNSDomainRequest)_ returns _(RPCSuccess)_HTTP POST /NSDomainService/updateNSDomain                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateNSDomainRequest：**_                                                                                                                                                           |
| <pre><code>message UpdateNSDomainRequest {
	int64 nsDomainId = 1;
	int64 nsClusterId = 2;
	int64 userId = 3;
	repeated int64 nsDomainGroupIds = 5; // 域名分组ID
	bool isOn = 4;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                      |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                             |

| 删除域名 adminuserRPC deleteNSDomain _(DeleteNSDomainRequest)_ returns _(RPCSuccess)_HTTP POST /NSDomainService/deleteNSDomain |
| -------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteNSDomainRequest：**_                                                                                          |
| <pre><code>message DeleteNSDomainRequest {
	int64 nsDomainId = 1;
}</code></pre>                                           |
| _**输出对象：RPCSuccess：**_                                                                                                     |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                            |

| 批量删除域名 adminuserRPC deleteNSDomains _(DeleteNSDomainsRequest)_ returns _(RPCSuccess)_HTTP POST /NSDomainService/deleteNSDomains |
| ------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteNSDomainsRequest：**_                                                                                              |
| <pre><code>message DeleteNSDomainsRequest {
	repeated string names = 1;
	int64 userId = 2; // 域名所属用户ID
}</code></pre>           |
| _**输出对象：RPCSuccess：**_                                                                                                          |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                 |

| 查找单个域名 adminRPC findNSDomain _(FindNSDomainRequest)_ returns _(FindNSDomainResponse)_HTTP POST /NSDomainService/findNSDomain |
| ---------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindNSDomainRequest：**_                                                                                              |
| <pre><code>message FindNSDomainRequest {
	int64 nsDomainId = 1;
}</code></pre>                                               |
| _**输出对象：FindNSDomainResponse：**_                                                                                             |
| <pre><code>message FindNSDomainResponse {
	NSDomain nsDomain = 1;
}</code></pre>                                             |

| 计算域名数量 adminuserRPC countAllNSDomains _(CountAllNSDomainsRequest)_ returns _(RPCCountResponse)_HTTP POST /NSDomainService/countAllNSDomains              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllNSDomainsRequest：**_                                                                                                                     |
| <pre><code>message CountAllNSDomainsRequest {
	int64 userId = 1;
	int64 nsClusterId = 2;
	string keyword = 3;
	int64 nsDomainGroupId = 4;
}</code></pre> |
| _**输出对象：RPCCountResponse：**_                                                                                                                             |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                   |

| 列出单页域名 adminuserRPC listNSDomains _(ListNSDomainsRequest)_ returns _(ListNSDomainsResponse)_HTTP POST /NSDomainService/listNSDomains                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListNSDomainsRequest：**_                                                                                                                                                         |
| <pre><code>message ListNSDomainsRequest {
	int64 userId = 1;
	int64 nsClusterId = 2;
	string keyword = 3;
	int64 nsDomainGroupId = 6;
	int64 offset = 4;
	int64 size = 5;
}</code></pre> |
| _**输出对象：ListNSDomainsResponse：**_                                                                                                                                                        |
| <pre><code>message ListNSDomainsResponse {
	repeated NSDomain nsDomains = 1;
}</code></pre>                                                                                              |

| 根据版本列出一组域名 dnsRPC listNSDomainsAfterVersion _(ListNSDomainsAfterVersionRequest)_ returns _(ListNSDomainsAfterVersionResponse)_HTTP POST /NSDomainService/listNSDomainsAfterVersion |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListNSDomainsAfterVersionRequest：**_                                                                                                                                       |
| <pre><code>message ListNSDomainsAfterVersionRequest {
	int64 version = 1;
	int64 size = 2;
}</code></pre>                                                                          |
| _**输出对象：ListNSDomainsAfterVersionResponse：**_                                                                                                                                      |
| <pre><code>message ListNSDomainsAfterVersionResponse {
	repeated NSDomain nsDomains = 1;
}</code></pre>                                                                            |

| 查找TSIG配置 adminRPC findNSDomainTSIG _(FindNSDomainTSIGRequest)_ returns _(FindNSDomainTSIGResponse)_HTTP POST /NSDomainService/findNSDomainTSIG |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindNSDomainTSIGRequest：**_                                                                                                            |
| <pre><code>message FindNSDomainTSIGRequest {
	int64 nsDomainId = 1;
}</code></pre>                                                             |
| _**输出对象：FindNSDomainTSIGResponse：**_                                                                                                           |
| <pre><code>message FindNSDomainTSIGResponse {
	bytes tsigJSON = 1;
}</code></pre>                                                              |

| 修改TSIG配置 adminRPC updateNSDomainTSIG _(UpdateNSDomainTSIGRequest)_ returns _(RPCSuccess)_HTTP POST /NSDomainService/updateNSDomainTSIG |
| -------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateNSDomainTSIGRequest：**_                                                                                                  |
| <pre><code>message UpdateNSDomainTSIGRequest {
	int64 nsDomainId = 1;
	bytes tsigJSON = 2;
}</code></pre>                              |
| _**输出对象：RPCSuccess：**_                                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                        |

| 检查一组域名是否存在 adminuserRPC existNSDomains _(ExistNSDomainsRequest)_ returns _(ExistNSDomainsResponse)_HTTP POST /NSDomainService/existNSDomains |
| -------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ExistNSDomainsRequest：**_                                                                                                            |
| <pre><code>message ExistNSDomainsRequest {
	repeated string names = 1;
	int64 userId = 2;
}</code></pre>                                     |
| _**输出对象：ExistNSDomainsResponse：**_                                                                                                           |
| <pre><code>message ExistNSDomainsResponse {
	repeated string existingNames = 1;
}</code></pre>                                               |
