FROM lalitmohann/php7.2-fpm
MAINTAINER Lalit Mohan <lalitmohanwd@gmail.com>

RUN apt-get update
RUN apt-get install --yes --force-yes ssh rsync

# Magento Cloud
RUN curl -sS https://accounts.magento.cloud/cli/installer | php \
    && cp -R $HOME/.magento-cloud/bin/* /usr/local/bin/