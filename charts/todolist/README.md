# todolist

Deploys Red Hat Open Innovation Labs's todolist application.

In case you want to run it manually with podman:

```
podman network create todonet
podman run --rm --name mongodb --net todonet -d mongo:4.0
podman run --rm --name todolist --net todonet -e NODE_ENV=production -e OPENSHIFT_NODEJS_PORT=9000 -e OPENSHIFT_MONGODB_DB_URL=mongodb://mongodb/ -e OPENSHIFT_APP_NAME=todolist -p 9000:9000 monodot/todolist
```