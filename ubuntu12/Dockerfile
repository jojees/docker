FROM ubuntu:12.04

RUN sed -i 's/\(deb.*precise-updates.*\)$/#\1/g' /etc/apt/sources.list \
    && echo 'APT::Install-Recommends 0;' >> /etc/apt/apt.conf.d/01norecommends \
    && echo 'APT::Install-Suggests 0;' >> /etc/apt/apt.conf.d/01norecommends \
    && export TERM=xterm \
    && DEBIAN_FRONTEND=noninteractive \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && apt-get clean \
    && apt-get update \
    && apt-get install -y curl vim tree build-essential openssl libssl-dev git groff\
    && curl "https://bootstrap.pypa.io/get-pip.py" -o "/tmp/get-pip.py" \
    && python2.7 /tmp/get-pip.py \
    && rm -f /tmp/get-pip.py
