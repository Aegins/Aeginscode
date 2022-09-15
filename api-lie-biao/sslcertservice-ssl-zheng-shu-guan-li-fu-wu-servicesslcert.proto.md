# SSLCertService - SSL证书管理服务 service\_ssl\_cert.proto

#### 方法列表

* createSSLCert - 创建Cert
* updateSSLCert - 修改Cert
* deleteSSLCert - 删除Cert
* findEnabledSSLCertConfig - 查找证书配置
* countSSLCerts - 计算匹配的Cert数量
* listSSLCerts - 列出单页匹配的Cert
* countAllSSLCertsWithOCSPError - 计算有OCSP错误的证书数量
* listSSLCertsWithOCSPError - 列出有OCSP错误的证书
* ignoreSSLCertsWithOCSPError - 忽略一组OCSP证书错误
* resetSSLCertsWithOCSPError - 重置一组证书OCSP错误状态
* resetAllSSLCertsWithOCSPError - 重置所有证书OCSP错误状态
* listUpdatedSSLCertOCSP - 读取证书的OCSP

| 创建Cert adminuserRPC createSSLCert _(CreateSSLCertRequest)_ returns _(CreateSSLCertResponse)_HTTP POST /SSLCertService/createSSLCert                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateSSLCertRequest：**_                                                                                                                                                                                                                                                                                                                                                          |
| <pre><code>message CreateSSLCertRequest {
	bool isOn = 1;
	string name = 2;
	string description = 3;
	string serverName = 4;
	bool isCA = 5;
	bytes certData = 6;
	bytes keyData = 7;
	int64 timeBeginAt = 8;
	int64 timeEndAt = 9;
	repeated string dnsNames = 10;
	repeated string commonNames = 11;
}</code></pre><p><a href="https://goedge.cn/docs/API/proto3.md">理解proto3协议</a></p> |
| _**输出对象：CreateSSLCertResponse：**_                                                                                                                                                                                                                                                                                                                                                         |
| <pre><code>message CreateSSLCertResponse {
	int64 sslCertId = 1;
}</code></pre>                                                                                                                                                                                                                                                                                                           |

| 修改Cert adminuserRPC updateSSLCert _(UpdateSSLCertRequest)_ returns _(RPCSuccess)_HTTP POST /SSLCertService/updateSSLCert                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateSSLCertRequest：**_                                                                                                                                                                                                                                                                                                             |
| <pre><code>message UpdateSSLCertRequest {
	int64 sslCertId = 1;
	bool isOn = 2;
	string name = 3;
	string description = 4;
	string serverName = 5;
	bool isCA = 6;
	bytes certData = 7;
	bytes keyData = 8;
	int64 timeBeginAt = 9;
	int64 timeEndAt = 10;
	repeated string dnsNames = 11;
	repeated string commonNames = 12;
}</code></pre> |
| _**输出对象：RPCSuccess：**_                                                                                                                                                                                                                                                                                                                       |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                                                                                                                                                                                              |

| 删除Cert adminuserRPC deleteSSLCert _(DeleteSSLCertRequest)_ returns _(RPCSuccess)_HTTP POST /SSLCertService/deleteSSLCert |
| ------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：DeleteSSLCertRequest：**_                                                                                         |
| <pre><code>message DeleteSSLCertRequest {
	int64 sslCertId = 1;
}</code></pre>                                           |
| _**输出对象：RPCSuccess：**_                                                                                                   |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                          |

| 查找证书配置 adminuserRPC findEnabledSSLCertConfig _(FindEnabledSSLCertConfigRequest)_ returns _(FindEnabledSSLCertConfigResponse)_HTTP POST /SSLCertService/findEnabledSSLCertConfig |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledSSLCertConfigRequest：**_                                                                                                                                     |
| <pre><code>message FindEnabledSSLCertConfigRequest {
	int64 sslCertId = 1;
}</code></pre>                                                                                       |
| _**输出对象：FindEnabledSSLCertConfigResponse：**_                                                                                                                                    |
| <pre><code>message FindEnabledSSLCertConfigResponse {
	bytes sslCertJSON = 1;
}</code></pre>                                                                                    |

| 计算匹配的Cert数量 adminuserRPC countSSLCerts _(CountSSLCertRequest)_ returns _(RPCCountResponse)_HTTP POST /SSLCertService/countSSLCerts                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：CountSSLCertRequest：**_                                                                                                                                                      |
| <pre><code>message CountSSLCertRequest {
	bool isCA = 1;
	bool isAvailable = 2;
	bool isExpired = 3;
	int32 expiringDays = 4;
	string keyword = 5;
	int64 userId = 6;
}</code></pre> |
| _**输出对象：RPCCountResponse：**_                                                                                                                                                         |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                                               |

