# SearXNG Docker
## How to use it

- [Install docker](https://docs.docker.com/install/)
- Get searxng-docker
  ```sh
  git clone https://github.com/zmh-program/searxng.git
  cd searxng
  docker compose up -d
  ```
- Edit the [.env](https://github.com/searxng/searxng-docker/blob/master/.env) file to set the hostname and an email
- Generate the secret key `sed -i "s|ultrasecretkey|$(openssl rand -hex 32)|g" searxng/settings.yml`
- Edit the [searxng/settings.yml](https://github.com/searxng/searxng-docker/blob/master/searxng/settings.yml) file according to your need
- Check everything is working: `docker compose up`
- Run SearXNG in the background: `docker compose up -d`


## Arch Support
- amd64
- arm64
- arm/v7 ([not when using redis](https://github.com/searxng/searxng-docker/issues/239))

## Update Version
```sh
git pull
docker compose pull
docker compose up -d
```
