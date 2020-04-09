# SSH

> Secure Shell \(SSH\) is a cryptographic network protocol for securing data communication. It establishes a secure channel over an insecure network in a client-server architecture, connecting an SSH client application with an SSH server.

## Linux setup a SSH key authentication

First insttal ssh client : **openSSH**

```bash
$ sudo apt-get update
$ sudo apt-get install openssh-client
```

We need also a **ssh-server** on the remote host. Now, generate ssh key on the client machine:

```bash
$ ssh-keygen -t dsa -b 1024

Generating public/private dsa key pair.
Enter file in which to save the key (/home/monlogin/.ssh/id_dsa):
```

Key will be stored in `~/.ssh` folder.

```text
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

Confirmation message

```text
Your identification has been saved in /home/monlogin/.ssh/id_dsa.
Your public key has been saved in /home/monlogin/.ssh/id_dsa.pub.
The key fingerprint is:
XX:8a:XX:91:XX:ae:XX:23:XX:2e:XX:ed:XX:4e:XX:b8 monlogin@mamachine
```

Add our public key on the **authorozed hosts** list of remote server.

```bash
$ ssh-copy-id -i ~/.ssh/id_dsa.pub titi@toto.host.org
Password:

Now try logging into the machine, with "ssh 'titi@toto.host.org'", and check in:

  .ssh/authorized_keys
to make sure we haven't added extra keys that you weren't expecting.
```

We can now run `ssh titi@toto.host.org`. If setted, the ssh key passphase will be asked.

```bash
$ ssh titi@toto.host.org
Enter passphrase for key '/home/monlogin/.ssh/id_dsa':
```

For more convenience, create an aliases: `sshtoto` for access to `toto.host.org` as `titi` user.

```bash
echo "alias sshtoto='ssh titi@toto.host.org'" > ~/.bashrc

# Make change to take effect
. .bashrc
```

Test created alias :

```text
$ sshtoto
```

