# ServerStatBoardService - 统计看板 service\_server\_stat\_board.proto

#### 方法列表

* findAllEnabledServerStatBoards - 读取所有看板
* composeServerStatNodeClusterBoard - 组合集群看板数据
* composeServerStatNodeBoard - 组合节点看板数据
* composeServerStatBoard - 组合服务看板数据

| 读取所有看板 adminRPC findAllEnabledServerStatBoards _(FindAllEnabledServerStatBoardsRequest)_ returns _(FindAllEnabledServerStatBoardsResponse)_HTTP POST /ServerStatBoardService/findAllEnabledServerStatBoards |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindAllEnabledServerStatBoardsRequest：**_                                                                                                                                                           |
| <pre><code>message FindAllEnabledServerStatBoardsRequest {
	int64 nodeClusterId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                     |
| _**输出对象：FindAllEnabledServerStatBoardsResponse：**_                                                                                                                                                          |
| <pre><code>message FindAllEnabledServerStatBoardsResponse {
	repeated ServerStatBoard serverStatBoards = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>              |

| 组合集群看板数据 adminRPC composeServerStatNodeClusterBoard _(ComposeServerStatNodeClusterBoardRequest)_ returns _(ComposeServerStatNodeClusterBoardResponse)_HTTP POST /ServerStatBoardService/composeServerStatNodeClusterBoard                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ComposeServerStatNodeClusterBoardRequest：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| <pre><code>message ComposeServerStatNodeClusterBoardRequest {
	int64 nodeClusterId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| _**输出对象：ComposeServerStatNodeClusterBoardResponse：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| <pre><code>message ComposeServerStatNodeClusterBoardResponse {
	int64 countActiveNodes = 1;
	int64 countInactiveNodes = 2;
	int64 countServers = 3;
	int64 countUsers = 4;

	repeated DailyTrafficStat dailyTrafficStats = 30;
	repeated HourlyTrafficStat hourlyTrafficStats = 31;
	repeated NodeStat topNodeStats = 32;

	repeated NodeValue cpuNodeValues = 34;
	repeated NodeValue memoryNodeValues = 35;
	repeated NodeValue loadNodeValues = 36;

	repeated MetricDataChart metricDataCharts = 37;


	message DailyTrafficStat {
		string day = 1;
		int64 bytes = 2;
		int64 cachedBytes = 3;
		int64 countRequests = 4;
		int64 countCachedRequests = 5;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}


	message HourlyTrafficStat {
		string hour = 1;
		int64 bytes = 2;
		int64 cachedBytes = 3;
		int64 countRequests = 4;
		int64 countCachedRequests = 5;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}


	message NodeStat {
		int64 nodeId = 1;
		string nodeName = 2;
		int64 countRequests = 3;
		int64 bytes = 4;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |

| 组合节点看板数据 adminRPC composeServerStatNodeBoard _(ComposeServerStatNodeBoardRequest)_ returns _(ComposeServerStatNodeBoardResponse)_HTTP POST /ServerStatBoardService/composeServerStatNodeBoard                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ComposeServerStatNodeBoardRequest：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| <pre><code>message ComposeServerStatNodeBoardRequest {
	int64 nodeId = 1;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| _**输出对象：ComposeServerStatNodeBoardResponse：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| <pre><code>message ComposeServerStatNodeBoardResponse {
	bool isActive = 1;
	int64 trafficInBytes = 2;
	int64 trafficOutBytes = 3;
	int64 countRequests = 4;
	int64 countAttackRequests = 5;
	int64 countConnections = 6;
	int64 cacheDiskSize = 7;
	int64 cacheMemorySize = 8;
	float cpuUsage = 9;
	float memoryUsage = 10;
	int64 memoryTotalSize = 11;
	float load = 12;

	repeated DailyTrafficStat dailyTrafficStats = 31;
	repeated HourlyTrafficStat hourlyTrafficStats = 32;

	repeated NodeValue cpuNodeValues = 34;
	repeated NodeValue memoryNodeValues = 35;
	repeated NodeValue loadNodeValues = 36;
	repeated NodeValue cacheDirsValues = 38;

	repeated MetricDataChart metricDataCharts = 37;


	message DailyTrafficStat {
		string day = 1;
		int64 bytes = 2;
		int64 cachedBytes = 3;
		int64 countRequests = 4;
		int64 countCachedRequests = 5;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}


	message HourlyTrafficStat {
		string hour = 1;
		int64 bytes = 2;
		int64 cachedBytes = 3;
		int64 countRequests = 4;
		int64 countCachedRequests = 5;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}
}</code></pre> |

| 组合服务看板数据 adminRPC composeServerStatBoard _(ComposeServerStatBoardRequest)_ returns _(ComposeServerStatBoardResponse)_HTTP POST /ServerStatBoardService/composeServerStatBoard                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ComposeServerStatBoardRequest：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <pre><code>message ComposeServerStatBoardRequest {
	int64 serverId = 1;
}</code></pre>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| _**输出对象：ComposeServerStatBoardResponse：**_                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <pre><code>message ComposeServerStatBoardResponse {
	int64 minutelyPeekBandwidthBytes = 5; // 当前带宽（N分钟峰值）
	int64 dailyPeekBandwidthBytes = 2; // 当天带宽峰值
	int64 monthlyPeekBandwidthBytes = 3; // 当月带宽峰值
	int64 lastMonthlyPeekBandwidthBytes = 4; // 上个月带宽峰值

	repeated ServerBandwidthStat minutelyBandwidthStats = 1; // 分钟级的带宽统计
	repeated ServerBandwidthStat dailyBandwidthStats = 6; // 按天的带宽统计
	repeated DailyTrafficStat dailyTrafficStats = 30;
	repeated HourlyTrafficStat hourlyTrafficStats = 31;
	repeated NodeStat topNodeStats = 32;
	repeated CountryStat topCountryStats = 35;

	repeated MetricDataChart metricDataCharts = 34;


	message DailyTrafficStat {
		string day = 1;
		int64 bytes = 2;
		int64 cachedBytes = 3;
		int64 countRequests = 4;
		int64 countCachedRequests = 5;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}


	message HourlyTrafficStat {
		string hour = 1;
		int64 bytes = 2;
		int64 cachedBytes = 3;
		int64 countRequests = 4;
		int64 countCachedRequests = 5;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}


	message NodeStat {
		int64 nodeId = 1;
		string nodeName = 2;
		int64 countRequests = 3;
		int64 bytes = 4;
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}


	message CountryStat {
		string countryName = 1;
		int64 bytes = 2;
		int64 countRequests = 3;
		float percent = 4; // 流量占比
		int64 countAttackRequests = 6;
		int64 attackBytes = 7;
	}
}</code></pre> |
