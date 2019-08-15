# 笔记
## 安装并且为最新requests
- import requests
 导入模块
- r = requests.get()
 利用.get来获取所有我们想要的信息储存到名为r的response对象中
- r = requests.post(url,data = {'key':'value'})
-  r = requests.delete('http://httpbin.org/delete')
 ...
 .post/.put/.delets/.head/.options等http请求类型
- payload = {'key1': 'value1', 'key2': 'value2'}
- r = requests.get("http://httpbin.org/get", params=payload)
 允许使用params关键字参数，以字符串字典来提供这些参数。
- r.text
- requests自动解码来自服务器内容。
- r.encoding
- r.encoding = utf8
- 查看response的文本编码并且可以对其进行更改。
- r.content
- 以字节的方式访问请求
- from PIL import Image
- from io import BytesIO
- i = Image.open(ByteIO(r.content))
- 以返回的二进制数据创建一张图片
- r.json()
- requests内置JSON解码器，如果解码失败会有错误401，尝试访问r.json会有Valueerror异常。成功调用也不意味着成功，有的失败响应中也带有JSON对象，可以用r.status_code检查
- headers = {
    'user-agent':'blabla'
}
- r = requests.get(url,headers = headers)
- 定制http的请求头
- r.status_code
- 响应状态码
- requests.get(url,headers = headers,timeout=0.01)
- 设置超时，服务器在timeout秒无应答就停止响应。
- cookies = dict(cookies_are='working')
- r = requests.get(url, cookies=cookies)
- 发送cookies
## 错误与异常
- ConnectionError为网络问题
- 如果 HTTP 请求返回了不成功的状态码， Response.raise_for_status() 会抛出一个 HTTPError 异常。
- 若请求超时，则抛出一个 Timeout 异常。
- 