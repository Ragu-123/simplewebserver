# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

# HTML content with a list of the top 5 revenue-generating companies
content = """
<!DOCTYPE html>
<html>
<head>
    <title>Top 5 Revenue-Generating Companies</title>
</head>
<body>
    <h1>Top 5 Revenue-Generating Companies</h1>
    <ol>
        <li>Apple Inc.</li>
        <li>Saudi Aramco</li>
        <li>Amazon.com Inc.</li>
        <li>Microsoft Corporation</li>
        <li>Alphabet Inc. (Google)</li>
    </ol>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('',80)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![output](https://github.com/Ragu-123/simplewebserver/assets/113915622/752f6b37-2845-4e4e-9a21-32251827c79d)
![output1](https://github.com/Ragu-123/simplewebserver/assets/113915622/589302c3-26b5-4a8f-b75e-ae401483d6ee)



## RESULT:
The program for implementing simple webserver is executed successfully.
