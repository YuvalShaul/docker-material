# Building a docker image from scratch

## Creating the executable

The very simple hellodocker.c file can be used to create a binary program.  
(You will need a compiler for that).  
The problem is that standard compilation will try to use a shared library that should be somewhere in the system.  
Example:  
```
=> gcc -o hello hellodocker.c 
=> ldd hello
	linux-vdso.so.1 (0x00007ffe47d5a000)
	libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f601ba53000)
	/lib64/ld-linux-x86-64.so.2 (0x00007f601bc91000)
=> 
```

We should instead make sure that all the needed binary is contained within the executable file:  

```
=> gcc -o hello **--** static hellodocker.c 
=> ldd hello
	not a dynamic executable
=> 
```

## Create and run the docker image

```
=> 
=> docker build .
Sending build context to Docker daemon  904.2kB
Step 1/3 : FROM scratch
 ---> 
Step 2/3 : COPY "hello" /
 ---> f417b4c0e76d
Step 3/3 : CMD ["/hello"]
 ---> Running in d60d715a6b4f
Removing intermediate container d60d715a6b4f
 ---> fa78e15e9be5
Successfully built fa78e15e9be5
=> 
=> docker run fa78e15e9be5
Hello Docker !!!
=> 
```