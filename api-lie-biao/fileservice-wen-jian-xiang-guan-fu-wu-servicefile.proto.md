# FileService - 文件相关服务 service\_file.proto

#### 方法列表

* findEnabledFile - 查找文件
* createFile - 创建文件
* updateFileFinished - 将文件置为已完成

| 查找文件 adminuserRPC findEnabledFile _(FindEnabledFileRequest)_ returns _(FindEnabledFileResponse)_HTTP POST /FileService/findEnabledFile |
| -------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：FindEnabledFileRequest：**_                                                                                                     |
| <pre><code>message FindEnabledFileRequest {
	int64 fileId = 1;
}</code></pre>                                                          |
| _**输出对象：FindEnabledFileResponse：**_                                                                                                    |
| <pre><code>message FindEnabledFileResponse {
	File file = 1;
}</code></pre>                                                            |

| 创建文件 adminuserRPC createFile _(CreateFileRequest)_ returns _(CreateFileResponse)_HTTP POST /FileService/createFile                                       |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：CreateFileRequest：**_                                                                                                                            |
| <pre><code>message CreateFileRequest {
	string filename = 1;
	int64 size = 2;
	bool isPublic = 3;
	string mimeType = 4;
	string type = 5;
}</code></pre> |
| _**输出对象：CreateFileResponse：**_                                                                                                                           |
| <pre><code>message CreateFileResponse {
	int64 fileId = 1;
}</code></pre>                                                                                |

| 将文件置为已完成 adminuserRPC updateFileFinished _(UpdateFileFinishedRequest)_ returns _(RPCSuccess)_HTTP POST /FileService/updateFileFinished |
| -------------------------------------------------------------------------------------------------------------------------------------- |
| _**输入对象：UpdateFileFinishedRequest：**_                                                                                                  |
| <pre><code>message UpdateFileFinishedRequest {
	int64 fileId = 1;
}</code></pre>                                                       |
| _**输出对象：RPCSuccess：**_                                                                                                                 |
| <pre><code>message RPCSuccess {

}</code></pre>                                                                                        |

\
