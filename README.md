# SimulateLogin
模拟登陆知乎

```python
#coding:utf-8
#模拟登陆

import requests
import urllib

#请求的地址
postUrl = 'https://www.zhihu.com/login/phone_num'
#请求头
headers = {'User-Agent':"Mozilla/5.0 (Windows NT 10.0; WOW64; rv:51.0) Gecko/20100101 Firefox/51.0",
			'Referer':'https://www.zhihu.com/'}
#发送的参数
value = {'password':'你的密码','phone_num':'你的账号'}
data = urllib.parse.urlencode(value).encode(encoding='UTF8')
#发送请求
request = urllib.request.Request(postUrl , data , headers)
#解析响应的信息
result = urllib.request.urlopen(request)
print(result.read().decode())
```
	图一：
![登陆成功](https://git.oschina.net/niithub/images/raw/master/1.png?dir=0&filepath=1.png&oid=6a46cefcab24f1447e751861edd7c2c2962f8b7c&sha=6a69be413afeaccf1ee59d0748b399d763d6da84 "登陆成功")

	图二：
![登陆失败](https://git.oschina.net/niithub/images/raw/master/error1.png?dir=0&filepath=error1.png&oid=dd55e4e0dd7341278bee5605575cd8969b45cee0&sha=6a69be413afeaccf1ee59d0748b399d763d6da84 "没有输入密码这一项")

	图三:
![登陆失败](https://git.oschina.net/niithub/images/raw/master/error2.png?dir=0&filepath=error2.png&oid=fba856669060e4803a3893d000dfdd2d9a209773&sha=6a69be413afeaccf1ee59d0748b399d763d6da84 "密码输入错误")
