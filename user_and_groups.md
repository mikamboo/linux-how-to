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


### Add existing user to an existing group 

```bash 
$ useradd -G {group-name} username


# Example add user Koukou to sudo (super users) group

$ useradd -G sudo kouakou
```

### Désactiver le mot de pass root

Après ça il n'est plus possible de se connecter au compte __root__ avec un mot de passe. Pour administrer le sytème il faudra utiliser les ```sudoers```


```bash
$  sudo passwd -l root
```
