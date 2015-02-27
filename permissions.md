# Permissions

**How can I get file permissions ?**

* __stat__ :  Display file or file system status

Use the ```-c``` option to specify output format.

```bash
stat -c "%a %A %n" *
```
Where ```%a``` gives access rights in octal, ```%n``` gives file name





