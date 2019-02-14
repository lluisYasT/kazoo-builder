FROM telephoneorg/debian:stretch

MAINTAINER Lluis Satorre <lluisyast@gmail.com>

ENV     APP kazoo
ENV     USER $APP
ENV     HOME /opt/$APP

COPY    build-builder.sh /tmp/
RUN     /tmp/build-builder.sh

ENV     KAZOO_VERSION=${KAZOO_VERSION:-4.3}
ENV     KAZOO_CONFIGS_VERSION=${KAZOO_CONFIGS_VERSION:-4.3}
ENV     KAZOO_SOUNDS_VERSION=${KAZOO_SOUNDS_VERSION:-4.3}

LABEL   app.kazoo.configs.version=$KAZOO_CONFIGS_VERSION
LABEL   app.kazoo.sounds.version=$KAZOO_SOUNDS_VERSION
LABEL   app.kazoo.core.version=$KAZOO_VERSION

COPY    patches /tmp/patches
COPY    build-kazoo.sh /

WORKDIR $HOME

CMD     ["/build-kazoo.sh"]
