# Home Server

A quick way to setup my home server.

## Software Stack

- [Truenas Scale](https://www.truenas.com/truenas-scale/)
- [Homepage](https://gethomepage.dev/latest/)
- [Pi-hole](https://pi-hole.net/)
- [Unbound](https://nlnetlabs.nl/projects/unbound/about/)
- [Home Assistant](https://www.home-assistant.io/)
- [Uptime Kuma](https://uptime.kuma.pet/)
- [MySpeed](https://myspeed.gnmyt.dev/)
- [Nextcloud](https://nextcloud.com/)
- [Syncthing](https://syncthing.net/)

## Truenas Scale

We will be using Truenas Scale as the base OS for the server. It is a Linux based OS which will allow us to use Docker. So you must [Download](https://www.truenas.com/download-truenas-scale/) and install Truenas Scale from the official website.

## Docker

Our entire environment will be running on Docker. So we need to install Docker on Truenas Scale. The following command will install Docker, but it is recommended to check the official documentation for the latest installation instructions.

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh --dry-run
```

## Unbound

Unbound is a validating, recursive, and caching DNS resolver. It is designed to be fast and lean and incorporates modern features based on open standards. We will be using Unbound as our DNS resolver.

Check this other repository to know more about Unbound and how to install it: [Unbound](https://github.com/Rapha-Borges/Unbound-Servidor-DNS-Recursivo)

## Homepage

Homepage is a web-based, self-hosted dashboard, that allows you to monitor your server. It's free, open-source, and fully customizable. So you can customize it to your needs or use my configuration.

As we are using Docker, we can use the `docker compose up` command to start the Homepage service. But first, we need to setup the `.env` file with the environment variables.

```bash
cd homepage
cp .env.example .env
vim .env
```

```bash
docker-compose up -d
```

## Servers Apllications

Now we have all the base services running, we can start to install the applications that we want to use. The first step, if you will use the same applications as me, is to configure the `.env` file with the environment variables.

```bash
cd applications
cp .env.example .env
vim .env
```

After that, we can use the `docker compose up` command to start the services.

```bash
docker-compose up -d
```

