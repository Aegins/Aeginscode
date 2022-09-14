# APIAccessTokenService - AccessToken相关服务 service\_api\_access\_token.proto

* [GetAPIAccessToken - 获取AccessToken](https://goedge.cn/dev/api/service/APIAccessTokenService#GetAPIAccessToken)

| 获取AccessTokenRPC GetAPIAccessToken _(GetAPIAccessTokenRequest)_ returns _(GetAPIAccessTokenResponse)_HTTP POST /APIAccessTokenService/GetAPIAccessToken |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：GetAPIAccessTokenRequest：**_                                                                                                                    |
| <pre><code>message GetAPIAccessTokenRequest {
	string type = 1;
	string accessKeyId = 2;
	string accessKey = 3;
}</code></pre>                          |
| _**输出对象：GetAPIAccessTokenResponse：**_                                                                                                                   |
| <pre><code>message GetAPIAccessTokenResponse {
	string token = 1;
	int64 expiresAt = 2;
}</code></pre>                                                  |

\
