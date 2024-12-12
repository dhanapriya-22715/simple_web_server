6 # EX01 Developing a Simple Webserver

# Date: 04-10-2024
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Configuration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            line-height: 1.6;
        }
        .config-table {
            border-collapse: collapse;
            width: 100%;
            margin-top: 20px;
        }
        .config-table th, .config-table td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: left;
        }
        .config-table th {
            background-color: #f4f4f4;
        }
        .config-title {
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <div>
        <p class="config-title">Laptop Configuration Details</p>
        <table class="config-table">
            <tr>
                <th>Component</th>
                <th>Details</th>
            </tr>
            <tr>
                <td>Processor</td>
                <td>Intel Core i7-11800H</td>
            </tr>
            <tr>
                <td>RAM</td>
                <td>16GB DDR4</td>
            </tr>
            <tr>
                <td>Storage</td>
                <td>512GB NVMe SSD</td>
            </tr>
            <tr>
                <td>Graphics</td>
                <td>NVIDIA GeForce RTX 3060</td>
            </tr>
            <tr>
                <td>Display</td>
                <td>15.6-inch, 1920x1080, 144Hz</td>
            </tr>
            <tr>
                <td>Operating System</td>
                <td>Windows 11 Home</td>
            </tr>
        </table>
    </div>
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
print("my webserver id running....")
httpd.serve_forever()
```
# OUTPUT:
![Screenshot (40)](https://github.com/user-attachments/assets/81b946dc-ddc8-4273-b0e7-4132c5023fcf)

![Screenshot (41)](https://github.com/user-attachments/assets/26128158-c158-4589-b347-4c2076960afa)

![Screenshot (42)](https://github.com/user-attachments/assets/d4f0ecf6-a408-4b71-a4bc-30b704054f09)

# RESULT:
The program for implementing simple webserver is executed successfully.
