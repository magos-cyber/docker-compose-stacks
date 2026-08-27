# Docker Compose Stacks

Production-ready Docker Compose stacks for homelab & self-hosting. Each stack is self-contained, well-documented, and ready to deploy with a single command.

## 📁 Structure

```
docker-compose-stacks/
├── media/              # Jellyfin, *arr, Immich, Navidrome
├── monitoring/         # Prometheus, Grafana, Uptime Kuma, cAdvisor, node-exporter
├── network/            # Pi-hole, Traefik, AdGuard+Unbound
├── utils/              # Portainer, Vaultwarden, Homer, Watchtower, Dozzle, IT-Tools, Stirling PDF
├── home-assistant/     # Home Assistant + Mosquitto MQTT
├── productivity/       # Nextcloud, Paperless-ngx, Gitea
├── auth/               # Authentik identity server
└── databases/          # MariaDB, PostgreSQL, Redis shared stack
```

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/magos-cyber/docker-compose-stacks.git
cd docker-compose-stacks

# Choose a stack and deploy
cd monitoring
cp .env.example .env
# Edit .env with your values
docker compose up -d
```

## 📝 Available Stacks

### 📺 Media
| Stack | Description | Ports |
|-------|-------------|-------|
| `media/` | Jellyfin + Sonarr/Radarr | 8096, 7878, 8989 |
| `media/immich/` | Immich photo management | 2283 |
| `media/navidrome/` | Navidrome music streaming | 4533 |

### 📊 Monitoring
| Stack | Description | Ports |
|-------|-------------|-------|
| `monitoring/` | Prometheus + Grafana + Uptime Kuma + cAdvisor + node-exporter | 9090, 3000, 3001, 8080, 9100 |

### 🌐 Network
| Stack | Description | Ports |
|-------|-------------|-------|
| `network/` | Pi-hole DNS ad-blocker | 53, 8080 |
| `network/traefik/` | Traefik v3 reverse proxy + Let's Encrypt | 80, 443, 8080 |
| `network/dns/` | AdGuard Home + Unbound (DNS-over-TLS) | 53, 3000, 5353 |

### 🛠️ Utilities
| Stack | Description | Ports |
|-------|-------------|-------|
| `utils/` | Portainer + Vaultwarden + Homer | 9000, 8080, 8081 |
| `utils/utility.yml` | Watchtower + Dozzle + IT-Tools + Stirling PDF | 9999, 8082, 8083 |

### 🏠 Home Automation
| Stack | Description | Ports |
|-------|-------------|-------|
| `home-assistant/` | Home Assistant + Mosquitto MQTT | 8123, 1883 |

### 📄 Productivity
| Stack | Description | Ports |
|-------|-------------|-------|
| `productivity/nextcloud/` | Nextcloud (PostgreSQL + Redis + Cron) | 8080 |
| `productivity/paperless-ngx/` | Paperless-ngx document management | 8000 |
| `productivity/gitea/` | Gitea self-hosted Git | 3000, 2222 |

### 🔐 Authentication
| Stack | Description | Ports |
|-------|-------------|-------|
| `auth/authentik/` | Authentik identity server | 9000, 9443 |

### 🗄️ Databases
| Stack | Description | Ports |
|-------|-------------|-------|
| `databases/` | MariaDB + PostgreSQL + Redis | 3306, 5432, 6379 |

## ⚙️ Configuration

Each stack includes a `.env.example` file. Copy it to `.env`, edit the values, then run `docker compose up -d`.

```bash
cd <stack-name>
cp .env.example .env
nano .env  # or your preferred editor
docker compose up -d
```

## 🔒 Security Notes

- Change default passwords before deploying to production
- Use strong, unique passwords for databases and admin accounts
- Consider using Traefik as a reverse proxy for all services
- Enable HTTPS via Let's Encrypt for public-facing services

## 🤝 Contributing

Contributions are welcome! Please:
- Keep stacks in English
- Include `.env.example` files
- Document all environment variables
- Test before submitting

## 📜 License

MIT License — see [LICENSE](LICENSE) for details.