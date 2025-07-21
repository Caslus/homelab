# Homelab

This setup is designed to be modular and easy to maintain. Each service is defined in its own `docker-compose.yml` file with environment variables for configuration. Since I'm behind a CGNAT, I use [Cloudflare Zero Trust](https://www.cloudflare.com/zero-trust/) and a tunnel to expose my services to devices outside my network.

> **Note:** This is not a tutorial but a personal reference. If you find it useful, feel free to use it. However, many configurations are stored in data folders, environment variables, or the Cloudflare dashboard, which are not included here. I won’t be providing support for this setup, but feel free to reach out if you have questions.

---

## 🚀 Services

These are the services I personally felt a need for, each with its own purpose and functionality, all running in Docker containers. You can find more details in their respective repositories.

### 📚 Media & Content Management

- [**Calibre-Web**](https://github.com/janeczku/calibre-web) → Web app for managing e-books.
- [**Stremio-Server**](https://www.stremio.com/) → Streaming server for media content.
- [**Fusion**](https://github.com/0x2E/fusion) → RSS reader and aggregator for keeping up with news and content feeds.

### 🌐 Networking & Remote Access

- [**Cloudflared**](https://github.com/cloudflare/cloudflared) → Secure tunnel to expose local services through Cloudflare.
- [**Sshwifty**](https://github.com/nirui/sshwifty) → Web-based SSH client for remote access via browser.

### 🔄 Automation & Monitoring

- [**n8n**](https://github.com/n8n-io/n8n) → Workflow automation tool for integrating and automating services.
- [**Cup**](https://github.com/sergi0g/cup) → Checks for Docker container updates.
- [**Beszel**](https://github.com/henrygd/beszel) → Lightweight server monitoring hub with historical data, docker stats, and alerts.
- [**Uptime-Kuma**](https://github.com/louislam/uptime-kuma) → Self-hosted uptime monitoring tool.

### 📊 Productivity & Organization

- [**Homarr**](https://github.com/homarr-labs/homarr) → Customizable dashboard for organizing and accessing services.
- [**Wallos**](https://github.com/ellite/Wallos) → Personal subscription tracker.
- [**Stirling-PDF**](https://github.com/Stirling-Tools/Stirling-PDF) → Web-based PDF manipulation tool.

### 📥 Downloads & Storage

- [**qBittorrent**](https://github.com/qbittorrent/qBittorrent) → Web-based BitTorrent client for managing downloads.

### 🎮 Game Server

- [**tModLoader**](https://github.com/hexlo/terraria-tmodloader-server) → Modded Terraria server for me and my friends.

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
├── downloads/
```

- **`docker-compose.yml`** → Main file including all services.
- **`.env`** → Environment variables for the main `docker-compose.yml` file.
- **`apps/`** → Each service has its own folder with a `docker-compose.yml` and an optional `.env` file.
- **`data/`** → Persistent storage, mounted to containers to prevent data loss.
- **`books/`** → Storage location for Calibre-Web books.
- **`downloads/`** → Folder for qBittorrent downloads.
