### Python发送Request请求的方法（待测试）
1. get
```python
url = ''
headers = {
    'Content-Type' : 'application/json',
    'Authorization' : token,
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
request.add_header('Authorization', token)
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
request.add_header('Authorization', token)
request.get_method = lambda:' PUT'
response = urllib2.urlopen(request)
print response.read()
```
4. delete
```python
url = ''
request = urllib2.Request(url)
request.add_header('Content-Type', 'application/json')
request.add_header('Authorization', token)
request.get_method = lambda:' DELETE'
response = urllib2.urlopen(request)
print response.read()
```