FROM bitnami/minideb-extras:jessie-r15
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install related packages
RUN echo 'deb http://ftp.au.debian.org/debian/ stretch main contrib non-free' > /etc/apt/sources.list.d/stretch.list && \
apt-get update && \
apt-get install -y --no-install-recommends openjdk-8-* && \
rm /etc/apt/sources.list.d/stretch.list && \
apt-get clean && \
rm -rf /var/lib/apt/lists/*

RUN mkdir /bitnami
WORKDIR /bitnami
ENTRYPOINT chown -R bitnami:bitnami /bitnami &&  su bitnami -c './mvnw -Pprod clean package'