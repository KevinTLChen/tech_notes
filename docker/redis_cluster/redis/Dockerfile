# syntax=docker/dockerfile:1
FROM redis:6.2.7-bullseye
COPY redis.conf /usr/local/etc/redis/redis.conf
CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]