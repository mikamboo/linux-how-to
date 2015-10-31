# Create super user


### Création d'un super utilisateur 

```bash

# Pass root user
$ su - 

# Create nyangy user with its home directory at "/home/nyangui"
$ useradd -m -G sudo nyangui

```


### Désactiver le mot de pass root

Après ça il n'est plus possible de se connecter au compte __root__ avec un mot de passe. Pour administrer le sytème il faudra utiliser les ```sudoers```


```bash
$  sudo passwd -l root
```