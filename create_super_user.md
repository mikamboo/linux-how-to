# Create super user


### Création d'un super utilisateur 

```bash


```


### Désactiver le mot de pass root

Après ça il n'est plus possible de se connecter au compte __root__ avec un mot de passe. Pour administrer le sytème il faudra utiliser les ```sudoers```


```bash
$  sudo passwd -l root
```