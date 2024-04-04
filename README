# lakeFS Testing Repo

This repository contains a starter `docker compose` stack to spin up:

- minio
- postgres
- lakeFS

## lakeFS Repo

lakeFS starts up in a fairly blank-slate format for your testing. This
docker-compose file does create a bucket called `data-lake` in the minio volumne
for you. It appears that lakeFS cannot create buckets when initializing a new
repo. Creating the bucket must be done separately.

## lakectl Configuration

My recommendation (for now) is to download lakectl to your local machine via the
[GitHub Release](https://github.com/treeverse/lakeFS/releases) page. When you
boot up lakeFS for the first time, you will be prompted to create an admin user.

    Pre-populating an admin user and credentials is only possible when using the
    "local" database option. As this is not reflective of the desired runtime
    operation, I am opting to use the "postgres" database option. The database
    is not the object store, it is just used for metadata storage.

When creating the initial user, you will be presented with the access key and
secret key for the user just created. You will be offered to download the
credentials and store them on you local drive. Storing this file at
`~/.lakectl.yaml` will make it visible to `lakectl` binary, and simplify
authentication.

## minio

This docker compose creates a single bucket named `data-lake`. This is important
becase lakeFS cannot create buckets, so if there is no bucket, it will not be
able to create a repository in your object store.
