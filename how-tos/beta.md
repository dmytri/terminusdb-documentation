---
title: Accessing TerminusHub with Bootstrap - Certificate Help
layout: default
parent: How Tos
nav_order: 9
---
## Accessing TerminusHub with Bootstrap - Certificate Help

You can access the Bootstrap through the [TerminusDB Download Center](https://terminusdb.com/hub/download)

## Requirements

Requirements: Git, Bash and Docker

Windows users: Git Bash and Docker

## Installing

Clone terminusdb-bootstrap and enter the directory:

```bash
git clone https://github.com/terminusdb/terminusdb-bootstrap.git
cd terminusdb-bootstrap
git checkout rc
```

Run the following command to change the default options, to be part of our beta

```bash
echo "
# shellcheck shell=sh
# shellcheck disable=SC2034

#
# ENVIRONMENT
#
# To persist environment settings copy this file to ENV
#

# Docker command
#TERMINUSDB_DOCKER=sudo docker

# Container
#TERMINUSDB_CONTAINER=terminusdb-server
#TERMINUSDB_REPOSITORY=terminusdb/terminusdb-server
#TERMINUSDB_NETWORK=bridge
#TERMINUSDB_LABEL_FILE=labels

# Version
#TERMINUSDB_TAG=beta

# Name of Docker Storage Volume
#TERMINUSDB_STORAGE=terminusdb_storage_local

# Container Port to Publish
#TERMINUSDB_PORT=6363

# Local Directory to Mount inside Container
#TERMINUSDB_LOCAL=/home/username/localfiles

# URL To TermiunusDB Console
#TERMINUSDB_CONSOLE_BASE_URL=//127.0.0.1:3005

# Server
#TERMINUSDB_AUTOLOGIN=false
#TERMINUSDB_PASS=root
#TERMINUSDB_SERVER_IP=127.0.0.1
#TERMINUSDB_CONSOLE=http://127.0.0.1/console

# HTTPS
TERMINUSDB_HTTPS_ENABLED=true
#TERMINUSDB_SSL_CERT=/etc/letsencrypt/live/example.com/fullchain.pem
#TERMINUSDB_SSL_CERT_KEY=/etc/letsencrypt/live/example.com/privkey.pem

# vim:ft=sh
" > ENV
```

Run `./terminusdb-container run`

You should be able to access terminusdb on https://127.0.0.1:6363/ . Unfortunately, the browser
will give you a certificate warning. Do not worry, since the server is running on your own machine, nobody
is intercepting your traffic.
