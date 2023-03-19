# As an example, create docer environment and deployment using rsync

# Actions secrets and variables

Use GitHub Actions to deploy your app. For that, set some values in Actions secrets and variables.

## PROD_DEPLOY_SSH_HOST

Specify the host to deploy to.

## PROD_DEPLOY_TARGET_DIR

Specify the directory in which to deploy.

## PROD_DEPLOY_SSH_KNOWN_HOSTS


## PROD_DEPLOY_SSH_KEY

Specify the ssh private key to be used for deployment.

This value can be created with the ssh-keygen command, for example.

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

## PROD_DEPLOY_SSH_USER

Specify the ssh user to be used for deployment.

# References

- https://github.com/actions/checkout
