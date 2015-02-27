# Proxy


## How to configure docker when behind a proxy

> If you use docker behind a proxy you need to specify the corresponding environment variables to download images from internet. In my case I use docker on a mac os hence I use boot2docker Linux based virtual machine to host the docker process. Here are few simple steps to configure the proxy for boot2docker (version 1.1.1):

1. Login to the host vm
```
$ boot2docker ssh
```

2. find where the docker configuration is stored
```
$ docker@boot2docker:~$ ls -la /etc/init.d/docker
```

    OUTPUT
```
lrwxrwxrwx 1 root root 28 Jul 17 07:46 /etc/init.d/docker -> /usr/local/etc/init.d/docker
```

3. If you cat the startup script youâ€™ll see something like
```
#import settings from profile (e.g. HTTP_PROXY, HTTPS_PROXY)
$ test -f "/var/lib/boot2docker/profile" && . "/var/lib/boot2docker/profile"
```
4. Check to see if profile file exists and add the needed configuration

```
$ vi /var/lib/boot2docker/profile

# Add lines  : 
export HTTP_PROXY=http://{proxy_host}:{proxy_port}
export HTTPS_PROXY=https://{proxy_host}:{proxy_port}
```

5. Restart the docker process
```
$ sudo /etc/init.d/docker restart
```
Done, now you can pull docker images behind a proxy.