| 列出单页匹配的Cert adminuserRPC listSSLCerts _(ListSSLCertsRequest)_ returns _(ListSSLCertsResponse)_HTTP POST /SSLCertService/listSSLCerts                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _**输入对象：ListSSLCertsRequest：**_                                                                                                                                                                                          |
| <pre><code>message ListSSLCertsRequest {
	bool isCA = 1;
	bool isAvailable = 2;
	bool isExpired = 3;
	int32 expiringDays = 4;
	string keyword = 5;
	int64 offset = 6;
	int64 size = 7;
	int64 userId = 8;
}</code></pre> |
| _**输出对象：ListSSLCertsResponse：**_                                                                                                                                                                                         |
| <pre><code>message ListSSLCertsResponse {
	bytes sslCertsJSON = 1;
}</code></pre>                                                                                                                                        |

| 计算有OCSP错误的证书数量 adminRPC countAllSSLCertsWithOCSPError _(CountAllSSLCertsWithOCSPErrorRequest)_ returns _(RPCCountResponse)_HTTP POST /SSLCertService/countAllSSLCertsWithOCSPError |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CountAllSSLCertsWithOCSPErrorRequest：**_                                                                                                                                   |
| <pre><code>message CountAllSSLCertsWithOCSPErrorRequest {
	string keyword = 1;
}</code></pre>                                                                                      |
| _**输出对象：RPCCountResponse：**_                                                                                                                                                       |
| <pre><code>message RPCCountResponse {
	int64 count = 1;
}</code></pre>                                                                                                             |

| 列出有OCSP错误的证书 adminRPC listSSLCertsWithOCSPError _(ListSSLCertsWithOCSPErrorRequest)_ returns _(ListSSLCertsWithOCSPErrorResponse)_HTTP POST /SSLCertService/listSSLCertsWithOCSPError |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListSSLCertsWithOCSPErrorRequest：**_                                                                                                                                          |
| <pre><code>message ListSSLCertsWithOCSPErrorRequest {
	string keyword = 1;
	int64 offset = 2;
	int64 size = 3;
}</code></pre>                                                         |
| _**输出对象：ListSSLCertsWithOCSPErrorResponse：**_                                                                                                                                         |
| <pre><code>message ListSSLCertsWithOCSPErrorResponse {
	repeated SSLCert sslCerts = 1;
}</code></pre>                                                                                 |

| 忽略一组OCSP证书错误 adminRPC ignoreSSLCertsWithOCSPError _(IgnoreSSLCertsWithOCSPErrorRequest)_ returns _(RPCSuccess)_HTTP POST /SSLCertService/ignoreSSLCertsWithOCSPError |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：IgnoreSSLCertsWithOCSPErrorRequest：**_                                                                                                                       |
| <pre><code>message IgnoreSSLCertsWithOCSPErrorRequest {
	repeated int64 sslCertIds = 1;
}</code></pre>                                                               |
| _**输出对象：RPCSuccess：**_                                                                                                                                               |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                      |

| 重置一组证书OCSP错误状态 adminRPC resetSSLCertsWithOCSPError _(ResetSSLCertsWithOCSPErrorRequest)_ returns _(RPCSuccess)_HTTP POST /SSLCertService/resetSSLCertsWithOCSPError |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ResetSSLCertsWithOCSPErrorRequest：**_                                                                                                                       |
| <pre><code>message ResetSSLCertsWithOCSPErrorRequest {
	repeated int64 sslCertIds = 1;
}</code></pre>                                                               |
| _**输出对象：RPCSuccess：**_                                                                                                                                              |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                     |

| 重置所有证书OCSP错误状态 adminRPC resetAllSSLCertsWithOCSPError _(ResetAllSSLCertsWithOCSPErrorRequest)_ returns _(RPCSuccess)_HTTP POST /SSLCertService/resetAllSSLCertsWithOCSPError |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ResetAllSSLCertsWithOCSPErrorRequest：**_                                                                                                                             |
| <pre><code>message ResetAllSSLCertsWithOCSPErrorRequest {

}</code></pre>                                                                                                    |
| _**输出对象：RPCSuccess：**_                                                                                                                                                       |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                                                              |

| 读取证书的OCSP nodeRPC listUpdatedSSLCertOCSP _(ListUpdatedSSLCertOCSPRequest)_ returns _(ListUpdatedSSLCertOCSPResponse)_HTTP POST /SSLCertService/listUpdatedSSLCertOCSP                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：ListUpdatedSSLCertOCSPRequest：**_                                                                                                                                                                                  |
| <pre><code>message ListUpdatedSSLCertOCSPRequest {
	int64 version = 1;
	int32 size = 2;
}</code></pre>                                                                                                                     |
| _**输出对象：ListUpdatedSSLCertOCSPResponse：**_                                                                                                                                                                                 |
| <pre><code>message ListUpdatedSSLCertOCSPResponse {
	repeated SSLCertOCSP sslCertOCSP = 1;


	message SSLCertOCSP {
		int64 sslCertId = 1;
		bytes data = 2;
		int64 version = 3;
		int64 expiresAt = 4;
	}
}</code></pre> |
