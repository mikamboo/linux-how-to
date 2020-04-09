# Install and use

## Install Docker

```text
sudo apt-get update
sudo apt-get install docker.io
source /etc/bash_completion.d/docker.io
sudo docker -v

# if [ERROR :  Error loading docker apparmor profile: exec...] for linux Mint
sudo apt-get install apparmor
```

## Docker commons commands

```text
# Show running containers
sudo docker ps

# Show all containers
sudo docker ps -a

# Show images
sudo docker images    

# Delete containers
sudo docker rm container_name_or_id

# Delete image
sudo docker rmi image_name_or_id
```

## Docker cleanup commands

```bash
# Kill all running containers
docker kill $(docker ps -q)

# Delete all stopped containers (including data-only containers)
docker rm $(docker ps -a -q)

# Delete all ‘untagged/dangling’ (<none>) images
docker rmi $(docker images -q -f dangling=true)

# Delete ALL images (DANGER)
docker rmi $(docker images -q)
```

**It might also be useful to create bash aliases for these commands, for example:**

```bash
# ~/.bash_aliases

# Kill all running containers.
alias dockerkillall='docker kill $(docker ps -q)'

# Delete all stopped containers.
alias dockercleanc='printf "\n>>> Deleting stopped containers\n\n" && docker rm $(docker ps -a -q)'

# Delete all untagged images.
alias dockercleani='printf "\n>>> Deleting untagged images\n\n" && docker rmi $(docker images -q -f dangling=true)'

# Delete all stopped containers and untagged images.
alias dockerclean='dockercleanc || true && dockercleani'
```

