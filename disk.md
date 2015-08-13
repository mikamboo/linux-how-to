
# Disk usage & filesystem




### ```du``` : Linux disk usage


Find out the disk usage summary of __/home/toto__ directory tree

```bash
$ du /home/toto
```

Same in __Human Readable Format__ with ```-h``` option

```bash
$ du -h  /home/toto


# Add "s" flag to get summary of a grand total disk usage size
$ du -sh  /home/toto
```




### ```df``` : Linux disk filesystem

Basic usage (-h flag for human readable)

```bash
df -h
```

To see the information of only device __/home__ file system in human readable format use the following command

```bash
df -hT /home
```

### Use ```du``` and ```dh``` commands : live Demo
 
TODO