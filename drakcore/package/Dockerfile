ARG IMAGE
FROM $IMAGE

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y wget curl python3 python3-venv python3-pip debhelper devscripts && \
    curl https://debs.icedev.pl/manual/focal-dev/dh-virtualenv_1.2~dev-1_all.deb -o dh-virtualenv.deb && \
    apt install -y ./dh-virtualenv.deb && \
    curl -sL https://deb.nodesource.com/setup_13.x | bash - && \
    apt-get install -y nodejs && \
    pip3 install virtualenv

COPY drakcore /build
WORKDIR /build
