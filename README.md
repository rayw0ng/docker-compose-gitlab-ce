# Compose file for local Gitlab Community Edition

[![License](https://img.shields.io/github/license/mgcrea/docker-compose-gitlab-ce.svg?style=flat)](https://tldrlegal.com/license/mit-license)

Working `docker-compose.yml` for official [gitlab-ce](https://hub.docker.com/r/gitlab/gitlab-ce) docker images leveraging separate instances for services:

- Uses official [postgres](https://hub.docker.com/_/postgres/) docker image
- Uses official [redis](https://hub.docker.com/_/redis/) docker image
- Comes with a [gitlab-runner](https://hub.docker.com/r/gitlab/gitlab-runner/) instance

## Quickstart

- You can quickly start your compose gitlab instance (requires a working automated nginx_proxy compose instance)

```bash
git clone git@github.com:jeremy-kreditech/docker-compose-gitlab-ce.git gitlab; cd $_
cp .env.default .env; nano .env
make
docker-compose up -d
```


## Check postgres bundled version

```bash
source .env
docker run --rm -it gitlab/gitlab-ce:${GITLAB_CE_VERSION} postgres --version
```

## Templates

- [gitlab.rb](https://gitlab.com/gitlab-org/omnibus-gitlab/blob/master/files/gitlab-config-template/gitlab.rb.template)

## Related Documentation

- [Gitlab installation](https://docs.gitlab.com/ce/install/docker.html)
- [GitLab Docker images](https://docs.gitlab.com/omnibus/docker/)
- [GitLab CI Docker images](https://docs.gitlab.com/ce/ci/docker/using_docker_images.html)
- [Using a non-bundled web-server](https://docs.gitlab.com/omnibus/settings/nginx.html#using-a-non-bundled-web-server)

