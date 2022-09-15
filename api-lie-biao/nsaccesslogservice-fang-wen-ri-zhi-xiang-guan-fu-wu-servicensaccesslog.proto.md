# NSAccessLogService - 访问日志相关服务 service\_ns\_access\_log.proto

#### 方法列表

* createNSAccessLogs - 创建访问日志
* listNSAccessLogs - 列出单页访问日志
* findNSAccessLog - 查找单个日志

| 创建访问日志 dnsRPC createNSAccessLogs _(CreateNSAccessLogsRequest)_ returns _(CreateNSAccessLogsResponse)_HTTP POST /NSAccessLogService/createNSAccessLogs |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateNSAccessLogsRequest：**_                                                                                                                 |
| <pre><code>message CreateNSAccessLogsRequest {
	repeated NSAccessLog nsAccessLogs = 1;
}</code></pre>                                                 |
| _**输出对象：CreateNSAccessLogsResponse：**_                                                                                                                |
| <pre><code>message CreateNSAccessLogsResponse {

}</code></pre>                                                                                       |

| 列出单页访问日志 adminuserRPC listNSAccessLogs _(ListNSAccessLogsRequest)_ returns _(ListNSAccessLogsResponse)_HTTP POST /NSAccessLogService/listNSAccessLogs                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListNSAccessLogsRequest：**_                                                                                                                                                                                                                                                                                                                                               |
| <pre><code>message ListNSAccessLogsRequest {
	string requestId = 1; // 上一页请求ID，可选
	int64 nsClusterId = 9; // 集群
	int64 nsNodeId = 2; // 节点ID
	int64 nsDomainId = 3; // 域名ID
	int64 nsRecordId = 4; // 记录ID
	int64 size = 5; // 单页条数
	string day = 6; // 日期，格式YYYYMMDD
	bool reverse = 7; // 是否反向查找，可选
	string keyword = 8; // 关键词
	string recordType = 10; // 记录类型
}</code></pre> |
| _**输出对象：ListNSAccessLogsResponse：**_                                                                                                                                                                                                                                                                                                                                              |
| <pre><code>message ListNSAccessLogsResponse {
	repeated NSAccessLog nsAccessLogs = 1;
	string requestId = 2;
	bool hasMore = 3;
}</code></pre>                                                                                                                                                                                                                                    |

| 查找单个日志 adminuserRPC findNSAccessLog _(FindNSAccessLogRequest)_ returns _(FindNSAccessLogResponse)_HTTP POST /NSAccessLogService/findNSAccessLog |
| ----------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindNSAccessLogRequest：**_                                                                                                              |
| <pre><code>message FindNSAccessLogRequest {
	string requestId = 1;
}</code></pre>                                                               |
| _**输出对象：FindNSAccessLogResponse：**_                                                                                                             |
| <pre><code>message FindNSAccessLogResponse {
	NSAccessLog nsAccessLog = 1;
}</code></pre>                                                       |
