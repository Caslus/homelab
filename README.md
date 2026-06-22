# Homelab

This setup is designed to be modular and easy to maintain. Each service is defined in its own `docker-compose.yml` file with environment variables for configuration. Since I'm behind a CGNAT, I use [Cloudflare Zero Trust](https://www.cloudflare.com/zero-trust/) and a tunnel to expose my services to devices outside my network.

> **Note:** This is not a tutorial but a personal reference. If you find it useful, feel free to use it. However, many configurations are stored in data folders, environment variables, or the Cloudflare dashboard, which are not included here. I won’t be providing support for this setup, but feel free to reach out if you have questions.

---

## 🚀 Services

These are the services I personally felt a need for, each with its own purpose and functionality, all running in Docker containers. You can find more details in their respective repositories.

### 📚 Media & Content Management

- [**Komga**](https://github.com/gotson/komga) → Media server for comics, manga, and books.
- [**Jellyfin**](https://github.com/jellyfin/jellyfin) → Media server for movies, TV shows, music, and photos.
- [**Seerr**](https://github.com/seerr-team/seerr) → Media request and management tool for Jellyfin.
- [**Radarr**](https://github.com/Radarr/Radarr) → Movie collection manager and downloader.
- [**Sonarr**](https://github.com/Sonarr/Sonarr) → TV show collection manager and downloader.
- [**Prowlarr**](https://github.com/Prowlarr/Prowlarr) → Indexer manager/proxy for various torrent and usenet indexers.
- [**Bazarr**](https://github.com/morpheus65535/bazarr) → Subtitle downloader and manager.
- [**Profilarr**](https://github.com/Dictionarry-Hub/profilarr) → Profile manager for Radarr and Sonarr to automate quality and release profile management.

### 🌐 Networking & Remote Access

- [**Cloudflared**](https://github.com/cloudflare/cloudflared) → Secure tunnel to expose local services through Cloudflare.

### 🔄 Automation & Monitoring

- [**n8n**](https://github.com/n8n-io/n8n) → Workflow automation tool for integrating and automating services.
- [**KISS**](https://github.com/Caslus/kiss) → Custom dashboard for monitoring and accessing services.

### 🧾 Finances
- [**ezBookkeeping**](https://github.com/mayswind/ezbookkeeping) → Personal finance management tool.

### 📥 Downloads & Storage

- [**Deluge**](https://github.com/deluge-torrent/deluge) → Web-based BitTorrent client for managing downloads.

---

## 📂 Structure

The folder structure ensures easy maintenance by keeping each service isolated and organized:

```
/
├── docker-compose.yml
├── .env
├── apps/
│   ├── <service>/
│   │   ├── docker-compose.yml
│   │   ├── .env (when needed)
├── data/
│   ├── <service>/
├── books/
├── media/
├── downloads/
```

- **`docker-compose.yml`** → Main file including all services.
- **`.env`** → Environment variables for the main `docker-compose.yml` file.
- **`apps/`** → Each service has its own folder with a `docker-compose.yml` and an optional `.env` file.
- **`data/`** → Persistent storage, mounted to containers to prevent data loss.
- **`books/`** → Storage location for Komga books.
- **`media/`** → Storage location for Jellyfin media.
- **`downloads/`** → Folder for Deluge downloads.