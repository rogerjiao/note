### requests模块



1.安装
非常简单，打开cmd，直接pip安装,或pycharm 中搜索 requests 安装即可.

```
pip install requests
```

2.导入模块

```
import requests
```

3.简单使用

Get 请求

发送无参数的get请求,尝试获取某个网页.

```
r = requests.get('http://www.baidu.com')
```

发送无参数的get请求 设置超时时间 timeout 单位秒

```
r = requests.get('http://www.baidu.com', timeout=1)
```



定制请求头
如果你想为请求添加 HTTP 头部，只要简单地传递一个 dict 给 headers 参数就可以了

```
url = 'https://www.baidu.com/s?wd=python'
headers = {
        'Content-Type': 'text/html;charset=utf-8',
        'User-Agent' : 'Mozilla/5.0 (Windows NT 10.0; Win64; x64)'
    }
r = requests.get(url,headers=headers)
```



将一个列表作为值传入.

```
payload = {'key1': 'value1', 'key2': ['value2', 'value3']}
r = requests.get('http://www.baidu.com/', params=payload)
print(r.url)
http://www.baidu.com/?key2=value2&key2=value3&key1=value1
```



经常想为 URL 的查询字符串(query string) 传递某种数据

```
payload = {'key1': 'value1', 'key2': 'value2'}
r = requests.get("https://www.baidu.com/", params=payload)
print(r.url)
https://www.baidu.com/?key2=value2&key1=value1
```