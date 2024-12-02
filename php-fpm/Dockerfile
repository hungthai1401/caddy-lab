# Builder stage for Caddy
FROM caddy:2-alpine as caddy

# Final stage
FROM php:8.1-fpm-alpine

# Install Caddy from first stage
COPY --from=caddy /usr/bin/caddy /usr/bin/caddy

# Configure PHP
COPY Caddyfile /etc/caddy/Caddyfile

# Setup work directory
WORKDIR /srv
COPY index.php /srv/index.php
RUN chown -R www-data:www-data /srv

EXPOSE 80 443

# Start services
CMD php-fpm & caddy run --config /etc/caddy/Caddyfile