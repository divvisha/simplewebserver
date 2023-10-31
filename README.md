# EX01 Developing a Simple Webserver
## Date: 16.09.2023

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Revenue Companies</h1>
    <ol>
        <li>Apple</li>
        <li>Google</li>
        <li>Amazon</li>
        <li>Samsung</li>
        <li>TATA</li>
    </ol>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
<img width="960" alt="Screenshot 2023-10-21 094535" src="https://github.com/divvisha/simplewebserver1/assets/127508123/b7050c90-8ae9-4596-9176-b9232f5438d3">

<img width="960" alt="Screenshot 2023-10-31 154654" src="https://github.com/divvisha/simplewebserver1/assets/127508123/483dd8df-a291-43f1-a4fb-2300cbafe50d">


## RESULT:
The program for implementing simple webserver is executed successfully.
