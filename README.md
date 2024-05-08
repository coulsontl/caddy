# Caddy Docker Custom Image

Caddy Docker Container with custom modules

I took the base caddy docker image; added below custom modules and built custom caddy docker container. I just followed "Building your own Caddy-based image" section in the below link

https://hub.docker.com/_/caddy?tab=description 

# Modules Included

## DNS

caddy-dns/cloudflare \
caddy-dns/dnspod \
caddy-dns/gandi \
caddy-dns/lego-deprecated \
caddy-dns/route53 \
caddy-dns/alidns \
caddy-dns/azure \
caddy-dns/digitalocean \
caddy-dns/duckdns \
caddy-dns/hetzner \
caddy-dns/openstack-designate \
caddy-dns/vultr

## Others

abiosoft/caddy-hmac \
lolPants/caddy-requestid \
mholt/caddy-webdav \
abiosoft/caddy-json-parse \
hslatman/caddy-crowdsec-bouncer \
porech/caddy-maxmind-geolocation \
WeidiDeng/caddy-cloudflare-ip \
ueffel/caddy-brotli \
caddyserver/replace-response \
coulsontl/auth-modifier \
corazawaf/coraza-caddy/v2

### Please find LICENSE link for caddy below 

https://github.com/caddyserver/caddy/blob/master/LICENSE

# Docker Compose

```
version: 3
services:
  caddy:
    image: coulsontl/caddy
    ports:
      - "80:80"
      - "443:443"
    network_mode: bridge
    restart: always
    volumes:
      - ./Caddyfile:/etc/caddy/Caddyfile
      - ./data:/data
      - ./config:/config
      - ./logs:/var/log/caddy
    environment:
      - TZ=Asia/Shanghai
```
