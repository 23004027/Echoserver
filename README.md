# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
# Server code:
```
import socket


HOST = "192.168.109.189"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```
# Client Code:
```
import socket


HOST = "192.168.109.189"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"vignesh,212223230241")
    data = s.recv(1024)


print(f"Received {data!r}")
```

## OUTPUT:
![Screenshot 2025-03-06 113516](https://github.com/user-attachments/assets/5672f926-48a4-4c44-9e0c-10eb7a2888fe)
![Screenshot 2025-03-06 114013](https://github.com/user-attachments/assets/c66d8014-8758-4463-8d9a-7bd433fd8c1e)



## RESULT:
The program is executed successfully
