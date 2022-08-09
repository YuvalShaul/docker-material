# Empty alpine

## Creating image

The alpine Linux image is a small and often used distribution of Linux.  
Let's create our own image:  
```
=> 
=> docker build  -t myalpine:3.4  .
Sending build context to Docker daemon  3.072kB
Step 1/1 : FROM  alpine:3.4
3.4: Pulling from library/alpine
c1e54eec4b57: Pull complete 
Digest: sha256:b733d4a32c4da6a00a84df2ca32791bb03df95400243648d8c539e7b4cce329c
Status: Downloaded newer image for alpine:3.4
 ---> b7c5ffe56db7
Successfully built b7c5ffe56db7
Successfully tagged myalpine:3.4
=> 
```

## Run an alpine container

```
=> 
=> docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
alpine       3.4       b7c5ffe56db7   3 years ago   4.82MB
myalpine     3.4       b7c5ffe56db7   3 years ago   4.82MB
=> 
=> docker run -it myalpine:3.4
/ # ls
bin      dev      etc      home     lib      linuxrc  media    mnt      proc     root     run      sbin     srv      sys      tmp      usr      var
/ # uname -a
Linux 50a2d8daf40c 5.15.0-43-generic #46-Ubuntu SMP Tue Jul 12 10:30:17 UTC 2022 x86_64 Linux
/ # exit
=> 
=> 
```
