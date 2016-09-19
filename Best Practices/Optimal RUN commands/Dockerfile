FROM debian:jessie
MAINTAINER Karel Bemelmans <mail@karelbemelmans.com>

# Example 1: A Drupal module

# - download tarball from remote host using curl
# - check the MD5 sum after download
# - use ENV variables to keep updating the version easy

ENV MEMCACHE_VERSION 7.x-1.5
ENV MEMCACHE_MD5 3ea99c76b6429f0bbc8f922cd91eb459

RUN mkdir -p sites/all/modules/contrib/memcache \
  && curl -Lks https://ftp.drupal.org/files/projects/memcache-${MEMCACHE_VERSION}.tar.gz \
       -o /tmp/memcache-${MEMCACHE_VERSION}.tar.gz \
  && echo "${MEMCACHE_MD5} /tmp/memcache-${MEMCACHE_VERSION}.tar.gz" | md5sum -c - \
  && tar --strip=1 -xzf /tmp/memcache-${MEMCACHE_VERSION}.tar.gz -C sites/all/modules/contrib/memcache \
  && rm /tmp/memcache-${MEMCACHE_VERSION}.tar.gz


