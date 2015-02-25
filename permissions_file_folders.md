# Files, folders and permissions


**How can I get octal file permissions ?**

* __stat__ :  Display file or file system status

Use the ```-c alias --format``` option to specify output format.

```bash
stat -c "%a %A %n" *
```
Where ```%a```is access rights in octal, ```%n```is file name




