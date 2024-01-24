
#BeautifulSoup

import requests
page = requests.get("https://247ctf.com/scoreboard")
print(page.text)
from bs4 import BeautifulSoup
soup = BeautifulSoup(page.content, "html.parser")
print (soup.text)
print (soup.title)
print (soup.title.name)
print (soup.title.string)
print (soup.find("a"))
for line in soup.find_all("a"):
    print(line)
    print(line.get('href'))
table = soup.find("table")
print (table)
table_body = table.find("tbody")
rows = table_body.find_all("tr")
for row in rows:
    print("---")
    cols = [x.text.strip() for x in row.find_all("td")]
    print("{} is in {} place with {} points.".format(cols[2], cols[0], cols[4]))


#Py2Exe
?

#Sockets


```
import socket

  
  

ip = socket.gethostbyname('247ctf.com')

  

'print(ip)'

  

's = socket.socket(socket.AF_INET, socket.SOCK_STREAM)'

  

's.connect(("247ctf.com", 80))'

  

's.sendall(b"HEAD / HTTP 1.1\r\nHost: 247ctf.com\r\n\r\n")'

  

'print(s.recv(1024).decode())'

  

's.close()'

  
  

client = False

  

server = False

port = 8080

  

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

  

if server:

    s.bind(("127.0.0.1", port))

    s.listen()

    while True:

        connect, addr = s.accept()

        connect.send(b"You made it to the socket!")

        connect.close()

  

if client:

    s.connect(("127.0.0.1", port))

    print(s.recv(1024))

    s.close()

  
  

for port in [22, 80, 139, 443, 445, 8080]:

    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    socket.setdefaulttimeout(1)

    result = s.connect_ex(("127.0.0.1", port))

    if result == 0:

        print("{} is open!".format(port))

    else:

        print("{} is closed.".format(port))

    s.close()

```

#Scapy

