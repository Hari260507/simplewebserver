# EX01 Developing a Simple Webserver
## Date:24/10/2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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

from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body align="center">
    <h1>MY LAPTOP CONFIGURATION</h1>
<table border="5" cellbadding="100" width="50%" align="center">
        <tr>
            <th>Configuration</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel(R) Core(TM) i5-8350U CPU @ 1.70GHz   1.90 GHzx
            </td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>8.00 GB (7.85 GB usable)</td>
        </tr>
        <tr>
            <td>system type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Device ID
            </td>
            <td>2A191FB8-5571-4CE6-A3E1-F9486DE092C5</td>
        </tr>
        <tr>
            <td>Pen and Touch
            </td>
            <td>No pen or touch input is available for this display</td>
        </tr>
        <tr>
            <td>Graphic Processor</td>
            <td>NVIDIA GeForce RTX 2050</td>
        </tr>
    </table>
</body>
</html>

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

## OUTPUT:
![alt text](<Screenshot 2024-10-26 105102.png>)
![alt text](<Screenshot 2024-10-26 105224.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
