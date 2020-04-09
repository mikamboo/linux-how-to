# Commons

**How to get systeme infos ?**

```text
# Kernel Version?
uname -a

# Release infos
lsb_release -a
cat /etc/*-release
```

**How to check process/ports usage ?**

```text
netstat -taupen

# Process of user toto
top -U toto
```

**Add user to sudoers group**

```text
adduser -aG toto sudo
```

