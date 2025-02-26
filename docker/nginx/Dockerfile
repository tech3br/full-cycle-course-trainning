FROM nginx:alpine-slim AS builder

COPY html /usr/share/nginx/html

FROM scratch

COPY --from=builder /etc/nginx /etc/nginx/
COPY --from=builder /usr/share/nginx/html /usr/share/nginx/html

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["nginx", "-g", "daemon off;"]
