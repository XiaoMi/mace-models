MACE Model Zoo
=====
[![build status](http://v9.git.n.xiaomi.com/deep-computing/mace-models/badges/master/build.svg)](http://v9.git.n.xiaomi.com/deep-computing/mace-models/commits/master)

This project hosts MACE models deployment configurations.

Introduction
---
Each `yml` deployment script describes a case of deployments, which will 
generate one or one group (in case more than one ABIs specified) of static 
libraries and headers. Each `yml` scripts contains one or more models.

Trigger a build on CI server
---
For example, build `mobilenet-v1` (can be any grep style regular expression) model against `sdm845` (can be a list, values from `adb shell getprop | grep ro.board.platform`):
```sh
curl -X POST \
     -F token=eadfeb029dd9fd8fa4bf3db9e10fd2 \
     -F ref=master \
     -F "variables[TARGET_FILE_PATTERN]=mobilenet-v1.yml" \
     -F "variables[TARGET_SOCS]=sdm845" \
     http://v9.git.n.xiaomi.com/api/v4/projects/1362/trigger/pipeline
```


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

3. Mount fds bucket to host (Ask mace-dev for AKSK)
```sh
export XIAOMI_ACCESS_KEY_ID=XXXXXXXXXXXXX
export XIAOMI_SECRET_ACCESS_KEY=XXXXXXXXXXXXXXXXXXXX
export XIAOMI_FDS_ENDPOINT=cnbj1-inner-fds.api.xiaomi.net
sudo fdsfuse mace-build-output /fds -o use_cache=/fdscache
```

4. Start docker as deamon
```sh
docker run --name mace-dev-runner -it -d --rm --privileged -v /fds/:/mace-build-output -v /dev/bus/usb:/dev/bus/usb -v /home/mace/gitlab-runner/config.toml:/etc/gitlab-runner/config.toml --net=host -v /home/mace/docker-ssh-keys:/root/.ssh cr.d.xiaomi.net/mace/gitlab-runner
```

5. Create and set deploy key in your project (For the 1st time)
```sh
ssh-keygen
cat ~/.ssh/id_ras.pub
```

6. Register as gitlab ci runner (Follows the instruction in project Settings/Pipelines page)
```sh
docker exec -it mace-dev-runner gitlab-runner register
# Please enter the gitlab-ci tags for this runner (comma separated):
# master
# Whether to run untagged builds [true/false]:
# [false]: true
```

7. Config auto register after runner host reboot
```
sudo chmod +x /etc/rc.local

echo '#!/bin/bash

# Waiting for fdsfuse dependencies
sleep 10

sudo XIAOMI_ACCESS_KEY_ID=AKWLOJLQHUJAIQWAB4 \
    XIAOMI_SECRET_ACCESS_KEY=eHH3ODS3tjHY4IjEIWFvHg9I6JEZbsTD9JGZF0mq \
    XIAOMI_FDS_ENDPOINT=cnbj1-inner-fds.api.xiaomi.net \
    fdsfuse mace-build-output /fds -o use_cache=/fdscache

docker run --name mace-dev-runner -it -d --rm --privileged -v /fds/:/mace-build-output -v /dev/bus/usb:/dev/bus/usb -v /home/mace/gitlab-runner/config.toml:/etc/gitlab-runner/config.toml --net=host -v /home/mace/docker-ssh-keys:/root/.ssh cr.d.xiaomi.net/mace/gitlab-runner

exit 0
' > /etc/rc.local
```
