# Domain-status
## Python - This code is written to check the status of domains. We can use this code as a cron to check whether the domains are active or not.

```python
import requests
import time



start = time.time()


urls = [
  'https://www.javatpoint.com/',
  'https://www.guru99.com/',
  'https://www.tutorialspoint.com',
  'https://ryanstutorials.net/',
  'https://www.linux.org',
  'https://linuxconfig.org',
  'https://www.tecmint.com/'
]

status = {}

for url in urls:
    try:
        response = requests.get(url,timeout=2)
        status[url] = response.status_code
    except:
        pass

end = time.time()
    
for item in status:
    code = status[item]
    if response.status_code == requests.codes.OK:
        print('The domain {:20} is active and the status code is {}'.format(item,code))

print()
print('the total time taken to execute the code is {}'.format(end - start))
```
