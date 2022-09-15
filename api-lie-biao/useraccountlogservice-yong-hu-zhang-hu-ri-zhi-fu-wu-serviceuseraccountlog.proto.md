# UserAccountLogService - 用户账户日志服务 service\_user\_account\_log.proto

#### 方法列表

* countUserAccountLogs - 计算日志数量
* listUserAccountLogs - 列出单页日志

| 计算日志数量 adminuserRPC countUserAccountLogs _(CountUserAccountLogsRequest)_ returns _(RPCCountResponse)_HTTP POST /UserAccountLogService/countUserAccountLogs |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountUserAccountLogsRequest：**_                                                                                                                    |
| <pre><code>message CountUserAccountLogsRequest {
	int64 userAccountId = 1;
	string keyword = 2;
	string eventType = 3;
}</code></pre>                      |
| _**输出对象：RPCCountResponse：**_                                                                                                                               |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                     |

| 列出单页日志 adminuserRPC listUserAccountLogs _(ListUserAccountLogsRequest)_ returns _(ListUserAccountLogsResponse)_HTTP POST /UserAccountLogService/listUserAccountLogs       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：ListUserAccountLogsRequest：**_                                                                                                                                   |
| <pre><code>message ListUserAccountLogsRequest {
	int64 userAccountId = 1;
	string keyword = 2;
	string eventType = 3;
	int64 offset = 4;
	int64 size = 5;
}</code></pre> |
| _**输出对象：ListUserAccountLogsResponse：**_                                                                                                                                  |
| <pre><code>message ListUserAccountLogsResponse {
	repeated UserAccountLog userAccountLogs = 1;
}</code></pre>                                                            |

\
