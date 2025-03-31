# homelab

this setup is supped to be modular and easy to maintain. each service is defined in its own `docker-compose.yml` file and environment variables. i'm behind a cgnat so i'm using cloudflare zero trust and a tunnel to expose my services to devices outside my network.
i will add more stuff to this whenever i have some spare time.

## services

- **calibre-web**: ebook library
- **cloudflared**: cloudflare tunnel
- **homarr**: homepage
- **n8n**: workflow automation
- **qbittorrent**: torrent client
- **sshwifty**: remote ssh from the browser
- **stremio-server**: server for stremio
- **wallos**: expense tracker
- **cup**: docker image update watcher
- **beszel**: monitoring

## config

the `.env.example` files are my config, i only got the tokens out. so if, for some reason, you want to use this for your homelab:

- rename `.env.example` files to `.env`
- fill in the empty variables with whatever is needed
- setup [cloudflare tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/)
- `docker compose up -d`
