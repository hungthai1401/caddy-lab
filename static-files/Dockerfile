FROM caddy:2-alpine

COPY Caddyfile /etc/caddy/Caddyfile
COPY index.html /srv/index.html

EXPOSE 80

CMD ["caddy", "run", "--config", "/etc/caddy/Caddyfile"]