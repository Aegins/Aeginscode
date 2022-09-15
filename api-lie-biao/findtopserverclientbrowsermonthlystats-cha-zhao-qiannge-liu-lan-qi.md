# findTopServerClientBrowserMonthlyStats - 查找前N个浏览器

#### 方法列表

* findTopServerClientBrowserMonthlyStats - 查找前N个浏览器

| 查找前N个浏览器 adminuserRPC findTopServerClientBrowserMonthlyStats _(FindTopServerClientBrowserMonthlyStatsRequest)_ returns _(FindTopServerClientBrowserMonthlyStatsResponse)_HTTP POST /ServerClientBrowserMonthlyStatService/findTopServerClientBrowserMonthlyStats |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindTopServerClientBrowserMonthlyStatsRequest：**_                                                                                                                                                                                                        |
| <pre><code>message FindTopServerClientBrowserMonthlyStatsRequest {
	int64 serverId = 1;
	string month = 2;
	int64 offset = 3;
	int64 size = 4;
}</code></pre>                                                                                                    |
| _**输出对象：FindTopServerClientBrowserMonthlyStatsResponse：**_                                                                                                                                                                                                       |
| <pre><code>message FindTopServerClientBrowserMonthlyStatsResponse {
	repeated Stat stats = 1;


	message Stat {
		ClientBrowser clientBrowser = 1;
		string version = 2;
		int64 count = 3;
	}
}</code></pre>                                                    |

\
