# User and Groups

> Warning : You need to login as root before

### Create user Kouakou

```bash
$ useradd -m kouakou
```


### Setup A Password For Kouakou

```bash 
$ passwd kouakou
```


### Add existing user to an existing group (ubuntu)

```bash 
$ useradd -G {group-name} username


# Example add user Koukou to classroom group

$ useradd -G sudo kouakou
```

