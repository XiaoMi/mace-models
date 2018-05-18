MiAI Model Zoo
==============
[![build status](http://v9.git.n.xiaomi.com/deep-computing/mace-models/badges/master/build.svg)](http://v9.git.n.xiaomi.com/deep-computing/mace-models/commits/master)

This project hosts MiAI Compute Engine models deployment configurations.

Introduction
---
Each `yml` deployment script describes a case of deployments, which will 
generate one or one group (in case more than one ABIs specified) of static 
libraries and headers. Each `yml` scripts contains one or more models.

Trigger a build on CI server
---
For example, build `mobilenet-v1` (can be any grep style regular expression) model against `sdm845` (can be a comma seperated list, values from `adb shell getprop | grep ro.board.platform`):
```sh
curl -X POST \
     -F token=eadfeb029dd9fd8fa4bf3db9e10fd2 \
     -F ref=master \
     -F "variables[TARGET_FILE_PATTERN]=mobilenet-v1-gpu.yml" \
     -F "variables[TARGET_SOCS]=sdm845" \
     http://v9.git.n.xiaomi.com/api/v4/projects/1362/trigger/pipeline
```