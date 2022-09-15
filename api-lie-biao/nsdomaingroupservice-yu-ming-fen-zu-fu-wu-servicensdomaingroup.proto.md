# NSDomainGroupService - 域名分组服务 service\_ns\_domain\_group.proto

#### 方法列表

* createNSDomainGroup - 创建分组
* updateNSDomainGroup - 修改分组
* deleteNSDomainGroup - 删除分组
* findAllNSDomainGroups - 查询所有分组
* countAllAvailableNSDomainGroups - 查询可用分组数量
* findAllAvailableNSDomainGroups - 查询所有启用分组
* findNSDomainGroup - 查找单个分组

| 创建分组 adminuserRPC createNSDomainGroup _(CreateNSDomainGroupRequest)_ returns _(CreateNSDomainGroupResponse)_HTTP POST /NSDomainGroupService/createNSDomainGroup |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSDomainGroupRequest：**_                                                                                                                          |
| <pre><code>message CreateNSDomainGroupRequest {
	string name = 1;
}</code></pre>                                                                                |
| _**输出对象：CreateNSDomainGroupResponse：**_                                                                                                                         |
| <pre><code>message CreateNSDomainGroupResponse {
	int64 nsDomainGroupId = 1;
}</code></pre>                                                                     |

| 修改分组 adminuserRPC updateNSDomainGroup _(UpdateNSDomainGroupRequest)_ returns _(RPCSuccess)_HTTP POST /NSDomainGroupService/updateNSDomainGroup |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateNSDomainGroupRequest：**_                                                                                                         |
| <pre><code>message UpdateNSDomainGroupRequest {
	int64 nsDomainGroupId = 1;
	string name = 2;
	bool isOn = 3;
}</code></pre>                   |
| _**输出对象：RPCSuccess：**_                                                                                                                         |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                |

| 删除分组 adminuserRPC deleteNSDomainGroup _(DeleteNSDomainGroupRequest)_ returns _(RPCSuccess)_HTTP POST /NSDomainGroupService/deleteNSDomainGroup |
| ---------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteNSDomainGroupRequest：**_                                                                                                         |
| <pre><code>message DeleteNSDomainGroupRequest {
	int64 nsDomainGroupId = 1;
}</code></pre>                                                     |
| _**输出对象：RPCSuccess：**_                                                                                                                         |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                |

| 查询所有分组 adminuserRPC findAllNSDomainGroups _(FindAllNSDomainGroupsRequest)_ returns _(FindAllNSDomainGroupsResponse)_HTTP POST /NSDomainGroupService/findAllNSDomainGroups |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindAllNSDomainGroupsRequest：**_                                                                                                                                  |
| <pre><code>message FindAllNSDomainGroupsRequest {
	int64 userId = 1;
}</code></pre>                                                                                       |
| _**输出对象：FindAllNSDomainGroupsResponse：**_                                                                                                                                 |
| <pre><code>message FindAllNSDomainGroupsResponse {
	repeated NSDomainGroup nsDomainGroups = 1;
}</code></pre>                                                             |

| 查询可用分组数量 adminuserRPC countAllAvailableNSDomainGroups _(CountAllAvailableNSDomainGroupsRequest)_ returns _(RPCCountResponse)_HTTP POST /NSDomainGroupService/countAllAvailableNSDomainGroups |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllAvailableNSDomainGroupsRequest：**_                                                                                                                                           |
| <pre><code>message CountAllAvailableNSDomainGroupsRequest {
	int64 userId = 1;
}</code></pre>                                                                                                |
| _**输出对象：RPCCountResponse：**_                                                                                                                                                                 |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                                                       |

| 查询所有启用分组 adminuserRPC findAllAvailableNSDomainGroups _(FindAllAvailableNSDomainGroupsRequest)_ returns _(FindAllAvailableNSDomainGroupsResponse)_HTTP POST /NSDomainGroupService/findAllAvailableNSDomainGroups |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindAllAvailableNSDomainGroupsRequest：**_                                                                                                                                                               |
| <pre><code>message FindAllAvailableNSDomainGroupsRequest {
	int64 userId = 1;
}</code></pre>                                                                                                                    |
| _**输出对象：FindAllAvailableNSDomainGroupsResponse：**_                                                                                                                                                              |
| <pre><code>message FindAllAvailableNSDomainGroupsResponse {
	repeated NSDomainGroup nsDomainGroups = 1;
}</code></pre>                                                                                          |

| 查找单个分组 adminuserRPC findNSDomainGroup _(FindNSDomainGroupRequest)_ returns _(FindNSDomainGroupResponse)_HTTP POST /NSDomainGroupService/findNSDomainGroup |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindNSDomainGroupRequest：**_                                                                                                                      |
| <pre><code>message FindNSDomainGroupRequest {
	int64 nsDomainGroupId = 1;
}</code></pre>                                                                  |
| _**输出对象：FindNSDomainGroupResponse：**_                                                                                                                     |
| <pre><code>message FindNSDomainGroupResponse {
	NSDomainGroup nsDomainGroup = 1;
}</code></pre>                                                           |
