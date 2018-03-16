MACE Model Zoo
=====
[![build status](http://v9.git.n.xiaomi.com/deep-computing/mace-models/badges/master/build.svg)](http://v9.git.n.xiaomi.com/deep-computing/mace-models/commits/master)

This folder contains MACE models deployment configurations.

Introduction
---
Each `yml` deployment script describes a case of deployments, which will 
generate one or one group (in case more than one ABIs specified) of static 
libraries and headers. Each `yml` scripts contains one or more models.


How to setup CI
---
1. Install docker and add current user into docker group
```sh
sudo groupadd docker
sudo gpasswd -a $USER docker
```

2. Create ssh key persistence folder on host (For the 1st time)
```sh
mkdir docker-ssh-keys
```

3. Start docker as deamon
```sh
docker run --name mace-dev-runner -it -d --rm --privileged -v /dev/bus/usb:/dev/bus/usb --net=host -v `pwd`/docker-ssh-keys:/root/.ssh cr.d.xiaomi.net/mace/gitlab-runner
```

4. Create and set deploy key in your project (For the 1st time)
```sh
ssh-keygen
cat ~/.ssh/id_ras.pub
```

5. Register as gitlab ci runner (Follows the instruction in project Settings/Pipelines page)
```sh
docker exec -it mace-dev-runner gitlab-runner register
# Please enter the gitlab-ci tags for this runner (comma separated):
# master
# Whether to run untagged builds [true/false]:
# [false]: true
```