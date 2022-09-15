# NSDomainService - 域名相关服务 service\_ns\_domain.proto

#### 方法列表

* createNSRecord - 创建记录
* createNSRecords - 批量创建记录
* createNSRecordsWithDomainNames - 为一组域名批量创建记录
* updateNSRecordsWithDomainNames - 批量修改一组域名的一组记录
* deleteNSRecordsWithDomainNames - 批量删除一组域名的一组记录
* updateNSRecordsIsOnWithDomainNames - 批量一组域名的一组记录启用状态
* importNSRecords - 导入域名解析
* updateNSRecord - 修改记录
* deleteNSRecord - 删除记录
* countAllNSRecords - 计算记录数量
* listNSRecords - 读取单页记录
* findNSRecord - 查询单个记录信息
* listNSRecordsAfterVersion - 根据版本列出一组记录

| 创建记录 adminRPC createNSRecord _(CreateNSRecordRequest)_ returns _(CreateNSRecordResponse)_HTTP POST /NSRecordService/createNSRecord                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSRecordRequest：**_                                                                                                                                                                                                                                               |
| <pre><code>message CreateNSRecordRequest {
	int64 nsDomainId = 1;
	string description = 2;
	string name = 3;
	string type = 4;
	string value = 5;
	int32 ttl = 6;
	repeated int64 nsRouteIds = 7 [deprecated = true];
	repeated string nsRouteCodes = 8; // 路线代号
}</code></pre> |
| _**输出对象：CreateNSRecordResponse：**_                                                                                                                                                                                                                                              |
| <pre><code>message CreateNSRecordResponse {
	int64 nsRecordId = 1;
}</code></pre>                                                                                                                                                                                               |

| 批量创建记录 adminRPC createNSRecords _(CreateNSRecordsRequest)_ returns _(CreateNSRecordsResponse)_HTTP POST /NSRecordService/createNSRecords                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSRecordsRequest：**_                                                                                                                                                                                                     |
| <pre><code>message CreateNSRecordsRequest {
	int64 nsDomainId = 1;
	string description = 2;
	repeated string names = 3;
	string type = 4;
	string value = 5;
	int32 ttl = 6;
	repeated string nsRouteCodes = 7; // 路线代号
}</code></pre> |
| _**输出对象：CreateNSRecordsResponse：**_                                                                                                                                                                                                    |
| <pre><code>message CreateNSRecordsResponse {
	repeated int64 nsRecordIds = 1;
}</code></pre>                                                                                                                                           |

