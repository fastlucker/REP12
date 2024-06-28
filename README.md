# SearXNG
## Deploy

> For more configurations and information see 👉 **[SearXNG](https://github.com/searxng/searxng)**.

- After deployment the service starts at **http://*[ip]*:7980**

```sh
git clone https://github.com/zmh-program/searxng.git
cd searxng

sed -i "s|ultrasecretkey|$(openssl rand -hex 32)|g" searxng/settings.yml # Generate the secret key

# Edit the [.env](https://github.com/searxng/searxng-docker/blob/master/.env) file to set the hostname and an email
# Edit the [searxng/settings.yml](https://github.com/searxng/searxng-docker/blob/master/searxng/settings.yml) file according to your need

# Check everything is working: `docker-compose up`

docker-compose up -d
```

## Update
```sh
git pull
docker-compose pull
docker-compose up -d
```

## Arch Support
- amd64
- arm64
- arm/v7 ([not when using redis](https://github.com/searxng/searxng-docker/issues/239))
