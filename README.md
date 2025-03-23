# homelab

this setup is supped to be modular and easy to maintain. each service is defined in its own `docker-compose.yml` file and environment variables. i'm behind a cgnat so i'm using cloudflare zero trust and a tunnel to expose my services to devices outside my network.
i will add more stuff to this whenever i have some spare time.

## services

- **cloudflared**: cloudflare tunnel
- **homarr**: homepage
- **qbittorrent**: torrent client
- **sshwifty**: remote ssh from the browser
- **calibre-web**: ebook library
- **stremio-server**: server for stremio

## config

the `.env.example` files are my config, i only got the tokens out. so if, for some reason, you want to use this for your homelab:

- rename `.env.example` files to `.env`
- fill in the empty variables with whatever is needed
- setup [cloudflare tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/)
- `docker compose up -d`