| 为一组域名批量创建记录 adminuserRPC createNSRecordsWithDomainNames _(CreateNSRecordsWithDomainNamesRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/createNSRecordsWithDomainNames                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSRecordsWithDomainNamesRequest：**_                                                                                                                                                  |
| <pre><code>message CreateNSRecordsWithDomainNamesRequest {
	repeated string nsDomainNames = 1;
	bytes recordsJSON = 2;
	bool removeOld = 3;
	bool removeAll = 4;
	int64 userId = 5;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                             |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                    |

| 批量修改一组域名的一组记录 adminuserRPC updateNSRecordsWithDomainNames _(UpdateNSRecordsWithDomainNamesRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/updateNSRecordsWithDomainNames                                                                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateNSRecordsWithDomainNamesRequest：**_                                                                                                                                                                                                                                                                                                         |
| <pre><code>message UpdateNSRecordsWithDomainNamesRequest {
	repeated string nsDomainNames = 1;
	string searchName = 2;
	string searchValue = 3;
	string searchType = 4;
	repeated string searchNSRouteCodes = 5;
	string newName = 6;
	string newValue = 7;
	string newType = 8;
	repeated string newNSRouteCodes = 9;
	int64 userId = 10;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                                                                                    |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                                                                           |

| 批量删除一组域名的一组记录 adminuserRPC deleteNSRecordsWithDomainNames _(DeleteNSRecordsWithDomainNamesRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/deleteNSRecordsWithDomainNames                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteNSRecordsWithDomainNamesRequest：**_                                                                                                                                                                                                  |
| <pre><code>message DeleteNSRecordsWithDomainNamesRequest {
	repeated string nsDomainNames = 1;
	string searchName = 2;
	string searchValue = 3;
	string searchType = 4;
	repeated string searchNSRouteCodes = 5;
	int64 userId = 6;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                             |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                    |

| 批量一组域名的一组记录启用状态 adminuserRPC updateNSRecordsIsOnWithDomainNames _(UpdateNSRecordsIsOnWithDomainNamesRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/updateNSRecordsIsOnWithDomainNames                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateNSRecordsIsOnWithDomainNamesRequest：**_                                                                                                                                                                                                                  |
| <pre><code>message UpdateNSRecordsIsOnWithDomainNamesRequest {
	repeated string nsDomainNames = 1;
	string searchName = 2;
	string searchValue = 3;
	string searchType = 4;
	repeated string searchNSRouteCodes = 5;
	bool isOn = 6;
	int64 userId = 7;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                        |

| 导入域名解析 adminuserRPC importNSRecords _(ImportNSRecordsRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/importNSRecords                                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ImportNSRecordsRequest：**_                                                                                                                                                                                                                                                                             |
| <pre><code>message ImportNSRecordsRequest {
	repeated Record nsRecords = 1;
	int64 userId = 2;


	message Record {
		string nsDomainName = 1;
		string name = 2;
		string type = 3;
		string value = 4;
		int32 ttl = 5;
	}
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                                         |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                                |

| 修改记录 adminRPC updateNSRecord _(UpdateNSRecordRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/updateNSRecord                                                                                                                                                                          |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateNSRecordRequest：**_                                                                                                                                                                                                                                                               |
| <pre><code>message UpdateNSRecordRequest {
	int64 nsRecordId = 1;
	string description = 2;
	string name = 3;
	string type = 4;
	string value = 5;
	int32 ttl = 6;
	repeated int64 nsRouteIds = 7 [deprecated = true];
	bool isOn = 8;
	repeated string nsRouteCodes = 9; // 路线代号
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                          |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                 |

| 删除记录 adminRPC deleteNSRecord _(DeleteNSRecordRequest)_ returns _(RPCSuccess)_HTTP POST /NSRecordService/deleteNSRecord |
| ---------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：DeleteNSRecordRequest：**_                                                                                      |
| <pre><code>message DeleteNSRecordRequest {
	int64 nsRecordId = 1;
}</code></pre>                                       |
| _**输出对象：RPCSuccess：**_                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                        |

| 计算记录数量 adminRPC countAllNSRecords _(CountAllNSRecordsRequest)_ returns _(RPCCountResponse)_HTTP POST /NSRecordService/countAllNSRecords                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllNSRecordsRequest：**_                                                                                                                                                                             |
| <pre><code>message CountAllNSRecordsRequest {
	int64 nsDomainId = 1;
	string type = 2;
	int64 nsRouteId = 3 [deprecated = true]; // 使用nsRouteCode代替
	string nsRouteCode = 5;
	string keyword = 4;
}</code></pre> |
| _**输出对象：RPCCountResponse：**_                                                                                                                                                                                     |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                                                                           |

| 读取单页记录 adminRPC listNSRecords _(ListNSRecordsRequest)_ returns _(ListNSRecordsResponse)_HTTP POST /NSRecordService/listNSRecords                                                                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListNSRecordsRequest：**_                                                                                                                                                                                                                                                                                                                                          |
| <pre><code>message ListNSRecordsRequest {
	int64 nsDomainId = 1;
	string type = 2;
	int64 nsRouteId = 3 [deprecated = true]; // 使用nsRouteCode代替
	string nsRouteCode = 7;
	string keyword = 4;

	bool nameAsc = 8;
	bool nameDesc = 9;
	bool typeAsc = 10;
	bool typeDesc = 11;
	bool ttlAsc = 12;
	bool ttlDesc = 13;

	int64 offset = 5;
	int64 size = 6;
}</code></pre> |
| _**输出对象：ListNSRecordsResponse：**_                                                                                                                                                                                                                                                                                                                                         |
| <pre><code>message ListNSRecordsResponse {
	repeated NSRecord nsRecords = 1;
}</code></pre>                                                                                                                                                                                                                                                                               |

| 查询单个记录信息 adminRPC findNSRecord _(FindNSRecordRequest)_ returns _(FindNSRecordResponse)_HTTP POST /NSRecordService/findNSRecord |
| ------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：FindNSRecordRequest：**_                                                                                                |
| <pre><code>message FindNSRecordRequest {
	int64 nsRecordId = 1;
}</code></pre>                                                 |
| _**输出对象：FindNSRecordResponse：**_                                                                                               |
| <pre><code>message FindNSRecordResponse {
	NSRecord nsRecord = 1;
}</code></pre>                                               |

| 根据版本列出一组记录 dnsRPC listNSRecordsAfterVersion _(ListNSRecordsAfterVersionRequest)_ returns _(ListNSRecordsAfterVersionResponse)_HTTP POST /NSRecordService/listNSRecordsAfterVersion |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListNSRecordsAfterVersionRequest：**_                                                                                                                                       |
| <pre><code>message ListNSRecordsAfterVersionRequest {
	int64 version = 1;
	int64 size = 2;
}</code></pre>                                                                          |
| _**输出对象：ListNSRecordsAfterVersionResponse：**_                                                                                                                                      |
| <pre><code>message ListNSRecordsAfterVersionResponse {
	repeated NSRecord nsRecords = 1;
}</code></pre>                                                                            |
