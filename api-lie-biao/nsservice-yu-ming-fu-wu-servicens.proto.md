# NSService - 域名服务 service\_ns.proto

#### 方法列表

* composeNSBoard - 组合看板数据

| 组合看板数据 adminRPC composeNSBoard _(ComposeNSBoardRequest)_ returns _(ComposeNSBoardResponse)_HTTP POST /NSService/composeNSBoard                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ComposeNSBoardRequest：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| <pre><code>message ComposeNSBoardRequest {

}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| _**输出对象：ComposeNSBoardResponse：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| <pre><code>message ComposeNSBoardResponse {
	int64 countNSDomains = 1;
	int64 countNSRecords = 2;
	int64 countNSClusters = 3;
	int64 countNSNodes = 4;
	int64 countOfflineNSNodes = 5;

	repeated DailyTrafficStat dailyTrafficStats = 30;
	repeated HourlyTrafficStat hourlyTrafficStats = 31;
	repeated NodeStat topNSNodeStats = 32;
	repeated DomainStat topNSDomainStats = 33;
	repeated NodeValue cpuNodeValues = 34;
	repeated NodeValue memoryNodeValues = 35;
	repeated NodeValue loadNodeValues = 36;


	message DailyTrafficStat {
		string day = 1;
		int64 bytes = 2;
		int64 countRequests = 3;
	}


	message HourlyTrafficStat {
		string hour = 1;
		int64 bytes = 2;
		int64 countRequests = 3;
	}


	message NodeStat {
		int64 nsClusterId = 1;
		int64 nsNodeId = 2;
		string nsNodeName = 3;
		int64 countRequests = 4;
		int64 bytes = 5;
	}


	message DomainStat {
		int64 nsDomainId = 1;
		string nsDomainName = 2;
		int64 countRequests = 3;
		int64 bytes = 4;
	}
}</code></pre> |

\
