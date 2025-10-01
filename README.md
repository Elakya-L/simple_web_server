# EX01 Developing a Simple Webserver

# Date:18-09-2025
# AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

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
content= '''
<html>
<head>
    <title>SIMPLE WEB SERVER</title>
    <style>
        * {background-color: blanchedalmond ;}
        body { font-family: 'Times New Roman', Times, serif; }
        h2 { color: #090909; }
        th { background: #8174b8; color:beige }  
        table { border-collapse: collapse; }
      
    </style>
</head>
<body>
    <h2>TCP/IP PROTOCOL SUITE</h2>
       <table BORDER="3" width="950" cellspacing="20" cellpadding="20" >
            <tr>
                <th>LAYERS</th>
                <th>LAYER NAME</th>
                <th>PROTOCOLS IN EACH LAYER</th>
                
            </tr>
            <tr>
                <td>1st Layer</td>
                <td>Application Layer</td>
                <td>HTTP, RDP, DNS, X WINDOWS, DHCP, FTP, TFTP, SNMP, SMTP, DNS, SSH, Telnet</td>
            </tr>
            <tr>
                <td>2nd Layer</td>
                <td>Transport Layer</td>
                <td>TCP, UDP</td>
            </tr>
            <tr>
                <td>3rd Layer</td>
                <td>Internet Layer</td>
                <td>IP (IPv4/IPv6), ICMP, ARP, IGMP</td>
            </tr>
            <tr>
                <td>4th Layer</td>
                <td>Network Access Layer</td>
                <td>Ethernet, X.25, FRAME RELAY, TOKEN RING, FDI</td>
            </tr>
      </table>
</body>
</html> '''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


# OUTPUT:
![alt text](<Screenshot (10).png>)

![alt text](<Screenshot (11).png>)




# RESULT:
The program for implementing simple webserver is executed successfully.
