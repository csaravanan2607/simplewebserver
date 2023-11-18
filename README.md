# EX01 Developing a Simple Webserver
## Date: 05/10/23

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
<h1 align="center"><b>Top 5 Revenue Companies</b></h1><br>
    <table align="center" border="15" cellpadding="15" cellspacing="3">
        <tr>
            <th>Company name</th>
            <th>Location</th>
            <th>Yearly turn over</th>
        </tr>
        <tr>
            <td><ul>
                <li>Infosis</li>
                <br>
                <li>HCL</li>
                <br>
                <li>Wipro</li>
                <br>
                <li>Redington India Ltd</li>
                <br>
                <li>Tech Mahindra Limited</li>
            </ul></td>
            <td>
                <ul>
                    <li>chennai</li>
                    <br>
                    <li>chennai</li>
                    <br>
                    <li>chennai</li>
                    <br>
                    <li>chennai</li>
                    <br>
                    <li>chennai</li>
                </ul>
            </td>
            <td>
                <ul>
                    <li>123crore</li>
                    <br>
                    <li>1233crore</li>
                    <br>
                    <li>4165crore</li>
                    <br>
                    <li>4523crore</li>
                    <br>
                    <li>7456crore</li>
                </ul>
            </td>
        </tr>
    </table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![267843978-82d3a59b-993a-45cb-84ba-9a469c986e3b](https://github.com/NaveenSivamalai/simplewebserver/assets/123792574/cbc737ca-1327-4578-8fe0-d9fda4ebde21)
![267844040-4d9b6494-c58e-42ce-b850-41c3a52515bd](https://github.com/NaveenSivamalai/simplewebserver/assets/123792574/2aff6cd6-056b-4793-b527-4c48909600cf)


## RESULT:
The program for implementing simple webserver is executed successfully.
