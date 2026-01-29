# Change Log

## 0.9.2

### Added
- For server-side HTTP request parsing, including the status line, response headers, and response body. If response body is compressed, the variable  **RESPONSE_BODY** stores the response body as raw hex data.

    在服务器侧解析http请求，包括状态行，响应头，响应体。如果响应体被压缩，则响应体变量 **RESPONSE_BODY** 存放16进制格式的原始数据。

### Fixed

### Changed
- change variables name in http_parser_clientside.irul, in order to distinguish the similar properties on sides client and server

    修改http_parser_clientside.irul中的变量名，以区分客户端和服务端类似的属性

### Removed


## 0.9.1

### Added
- For client-side HTTP request parsing, including the request line, request headers, and request body.

    在客户侧解析http请求，包括请求行，请求头，请求体。
- "Insert X-Forwarded-For" function implemented.

    实现插入X-Forwarded-For功能。

### Fixed

### Changed

### Removed