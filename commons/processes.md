# Processes

## Find Out Which Process Is Listening Upon a Port

```text
$ netstat -tulpn
$ netstat -tulpn | grep :80
```

## Check details of runnning process

```bash
# Eg. check PID 1138
$ ls -l /proc/1138/exe
```

## Find out the processes PID that opened tcp port 7000 :

```text
$ fuser 7000/tcp
```

## Get description

```bash
$ man node
$ whatis node # node (1) - Server-side JavaScript
```

Read more at [cyberciti.biz](http://www.cyberciti.biz/faq/what-process-has-open-linux-port/)

