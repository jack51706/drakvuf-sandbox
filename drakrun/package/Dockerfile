ARG IMAGE
FROM $IMAGE

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y \
    wget curl python3 python3-pip debhelper devscripts \
    libpixman-1-0 libpng16-16 libfdt1 libglib2.0-dev 'libjson-c[34]' libyajl2 libaio1 && \
    curl https://debs.icedev.pl/manual/focal-dev/dh-virtualenv_1.2~dev-1_all.deb -o dh-virtualenv.deb && \
    pip3 install virtualenv && \
    apt install -y ./dh-virtualenv.deb

RUN wget -O drakvuf.deb https://debs.icedev.pl/manual/focal-dev/drakvuf-bundle-0.7-git20200430114005+3fcbee8-1-generic.deb && \
    dpkg -i drakvuf.deb

COPY drakrun /build
WORKDIR /build
