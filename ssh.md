# SSH

> Secure Shell (SSH) is a cryptographic network protocol for securing data communication. It establishes a secure channel over an insecure network in a client-server architecture, connecting an SSH client application with an SSH server.

## Linux setup a SSH key authentication

Voici la procÃ©dure : d'abord - et si ce n'est dÃ©jÃ  fait - il vous faut installer le client openSSH :

[Source](http://prendreuncafe.com/blog/post/2005/08/29/262-installer-sa-cle-ssh-sur-un-serveur-distant)

```bash
$ sudo apt-get update
$ sudo apt-get install openssh-client
```

Il faudra de mÃªme disposer de ssh-server sur la machine distante. Ceci fait, il vous faut gÃ©nÃ©rer vos clÃ©s publiques et privÃ©es :

```bash
$ ssh-keygen -t dsa -b 1024

Generating public/private dsa key pair.
Enter file in which to save the key (/home/monlogin/.ssh/id_dsa):
```

Appuyez sur EntrÃ©e, vos clÃ©s seront sauvegardÃ©es dans le repertoire cachÃ© .ssh.

```
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

Une fois votre passphrase entrÃ©e, un message de confirmation de crÃ©ation est affichÃ© :

```
Your identification has been saved in /home/monlogin/.ssh/id_dsa.
Your public key has been saved in /home/monlogin/.ssh/id_dsa.pub.
The key fingerprint is:
XX:8a:XX:91:XX:ae:XX:23:XX:2e:XX:ed:XX:4e:XX:b8 monlogin@mamachine
```

Ensuite, il vous faut ajouter votre clÃ© publique Ã  la liste des clÃ©s autorisÃ©es du serveur distant. En admettant que votre serveur se nomme toto.host.org et que votre nom d'utilisateur est titi [1], cela donne :

```bash
$ ssh-copy-id -i ~/.ssh/id_dsa.pub titi@toto.host.org
Password:
```

Entrez le mot de passe de l'utilisateur titi sur la machine distante. Si l'opÃ©ration d'ajout de votre clÃ© a rÃ©ussi, un message est affichÃ© :

```
Now try logging into the machine, with "ssh 'titi@toto.host.org'", and check in:

  .ssh/authorized_keys
to make sure we haven't added extra keys that you weren't expecting.
```

Et voila, il ne vous reste plus qu'Ã  lancer un ```ssh titi@toto.host.org```, il vous sera demandÃ© votre passphrase et vous serez logguÃ© :)

```bash
$ ssh titi@toto.host.org
Enter passphrase for key '/home/monlogin/.ssh/id_dsa':
```

Create an aliases: ```alias <raccourci>='<commande>'```

```bash
alias sshtoto='ssh titi@toto.host.org'
```
Sauvegarder le fichier. Pour que les modifications soient prises en compte, il faut recharger le fichier .bashrc :
```
. .bashrc
```
Voila ! Maintenant vous pouvez tester votre tout nouvel alias en lanÃ§ant :
```
$ sshtoto
```

