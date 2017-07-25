### Python发送Request请求的方法（待测试）
1. get
```python
url = ''
headers = {
    'Content-Type' : 'application/json',
}
response = request('GET', url, headers=headers)
print response.read()
```
2. post
```python
url = ''
body = {
    'email' : 'emali@test',
}
pa = json.dumps(body)
request = urllib2.Request(url, pa)
request.add_header('Content-Type', 'application/json')
response = urllib2.urlopen(request)
print response.read()
```
3. put
```python
url = ""
body = {}
pa = json.dumps(body)
request = urllib2.Request(url, pa)
request.add_header('Content-Type', 'application/json')
request.get_method = lambda:'PUT'
response = urllib2.urlopen(request)
print response.read()
```
4. delete
```python
url = ''
request = urllib2.Request(url)
request.get_method = lambda:'DELETE'
response = urllib2.urlopen(request)
print response.read()
```

### 关于hearder的详细设置
取自请求github主页
```
Host: github.com
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:54.0) Gecko/20100101 Firefox/54.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
Upgrade-Insecure-Requests: 1
Connection: keep-alive
```
