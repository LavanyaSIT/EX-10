# EX-10 APPLICATION USING TCP SOCKETS - FILE TRANSFER PROGRAM

# DATE :11-05-2023

# AIM :
To write a python program for creating File Transfer using TCP Sockets Links.

# ALGORITHM :
Start the program.
Get the frame size from the user.
To create the frame based on the user request.
To send frames to server from the client side.
If your frames reach the server, it will send ACK signal to client otherwise it will sendNACK signal to client.
Stop the program
# PROGRAM :
# CLIENT :
Developed By :Lavanya S

Register Number :212221220030
```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
    while True:
        print('receiving data...')
        data = s.recv(1024)
        print('data=%s', (data))
        if not data:
            break
        f.write(data)
f.close()
print('Successfully get the file')
s.close()
print('connection closed')
```
# SERVER :
Developed By : Lavanya S

Register Number :212221220030
```
import socket
port = 60000
s = socket.socket()
host = socket.gethostname()
s.bind((host, port))
s.listen(5)
while True:
    conn, addr = s.accept()
    data = conn.recv(1024)
    print('Server received', repr(data))
    filename='mytext.txt'
    f = open(filename,'rb')
    l = f.read(1024)
    while (l):
        conn.send(l)
        print('Sent ',repr(l))
        l = f.read(1024)
    f.close()
    print('Done sending')
    conn.send('Thank you for connecting'.encode())
    conn.close()
    ```
# OUTPUT :
# CLIENT :

![image](https://github.com/LavanyaSIT/EX-10/assets/130207418/cb97b12d-1f06-427d-9945-4bf38d8b379f)


# SERVER :

![image](https://github.com/LavanyaSIT/EX-10/assets/130207418/b4ef819d-0373-4460-ba6d-d59cb7147f7a)



# RESULT :
Thus, the python program for creating File Transfer using TCP Sockets Links was successfully created and executed.

