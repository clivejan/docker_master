FROM alpine:3.8
LABEL maintainer="Chihwei <clive.jan@gmail.com>"
LABEL description="This Dockerfile installs Apache & PHP."

ENV PHPVERSION=5

RUN apk add --update apache2 php${PHPVERSION}-apache2 php${PHPVERSION} && \
    rm -rf /var/cache/apk/* && \
    mkdir /run/apache2 && \
    rm -f /var/www/localhost/htdocs/index.html && \
    echo "<?php phpinfo() ?>" > /var/www/localhost/htdocs/index.php && \
    chmod 755 /var/www/localhost/htdocs/index.php

EXPOSE 80/tcp

ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]
