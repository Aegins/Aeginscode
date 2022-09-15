# ServerBandwidthStatService - 服务带宽统计服务 service\_server\_bandwidth\_stat.proto

#### 方法列表

* uploadServerBandwidthStats - 上传带宽统计
* findServerBandwidthStats - 获取服务的峰值带宽
* findHourlyServerBandwidthStats - 获取最近N小时峰值带宽
* findDailyServerBandwidthStats - 获取最近N天峰值带宽

| 上传带宽统计 nodeRPC uploadServerBandwidthStats _(UploadServerBandwidthStatsRequest)_ returns _(RPCSuccess)_HTTP POST /ServerBandwidthStatService/uploadServerBandwidthStats |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UploadServerBandwidthStatsRequest：**_                                                                                                                          |
| <pre><code>message UploadServerBandwidthStatsRequest {
	repeated ServerBandwidthStat serverBandwidthStats = 1;
}</code></pre>                                          |
| _**输出对象：RPCSuccess：**_                                                                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                        |

| 获取服务的峰值带宽 adminRPC findServerBandwidthStats _(FindServerBandwidthStatsRequest)_ returns _(FindServerBandwidthStatsResponse)_HTTP POST /ServerBandwidthStatService/findServerBandwidthStats |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：FindServerBandwidthStatsRequest：**_                                                                                                                                                |
| <pre><code>message FindServerBandwidthStatsRequest {
	int64 serverId = 1; // 服务ID
	string month = 2; // YYYYMM，month和day二选一
	string day = 3; // YYYYMMDD
}</code></pre>                    |
| _**输出对象：FindServerBandwidthStatsResponse：**_                                                                                                                                               |
| <pre><code>message FindServerBandwidthStatsResponse {
	repeated ServerBandwidthStat serverBandwidthStats = 1;
}</code></pre>                                                               |

| 获取最近N小时峰值带宽 adminRPC findHourlyServerBandwidthStats _(FindHourlyServerBandwidthStatsRequest)_ returns _(FindHourlyServerBandwidthStatsResponse)_HTTP POST /ServerBandwidthStatService/findHourlyServerBandwidthStats |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindHourlyServerBandwidthStatsRequest：**_                                                                                                                                                                    |
| <pre><code>message FindHourlyServerBandwidthStatsRequest {
	int64 serverId = 1;
	int32 hours = 2;
}</code></pre>                                                                                                     |
| _**输出对象：FindHourlyServerBandwidthStatsResponse：**_                                                                                                                                                                   |
| <pre><code>message FindHourlyServerBandwidthStatsResponse {
	repeated Stat stats = 1;


	message Stat {
		string day = 1;
		int32 hour = 2;
		int64 bytes = 3;
	}
}</code></pre>                                     |

| 获取最近N天峰值带宽 adminRPC findDailyServerBandwidthStats _(FindDailyServerBandwidthStatsRequest)_ returns _(FindDailyServerBandwidthStatsResponse)_HTTP POST /ServerBandwidthStatService/findDailyServerBandwidthStats |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindDailyServerBandwidthStatsRequest：**_                                                                                                                                                                |
| <pre><code>message FindDailyServerBandwidthStatsRequest {
	int64 serverId = 1;
	int32 days = 2;
}</code></pre>                                                                                                  |
| _**输出对象：FindDailyServerBandwidthStatsResponse：**_                                                                                                                                                               |
| <pre><code>message FindDailyServerBandwidthStatsResponse {
	repeated Stat stats = 1;


	message Stat {
		string day = 1;
		int64 bytes = 3;
	}
}</code></pre>                                                   |
