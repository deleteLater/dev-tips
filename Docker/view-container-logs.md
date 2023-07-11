## Keynote

The official `nginx` image creates a symbolic link from `/var/log/nginx/access.log` to `/dev/stdout`, and creates another symbolic link from `/var/log/nginx/error.log` to `/dev/stderr`, overwriting the log files and causing logs to be sent to the relevant special device instead. See the [Dockerfile](https://github.com/nginxinc/docker-nginx/blob/master/stable/alpine-slim/Dockerfile#L105).

The official `httpd` driver changes the `httpd` application’s configuration to write its normal output directly to `/proc/self/fd/1` (which is `STDOUT`) and its errors to `/proc/self/fd/2` (which is `STDERR`). See the [Dockerfile](https://github.com/docker-library/httpd/blob/master/2.4/alpine/Dockerfile#L204).

## Ref
- https://docs.docker.com/config/containers/logging/