# Docker Compose Stacks

Production-ready Docker Compose configurations for homelab services.

## Stacks

### Media
- `media/jellyfin` - Media server
- `media/plex` - Media server alternative

### Monitoring
- `monitoring/loki` - Log aggregation
- `monitoring/promtail` - Log shipping
- `monitoring/uptime-kuma` - Uptime monitoring

### Productivity
- `productivity/nextcloud` - File sync and share

### Network
- `network/wireguard` - VPN server

### Auth
- `auth/vaultwarden` - Password manager

## Usage

```bash
cd monitoring/loki
docker-compose up -d
```

## Requirements

- Docker Engine 20.10+
- Docker Compose v2

## License

MIT
