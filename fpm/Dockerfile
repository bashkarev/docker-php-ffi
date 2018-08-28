FROM php:7.3-rc-fpm-alpine3.8

RUN set -xe; \
    apk add --no-cache --virtual .persistent-deps libffi-dev; \
    mkdir -p /usr/src/php/ext/ffi; \
	curl -sL https://api.github.com/repos/dstogov/php-ffi/tarball/master | tar -xz --strip-components 1 -C /usr/src/php/ext/ffi; \
	docker-php-ext-configure ffi --with-ffi; \
	docker-php-ext-install ffi;\
	docker-php-source delete; \
	rm -rf /var/cache/*