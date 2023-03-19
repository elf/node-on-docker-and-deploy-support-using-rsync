# As an example, create docker environment for NodeJS and deployment using rsync

# Set up for development on your PC

```
# Retreive files.
git clone <GIT_REPOSITORY>

# Preparation
docker-compose build
docker-compose run --rm app npm install

# Boot a Docker container.
docker-compose up -d
# or
docker-compose up
```


# Set up for deployment on GitHub

## Actions secrets and variables

Use GitHub Actions to deploy your app. For that, set some values in Actions secrets and variables.

### PROD_DEPLOY_SSH_HOST

Specify the host to deploy to. e.g., `/home/app/target/prod/`

### PROD_DEPLOY_TARGET_DIR

Specify the directory in which to deploy. e.g., `target.example.com`

### PROD_DEPLOY_SSH_KNOWN_HOSTS

You can get the vaue by `ssh-keyscan`

```
ubuntu@dev:~$ ssh-keyscan target.example.com
# target.example.com:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3
target.example.com ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDOqLNKGxNLTncLs1XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXMntrZGxgfutBh+4XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX//6amqYVFwUjnngpMU6nMrXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXm8M3g0F3K0AlAX6YfS4PYkm9nY56Kox6wnBqV41r6UyjXXXXXXXX=
# target.example.com:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3
target.example.com ecdsa-sha2-nistp256 AAAAEXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXaBk7KvbhLDN9oWmghzYZG4Twy5I2g=
# target.example.com:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3
target.example.com ssh-ed25519 AAAAC3NzXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXHUTotNG/l
# target.example.com:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3
# target.example.com:22 SSH-2.0-OpenSSH_8.9p1 Ubuntu-3
```

### PROD_DEPLOY_SSH_KEY

Specify the ssh private key to be used for deployment.

This value can be created with the ssh-keygen command, for example.

You can create the key by `ssh-keygen`.

```
-----BEGIN OPENSSH PRIVATE KEY-----
cM+7BfElL07sw6qrpaz0IsRBK2s3TFMVIgpk5tGzFSeKbYo6FJER/hPwcq2xqjpMndcLMa
NhAAAAAwEAAQAAAgEA6zsJ7UX472k7fBlosr5DTBApihtVpk2bawm3NUwbT0RRxBmgWWGY
sKx9ntH690ifAAAAE3Rhcm9qMTIwNUBnbWFpbC5jb20BAgMEBQYH
q8t6GkwL5Uv+tmTWy9AbizdTuVy6FggPFVDQp9EPj1gyRN0cO6xYwwZxgdeo+NH9kU0E9j
(snip)
kcnzXp7ZYdYb7Oa4sqAC8E9BdDD8ei4ELWw7oKBa422rQzHR68Qdx/dpdeeZ+8DmMkiw9C
euEebRrt5VTH9PqwstT55oqZ1Shi8hxT7jvrP5p+mLiHiAoK9AYodgNi+eoW+BoWIvmgCh
-----END OPENSSH PRIVATE KEY-----
```

### PROD_DEPLOY_SSH_USER

Specify the ssh user to be used for deployment. e.g., `ubuntu`

# References

- https://github.com/actions/checkout
