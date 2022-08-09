# Better alpine

## Testing the empty image

When running this alpine directly, vim and curl are not installed.  
(although vi is there).  

```
=> 
=> docker run -it myalpine:3.4
/ # 
/ # vi
/ # vim
/bin/sh: vim: not found
/ # curl
/bin/sh: curl: not found
/ # 
/ # exit
=> 
=> 
```

## Creating and testing the better image

The new Dockerfile adds more commands to install **vim** and **curl**.  
The **apl** (alpine package) is a library manager used in alpine.  

```
=> 
=> docker build -t betteralpine .
Sending build context to Docker daemon  3.072kB
Step 1/4 : FROM  alpine:3.4
 ---> b7c5ffe56db7
Step 2/4 : RUN apk update
 ---> Running in 67075e41f836
fetch http://dl-cdn.alpinelinux.org/alpine/v3.4/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.4/community/x86_64/APKINDEX.tar.gz

. . .
. . .
Step 4/4 : RUN apk add curl
 ---> Running in 3645d4c44309
. . .
. . .
Successfully built 22fe5f9db4b8
Successfully tagged betteralpine:latest
=> 
=> 
=> docker run -it betteralpine:latest
/ # 
/ # vim
/ # curl google.com
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="http://www.google.com/">here</A>.
</BODY></HTML>
/ # 
/ # exit
=> ^C
=> 
